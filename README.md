## PHP-LAB
方便测试同一套PHP代码在不同PHP 版本下运行的不一致性 


## 使用方法
PHP代码放在 code 文件夹下即可

```sh 
docker-compose up --build --remove-orphans  
```
|宿主机port| 容器内port | php-fpm | libcurl |
| ---- | ---- |---- | ---- | 
| 8183 | 83 | 7.0.0 | 7.38.0 | 
| 8186 | 86 | 7.0.19 | 7.52.1 | 
| 8188 | 88 | 7.0.24 | 7.55.0 |
| 8187 | 87 | 7.0.29 | 7.59.0 | 
| 8185 | 85 | 7.0.33 | 7.61.1 |
| 8184 | 84 | 7.1.23 | 7.61.1 | 
| 8180 | 80 | 7.4.0 | 7.64.0  |
| 8189 | 89 | 7.4.21 | 7.77.0 |
| 8181 | 81 | 7.4.30 | 7.80.0 |
| 8182 | 82 | 8.0.24 | 7.83.1 |


注意php-fpm版本和其所使用的libcurl版本没有必然的对应关系，以上对应关系只是所使用镜像中的对应关系





## 运行原理 
启动多个不同版本的php-fpm 镜像，通过 nginx 监听不同的端口，转发请求给不同版本的php-fpm , 宿主机、nginx、多个不同版本的php-fpm 通过目录映射共享同一套PHP源码

## QQ 交流群
<img src="https://store.heytapimage.com/cdo-portal/feedback/202301/04/ed1d5ac9f0c48af0a154037fb892024f.png" height="250px" width="250px" alt="图片.png" title="图片.png" referrerPolicy="no-referrer" />
