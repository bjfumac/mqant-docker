# mqant-docker
A docker image for mqant framework

**1.Download mqantserver files and edit config**

git clone https://github.com/liangdas/mqantserver.git

Open mqantserver/bin/conf/server.json ,serach key "StaticPath" and modify the value to "/mqantserver/bin"


**2.Setup docker image**

git clone https://github.com/bjfumac/mqant-docker.git

cd mqant-docker

sudo docker build -t="bjfumac/mqant" .


**3.Run**

sudo docker run --name mqantserver -p 8080:8080 -p 3653:3653 -v ~/mqantserver:/mqantserver -idt bjfumac/mqant  
*(Change ~/mqantserver to your local mqantserver files path in step 1)*

sudo docker exec mqantserver sh start.sh  
*(You should run this line to recompile after you edit the local mqantserver files)*

**4.Test**

Use your browser to access http://127.0.0.1:8080/mqant/chat/index.html

**5.Other**
After you run the test successfully.You can start/stop the server by these commands below:  
Stop server:  
sudo docker stop mqantserver  
Start server:  
sudo docker start mqantserver  
sudo docker exec mqantserver sh start.sh


