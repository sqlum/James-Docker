James-Docker
=====
将James配置文件夹从Host挂载到容器内的Docker镜像相关信息

##### 前台运行并查看日志：
docker run \
  -p 25:25 \
  -p 465:465 \
  -p 110:110 \
  -v /opt/servers/james/conf:/usr/local/james/conf \
  --name james \
  stonelu/james-docker:v0.2

##### 后台启动：
docker run -d \
  -p 25:25 \
  -p 465:465 \
  -p 110:110 \
  -v /opt/servers/james/conf:/usr/local/james/conf \
  --name james \
  stonelu/james-docker:v0.2
  
##### 查看 后台启动时 最后10条日志(并实时跟踪新日志)：
docker logs -tf --tail 10 james

##### 进入 后台启动时 容器：
docker exec -it james /bin/sh
