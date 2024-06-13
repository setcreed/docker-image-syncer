# docker-image-syncer
使用github action能力将docker hub上的镜像同步到阿里云容器镜像仓库


# 使用方式
## 配置阿里云
登录 https://cr.console.aliyun.com/ 阿里云容器镜像服务，配置命名空间、用户名、密码、仓库地址

## 配置GitHub Action
fork本项目，进入Settings->Secret and variables->Actions->New Repository secret
配置相关的环境变量，分别是：
- ALIYUN_NAME_SPACE
- ALIYUN_REGISTRY_USER
- ALIYUN_REGISTRY_PASSWORD
- ALIYUN_REGISTRY

对应上阿里云镜像服务的配置

## 添加想要同步的镜像
在images.txt 上添加镜像即可，支持手动指定架构
如：
```bash
# 基础镜像
nginx
golang:1.22.4-alpine3.20

# 支持指定架构
--platform=linux/amd64 alpine:3.20
--platform=linux/arm64 alpine:3.20
```
