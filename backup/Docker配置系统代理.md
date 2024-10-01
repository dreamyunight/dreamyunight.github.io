## Docker 代理配置

```powershell
sudo mkdir /etc/systemd/system/docker.service.d && \
sudo touch /etc/systemd/system/docker.service.d/http-proxy.conf && \
sudo vim /etc/systemd/system/docker.service.d/http-proxy.conf
```

写入

```conf
[Service]
Environment="HTTP_PROXY=http://127.0.0.1:7890/“
Environment="HTTPS_PROXY=http://127.0.0.1:7890/"
Environment="NO_PROXY=localhost,127.0.0.1"
```

或者带代理账号密码

```
[Service]
Environment="HTTP_PROXY=http://Clash:123456@127.0.0.1:7890/“
Environment="HTTPS_PROXY=http://Clash:123456@127.0.0.1:7890/"
Environment="NO_PROXY=localhost,127.0.0.1"
```

重启 Docker

```powershell
sudo systemctl daemon-reload &&\
sudo systemctl restart docker
```