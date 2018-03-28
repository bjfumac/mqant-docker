# mqant-docker
A docker image for mqant framework

**1. Download mqantserver files and edit config**
```
cd /
git clone https://github.com/liangdas/mqantserver.git

# Open mqantserver/bin/conf/server.json ,serach key "StaticPath" and modify the value to "/mqantserver/bin"
```

**2. Setup docker image**
```
cd /
git clone https://github.com/bjfumac/mqant-docker.git
cd mqant-docker
sudo docker build -t="bjfumac/mqant" .
```

**3. Run**
```
sudo docker run --name mqantserver -p 8080:8080 -p 3653:3653  -p 7700:7700  -p 7701:7701 -v /mqantserver:/mqantserver -idt bjfumac/mqant  

# Change first '/mqantserver' to your local mqantserver files path in step 1

sudo docker exec mqantserver sh start.sh  
```
**4. Test**

Use your browser to access http://127.0.0.1:8080/mqant/chat/index.html

**5. Other Commands**  
After you run the test successfully.You can start/stop the server by these commands below  
*(You should restart server after you edit the local mqantserver files for recompiling)*:  
**Stop server:**  
```
sudo docker stop mqantserver  
```
**Start server:**  
```
sudo docker start mqantserver  
sudo docker exec mqantserver sh start.sh
```
#### 如果觉得对你的项目有帮助，欢迎微信打赏请我喝一杯咖啡，谢谢^^
#### 本人QQ:68552233 （反馈问题可联系）
![avatar](https://github.com/bjfumac/Asset/raw/master/images/wx_ma.jpg)
