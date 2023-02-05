
# docker命令
/***********************************************
/*	关闭所有镜像并删除		*/
/**********************************************
先提升为root		sudo su
关闭所有镜像并删除		docker stop $(docker ps -q) & docker rm $(docker ps -aq)

拉取镜像			docker pull vulhub/thinkphp:6.0.12
查看已拉取的镜像		docker images
运行容器			docker run vulhub/thinkphp:6.0.12

/**********************************
/*	vulhub改镜像	*/
/********************************
sudo vim /etc/docker/deanon.json

{
"insecure-registries": [
    "10.0.0.12:5000"
  ],
  "registry-mirrors": [
    "https://docker.mirrors.ustc.edu.cn/",
    "https://hub-mirror.c.163.com",
    "https://registry.docker-cn.com"
  ]
}

systemctl restart docker

systemctl stop docker
systemctl start docker.service
systemctl status docker.service
