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
| hub.rat.dev | ✅ Good | 146.00 MB/s | 0.343s | ✅ Verified |
| docker.1panel.live | ✅ Good | 128.74 MB/s | 0.389s | ✅ Verified |
| docker.wanpeng.top | ✅ Good | 163.13 MB/s | 0.307s | ✅ Verified |
| doublezonline.cloud | ✅ Good | 206.94 MB/s | 0.242s | ✅ Verified |
| docker.mrxn.net | ✅ Good | 122.44 MB/s | 0.409s | ✅ Verified |
| docker.anyhub.us.kg | ✅ Good | 126.78 MB/s | 0.395s | ✅ Verified |
| docker.imgdb.de | ✅ Good | 11.71 MB/s | 4.276s | ✅ Verified |
| docker.awsl9527.cn | ✅ Good | 94.31 MB/s | 0.531s | ✅ Verified |
| dockerpull.org | ❌ Failed | - | - | - |
| docker.m.daocloud.io | ❌ Failed | - | - | - |

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
             "doublezonline.cloud","docker.wanpeng.top","hub.rat.dev"
     ]
}
```

 3.重启 Docker 服务
```shell
systemctl daemon-reload
systemctl restart docker
```
