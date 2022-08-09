# FAQ


# Issues I ran into
## AWS VPC and EC2 access issues
1. First problem - I did not want to install anything on my local computers from SourceForge (right or wrong that is my stance). I found installing anything Cloudflared. This drove me to look to use either a VM or use another cloud system. 
* After searching a bit more, I discovered that I could use AWS EC2 instance for this. I also found that I had, unfortunately on a previous endeavour messed up the AWS VPC such that it would not accept ANY connections or provide any communications interface. 
* The solution delete ALL VPCs and create the default VPC again. Re-start all instances and apply the newly created (default) VPC. This fixed all the connectivity issues I had. 

2. 
