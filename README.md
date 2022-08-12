# 原项目地址：https://github.com/fancyyawn/blog-hbs-cloud-microservice-multi-db
# blog-hbs-cloud-microservice-multi-db
> 基于SpringCloud的微服务化多人博客，每个服务可根据业务需要使用的不同的数据库。

* blog-common： 提供Paging得公共类
* blog-discovery：基于Eureka提供服务注册和发现功能
* blog-hbs-web：整个博客应用的gateway，对外提供页面， 其利用各微服务模块的api来提供数据和操作。
* blog-service-user：用户服务，在内网环境中提供rest api， 数据库为mysql(blog-microservice)
* blog-service-post：博客服务，在内网环境中提供rest api，数据库为mongodb（blog-microservice）
* blog-service-comment: 评价服务，在内网环境中提供rest api，数据库为mongodb（blog-microservice）

>mysql

    docker run -itd --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=123 mysql:8.0.29

    [root@master ~]# docker exec -it mysql bash
    
    bash-4.4# mysql -p123
    
    mysql> create database `blog-microservice`;
    
    mysql> use mysql;
    
    mysql> select host,user from user;
    
    mysql> ALTER USER 'root'@'%' IDENTIFIED WITH mysql_native_password BY '123';
    
    mysql> flush privileges;

