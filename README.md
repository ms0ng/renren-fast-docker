# 人人开源 后端搭建

## 从Docker启动Mysql

```bash
docker run --name [容器名] -e MYSQL_ROOT_PASSWORD=pass -d mysql:5.5
```

`MYSQL_ROOT_PASSWORD` 的值必须为pass.这是由已经编译的renren-fast服务端决定的.

你可以自行修改该项目,编译后替换 renren-fast.jar.然后自行进行docker build.



## 创建数据库

按照 [renren-fast开发文档 ](https://www.renren.io/guide#end) 中的章节 `2.1 后端部署` 部署Mysql服务器,需要注意的是 ***数据库名与原文档有所改变***

- 创建数据库 **renren_test** ，数据库编码为 UTF-8
- 执行 doc/db.sql 文件，初始化数据（默认支持MySQL）



## 从Docker启动后端

```bash
docker run -d -p [暴露端口]:8080 --link=[mysql容器名]:renren-mysql --name="renren-server" ms0ng/renren-fast:test
```



## 测试

浏览器访问 `http://localhost:[暴露端口]/renren-fast/` ,若出现以下提示,则搭建成功

```html
{"msg":"invalid token","code":401}
```



之后,即可搭建前端并连接至后端