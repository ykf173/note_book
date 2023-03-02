## docker 骚操作

* 1. 查看docker环境查看日志：
```bash
查看docker images: docker images | grep contract
查看id:  docker ps -a | grep contract 
```

* 2. 运行dock er环境
```bash
进入docker环境： sudo docker exec -it your_docker_id /bin/bash
Docker 服务日志查看： docker logs -f id
关闭docker：docker stop id
```

* 3. docker保存加载
```bash
docker commit -m ‘’ dickerid docker镜像名
docker save xx.tar docker镜像名
docker load -i xx.tar
```

* 4. 复制docker内部文件与宿主机文件相互复制

```bash
docker ps | grep （docker部分名称）
得到所需dokcer id
从docker内部复制文件到宿主机内部：docker cp (dockerid):/文件位置 宿主机位置
从宿主机复制到docker内部：docker cp  宿主机位置 (dockerid):/文件位置
```

  

  