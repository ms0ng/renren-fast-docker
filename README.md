# 人人开源 前端/后端/数据库 搭建

## 快速启动
```bash
git clone https://github.com/ms0ng/renren-fast-docker.git && cd renren-fast-docker && docker-compose up -d
```
Docker-compose需要Build镜像,请在良好的网络状况情况下启动

## 使用
浏览器访问 [8080端口](http://localhost:8080/)

登录的账号密码为 admin/admin

## 文件结构
```
|-- db_data             #Mysql数据库容器的映射
|-- mysql
    |-- Dockerfile
    |-- mysql           #Mysql数据库脚本
    |-- run.sh          #初始化数据库的脚本
|-- renren-fast
    |-- Dockerfile
    |-- renren-fast.jar #人人开源的后端程序
|-- renren-fast-vue
    |-- renren-fast-vue #人人开源的前端源码
    |-- Dockerfile
|-- docker-compose.yml
|-- README.md
```