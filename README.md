## PHP-LAB
方便测试同一套代码在不同PHP 版本下运行的不一致性 


## Usage 
PHP 放在 code 文件夹下即可

```sh 
docker-compose up --build --remove-orphans  
```

- http://localhost:8180 PHP 7.4.0
- http://localhost:8181 PHP 7.4.30


## 运行原理 
启动多个不同版本的php-fpm 镜像，通过 nginx 监听不同的端口，转发请求给不同版本的php-fpm , 宿主机、nginx、多个不同版本的php-fpm 通过目录映射共享同一套PHP源码
