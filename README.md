### 下载项目

```bash
git clone --recursive https://github.com/arcturus-weather/.github.git
```

### Docker 部署

安装 docker

```bash
sudo curl -sSL get.docker.com | sh
```

修改国内镜像源

```bash
sudo mkdir -p /etc/docker
```

```bash
sudo vim /etc/docker/daemon.json
```

```
{
  "registry-mirrors": [
     "https://docker.mirrors.ustc.edu.cn",
     "https://mirror.ccs.tencentyun.com",
     "https://hub-mirror.c.163.com",
     "https://reg-mirror.qiniu.com"
  ]
}
```

```bash
systemctl daemon-reload
```

```bash
systemctl restart docker
```

测试安装是否成功

```bash
sudo docker run hello-world
```

安装 docker-compose

```bash
sudo curl -L \
"https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" \
-o /usr/local/bin/docker-compose
```

```bash
sudo chmod +x /usr/local/bin/docker-compose
```

测试安装是否成功

```bash
docker-compose --version
```

在 `web` 和 `server` 文件夹下新建 `.env` 文件(具体内容见相应文件夹), 最后运行

```bash
sudo docker-compose up
```

访问地址 `http://localhost`
