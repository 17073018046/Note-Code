```
proxyTable: {
      '/api': {
        target: 'http://39.96.77.168:8082/',  //目标接口域名
        changeOrigin: true,  //是否跨域
        pathRewrite: {
          '^/api': ''
      }
      },
    },
```

打包后使用nginx配置

```
server {
        listen       443;  //监听的端口
        server_name  localhost;

        #charset koi8-r;

        #access_log  logs/host.access.log  main;

     
		
		location ^~  {
		     root G:/early-education/sgsd-early-web/dist; //找到index页面
			 
			 try_files $uri $uri/ index.html;
        }
	
	
		location /api/ {    //转发请求
           proxy_pass http://39.96.77.168:8082/;
        }
		
```