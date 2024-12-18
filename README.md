# Docker 镜像测速

## Why

因为众所周知的原因，国内访问 Docker Hub 的速度非常慢。广大热心网友贡献了大量的镜像加速服务，但是速度参差不齐。


所以该项目旨在罗列互联网上分享的镜像地址，并生成测速结果。

> [!WARNING]
> 测速利用 GitHub Actions，服务器托管在国外，因此测速结果中的速度快不代表国内拉取快。
>

本项目尽量保证罗列的镜像地址可用。

## 测速结果

| Registry | Status | Speed | Time | Integrity |
|----------|--------|-------|------|-----------|
| hub.rat.dev | ✅ Good | 98.39 MB/s | 0.509s | ✅ Verified |
| docker.1panel.live | ✅ Good | 65.80 MB/s | 0.761s | ✅ Verified |
| docker.wanpeng.top | ✅ Good | 72.58 MB/s | 0.690s | ✅ Verified |
| doublezonline.cloud | ✅ Good | 110.79 MB/s | 0.452s | ✅ Verified |
| docker.mrxn.net | ✅ Good | 65.21 MB/s | 0.768s | ✅ Verified |
| docker.anyhub.us.kg | ✅ Good | 8.55 MB/s | 5.852s | ✅ Verified |
| docker.imgdb.de | ✅ Good | 11.55 MB/s | 4.333s | ✅ Verified |
| docker.awsl9527.cn | ✅ Good | 78.74 MB/s | 0.636s | ✅ Verified |
| dockerpull.org | ✅ Good | 27.73 MB/s | 1.806s | ✅ Verified |
| docker.m.daocloud.io | ✅ Good | 11.37 MB/s | 4.401s | ✅ Verified |

## Docker 配置

1. 安装 Docker
```shell
export DOWNLOAD_URL="https://mirrors.tuna.tsinghua.edu.cn/docker-ce"
# 如您使用 curl
curl -fsSL https://raw.githubusercontent.com/docker/docker-install/master/install.sh | sh
# 如您使用 wget
wget -O- https://raw.githubusercontent.com/docker/docker-install/master/install.sh | sh
```

2. 配置镜像

```shell
mkdir -p /etc/docker
nano /etc/docker/daemon.json
```

```json
{
     "registry-mirrors": [
             "doublezonline.cloud","hub.rat.dev","docker.awsl9527.cn"
     ]
}
```

 3.重启 Docker 服务
```shell
systemctl daemon-reload
systemctl restart docker
```
