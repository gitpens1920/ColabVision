# FAQ


# Issues I ran into
## AWS VPC and EC2 access issues
1. First problem - I did not want to install anything on my local computers from SourceForge (right or wrong that is my stance). I found installing anything Cloudflared. This drove me to look to use either a VM or use another cloud system. 
* After searching a bit more, I discovered that I could use AWS EC2 instance for this. I also found that I had, unfortunately on a previous endeavour messed up the AWS VPC such that it would not accept ANY connections or provide any communications interface. 
* The solution delete ALL VPCs and create the default VPC again. Re-start all instances and apply the newly created (default) VPC. This fixed all the connectivity issues I had. 



## ML and Image recognition
### Video Streaming
1. I chose YOLOv5, as the model for the speed and availability. During testing, I found the detection script failed while using the streaming when the video from various open source sites. There was not a clear cause other than the video failing to play when accessed via the script. I am guessing it has to do with the ads.
2. The video streaming speed greatly impacts the model. At 2x speeds the it was very difficult to identify traffic lights at night. 
