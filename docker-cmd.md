# 镜像命令
docker pull ubuntu:16.04     # 拉取ubuntu16.04镜像<br>
docker images                 # 列出本地镜像<br>
docker rmi ubuntu:16.04      # 删除ubuntu16.04镜像<br>

dcoker import - new-image-name:v1 < image.tar #导入本地镜像,可以给镜像指定新名称<br>
docker save imageid > xxx.tar #保存镜像<br>
docker save -o xxx.tar imagexx:latest #指定标签，保存镜像<br>
docker load < xxx.tar #导入xxx镜像,不能对载入的镜像重命名<br>
docker load -i xxx.tar #导入xxx镜像,不能对载入的镜像重命名<br>
docker build -t nginx:v1 .     # 使用Dockerfile创建nginx镜像<br>

# 容器命令
docker run -it ubuntu:16.04 bash     # 启动ubuntu容器并进入bash<br>
docker ps                       # 列出运行中的容器<br>
docker stop container_id       # 停止指定容器<br>
docker rm container_id         # 删除指定容器<br>
docker export <容器ID> -o <文件名>.tar #导出容器到本地文件<br>
docker exec -it nginx /bin/sh  # 进入正在运行的nginx容器中 <br>

# compose命令
docker-compose up -d          # 启动所有服务,均在compose.yml文件目录下执行<br>          
docker-compose logs -f       # 滚动查看实时日志<br>
docker-compose ps            # 列出项目中的容器   <br>
docker-compose start|restart|down       # 启动|重启|停止所有服务   <br>
docker-compose exec nginx /bin/sh  # 进入正在运行的nginx服务容器中<br>

docker-compose build         # 重新构建项目中的镜像<br>
docker-compose config        # 校验和查看 compose 文件 <br>

# nginx相关
docker-compose exec nginx nginx -t #测试nginx配置文件语法<br>
docker-compose exec nginx  nginx -s reload  #nginx动态加载配置文件<br>
docker-compose logs -f -n 100 nginx #滚动查看nginx近100条日志<br>
or<br>
docker-compose logs -f --tail 100 nginx #滚动查看nginx近100条日志<br>

# redis相关
docker exec -it redis redis-cli #redis-cli命令行连接redis容器<br>

# 其他命令 
docker info #查看docker daemon信息<br>
docker login                   # 登录Docker Hub<br>
docker search mysql            # 搜索mysql镜像<br>
docker commit container_id     # 从容器创建镜像<br>
docker network ls              #查看网络<br>
docker volume ls #查看卷<br>
docker network inspect bridge #查看网桥信息<br>


