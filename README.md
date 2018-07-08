# docker-registry2
docker-registry2

- REGISTRY_AUTH=htpasswd
- REGISTRY_AUTH_HTPASSWD_REALM=Registry Realm
- REGISTRY_AUTH_HTPASSWD_PATH=/auth/htpasswd

## 启动
docker-compose up -d

# 开启代理无法push
proxy是registry v2的pull though cache功能。开启了cache的话就无法做push了。registry的官网有这个说明。
因为我这里是harbor的本地仓库 并且是docker部署的
之后找到registry的配置文件
common/config/registry/config.yml

proxy:
  #remoteurl: https://registry-1.docker.io
  remoteurl: https://plfmv1h0.mirror.aliyuncs.com
