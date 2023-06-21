# 前言

本项目为 [开源实例系列](https://dujun.io/open-source-examples.html) 文章对应的 Docker 镜像生成源码。

# 目录说明

```00000_BASE``` 目录为基础镜像，其他目录为相应的项目镜像。

# 构建说明

以构建 WordPress 项目为例，进入目录 ```10000_WordPress```。修改 ```docker-compose.yml```，将 EXAMPLE_DOMAIN 设置为你自己的项目域名。然后执行构建和启动。

构建镜像：

```vim
docker-compose -f build.yml build
```

启动容器（组）：

```vim
docker-compose up -d
```