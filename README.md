# Network-Automation-Environment
## This is a Docker container for Network Automation Environment with Python 3.9.16
### How to use __without docker-compose__
1. Download file  
   >git clone https://github.com/toshikondo/Network-Automation-Environment.git
2. Move to Network-Automation-Environment directory  
   >cd Network-Automation-Environment
3. Build Docker image
   >$docker build -f ./docker/Dockerfile ./docker --build-arg PASSWD=\<YOUR PASSWORD\> -t \<docker image\> 
4. Run Docker container
   >$docker run -p 53022:22 -v ./Scripts:/root/Scripts -v ./Output:/root/Output -d \<docker image name or ID\>  
5. Login Docker container from remote device  
   &emsp;Login remote device  
   &emsp;ssh root@\<ip address of docker host\> -p 53022  
   &emsp;password: \<YOUR PASSWORD\>   (If you did not set YOUR PASSWORD default password is "mypassword")

### How to use __with docker-compose__
1. Download file  
   >git clone https://github.com/toshikondo/Network-Automation-Environment.git
2. Move to Python3.9.16-Env directory
   >cd Network-Automation-Environment
3. Set your own password. (If you did not edit the password defauld password is "mypassword")  
   &emsp;Edit password(PASSWD: \<YOUR PASSWORD\>) in docker-compose.yml to set your own password.
     
4. Build Docker image & RUN Docker container
   >docker compose up -d --build
5. Login Docker container from remote device  
   &emsp;Login remote device  
   &emsp;ssh root@\<ip address of docker host\> -p 53022  
   &emsp;password: \<YOUR PASSWORD\>   (If you did not set YOUR PASSWORD default password is "mypassword")       
  
  
    
- All files in __Scripts__ and __Output__ directories is untracked. 
- __Scripts__ and __Output__ directories are mounted on this docker container.(__/root/Scripts__, __/root/Output__)
- You can put your automation script files in __Scripts__ directory.   
- If you want to add a python library you need to add the package's name on __requirements.txt__