# Hydro In Docker

本仓库修改自[Hydro](https://github.com/hydro-dev/Hydro)官方仓库`install/docker`，修改了一些内容。

由于官方不再对`docker`安装进行维护，所以不保证能够安装成功。

支持以下编译器:
```text
1. python3
2. gcc/g++
3. fp-compiler
4. rustc
5. libjavascriptcoregtk-4.0-bin
6. golang
7. ruby
8. mono
9. ghc
10. openjdk-17-jdk
11. php7.4
```

目前已经测试在我的云服务器（腾讯云 ubuntu22.04 amd64）上可以正常运行，制作镜像的时间约为7分钟。如果由于网络原因，建议修改`judge`内的`Dockerfile`，取消注释并修改为你所用的`debian`源。


