# Start E2C instance (circa Fall22)

**As described in https://github.com/jbnunn/CARLADesktop, start with:

OR - https://aws.amazon.com/marketplace/pp/prodview-vkoypmw6w3ta2?ref=recommended&m=model_BI_2022-08-01, if the commandline and troubleshooting are undesired.
1. Select AWS image:

![image](https://user-images.githubusercontent.com/99305660/187033141-ddd0a0a8-1b3e-4c19-995a-aea368bca599.png)

2. Test on Micro server

![image](https://user-images.githubusercontent.com/99305660/187033191-f065fe0a-14ba-4b10-a41b-0d48e1439c73.png)

3. Start and test Ubuntu gui
The byobu terminal interface provides some benefits when working with the EC2 instance via SSH. 

> I've found using a VNC application to be the easiest for managing the logins and workflow (so to speak). 
> Remmina or Nomachine have worked well. If the local client is Ubuntu (v18 or above I believe), Remmina is pre-installed. 

Read through this for micro instance setup of limited programs.
https://help.ubuntu.com/community/Installation/LowMemorySystems

4. Connect to the server and run the items below to install a less resource intensive desktop manaagement system.

https://ubuntu.com/tutorials/ubuntu-desktop-aws#2-setting-up-tightvnc-on-aws

https://lubuntu.me/

```bash
sudo apt update
sudo apt install --no-install-recommends lubuntu-desktop
sudo apt install tightvncserver
```

Run one of the below commands to setup the destkop (a lighter less intensive desktop) ~700MB
```
sudo apt install gnome-panel gnome-settings-daemon metacity nautilus gnome-terminal
```
or a desktop aligned to the standard 20.LTS version of ubuntu ~1.4GB
```
sudo apt-get install -y ubuntu-desktop gnome-panel gnome-settings-daemon metacity nautilus gnome-terminal xfce4 xterm
export DEBIAN_FRONTEND=noninteractive
```

If opting for the larger installation

complete the server setup you do not need to run the vnc and vim command below.

```
vncserver :1
vim ~/.vnc/xstartup
```
and alternative setup


In the VIM editor use keys
- "i" to enter the insert text mode
- "esc" to leave a mode
- "d" to delete a line while not in insert mode. 
- ":" then type wq to save file. 

Replace the file data with:
```
#!/bin/sh

export XKL_XMODMAP_DISABLE=1
unset SESSION_MANAGER
unset DBUS_SESSION_BUS_ADDRESS

[ -x /etc/vnc/xstartup ] && exec /etc/vnc/xstartup
[ -r $HOME/.Xresources ] && xrdb $HOME/.Xresources
xsetroot -solid grey

vncconfig -iconic &
gnome-panel &
gnome-settings-daemon &
metacity &
nautilus &
gnome-terminal &
```

Log into the server checkout the new instance!

4. Install Carla on larger "SPOT" Ubuntu instance. 
5. 
