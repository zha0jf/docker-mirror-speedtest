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
| hub.rat.dev | ✅ Good | 130.67 MB/s | 0.383s | ✅ Verified |
| docker.1panel.live | ✅ Good | 116.11 MB/s | 0.431s | ✅ Verified |
| docker.wanpeng.top | ✅ Good | 94.96 MB/s | 0.527s | ✅ Verified |
| doublezonline.cloud | ✅ Good | 199.39 MB/s | 0.251s | ✅ Verified |
| docker.mrxn.net | ✅ Good | 142.99 MB/s | 0.350s | ✅ Verified |
| lynn520.xyz | ❌ Failed | - | - | - |
| ginger20240704.asia | ❌ Failed | - | - | - |
| docker.anyhub.us.kg | ✅ Good | 10.27 MB/s | 4.870s | ✅ Verified |
| docker.wget.at | ❌ Failed | - | - | - |
| docker.awsl9527.cn | ✅ Good | 92.50 MB/s | 0.541s | ✅ Verified |
| dockerpull.com | ❌ Failed | - | - | - |
| dhub.kubesre.xyz | ✅ Good | 6.34 MB/s | 7.885s | ✅ Verified |
| docker.m.daocloud.io | ✅ Good | 14.79 MB/s | 3.382s | ✅ Verified |
| dockerhub.icu | ❌ Failed | - | - | - |

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
             "doublezonline.cloud","docker.mrxn.net","hub.rat.dev"
     ]
}
```

 3.重启 Docker 服务
```shell
systemctl daemon-reload
systemctl restart docker
```
