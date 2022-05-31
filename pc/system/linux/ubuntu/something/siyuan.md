# 思源笔记

```
# 安装Docker
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo  "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce

# 部署思源
docker pull b3log/siyuan

# 设定位置并提供权限
mkdir /me/siyuan
sudo chmod 777 /me/siyuan

# 启动思源
sudo docker run -v /me/siyuan:/me/siyuan -p 6806:6806 b3log/siyuan -resident -workspace /me/siyuan -accessAuthCode <你的密码>

# 访问思源
http://<你的ip>:6860

# 更新思源
docker container list
docker stop <...>
docker image pull b3log/siyuan
```
