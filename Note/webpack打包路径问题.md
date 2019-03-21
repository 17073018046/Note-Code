## webpack打包路径

1、页面和css中引用的图片，都放在assets中就可以，该文件夹的内容最终会被打包到static下,而开发环境时的static文件夹下的内容会按原来的结构打包到dist的static文件夹下，assets中没有被引用的文件不会被打包。
```
//css中的路径：
background: url("../assets/loginBg.jpg");

打包后的路径：
background: url("/static/img/loginBg.jpg");

//在utils.js中添加：
publicPath:"../../";

//打包后路径变为：
background: url("../../static/img/loginBg.jpg");
//就能找到正确的图片地址
```

### 2、config中index.js配置
- assetsSubDirectory：资源子目录，指js,css，img存放的目录，其路径相对于index.html
- assetsPublicPath：资源目录，默认是这样配置的assetsPublicPath: '/'，指assetsSubDirectory目录也就是js,css,img等资源相对于服务器host地址，传说中的绝对路径