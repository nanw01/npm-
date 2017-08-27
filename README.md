# NPM Publish发布自己的模块

> NPM Publish发布自己的模块

### 下载使用

```tex
npm install npm_alex
```



### 1.编写模块

```javascript

exports.sayHello =function(){ 
	return 'Hello World'; 
} 

```



### 2.初始化包描述文件

```

## 指令
npm init

## 文件
package.json

{
  "name": "npm_alex",
  "version": "1.0.0",
  "description": "上传公用库",
  "main": "index.js",
  "scripts": {
    "test": "test"
  },
  "repository": {
    "type": "git",
    "url": "git+ssh://git@github.com/wanghaonanlpc/npm_alex.git"
  },
  "keywords": [
    "**********"
  ],
  "author": "alex",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/wanghaonanlpc/npm_alex/issues"
  },
  "homepage": "https://github.com/wanghaonanlpc/npm_alex#readme"
}

```



### 3.注册npm仓库账号



> [https://www.npmjs.com](https://www.npmjs.com/) 上面的账号 

```

$ npm adduser

Username: wanghaonan***
Password:
Email: (this IS public) 152****2733@163.com

```



### 4.上传模块

```

$ npm publish
+ npm_alex@1.0.0

```



### 5.安装包

```

$ npm install npm_alex

```



### 6.管理包权限

```
查看模块拥有者 
$ npm owner ls <package_name> 
添加一个发布者 
$ npm owner add <user> <package_name> 
删除一个发布者 
$ npm owner rm <user> <package_name>
```



### 7.分析包



```

# 查看当前项目引用了哪些包 
$ npm ls

```



### 8、使用引入包

```

var hello = require('alex'); 
hello.sayHello();

```





# 问题

　1.使用 cnpm 的注意报错：

```
no_perms Private mode enable, only admin can publish this module
```

　　设置回原本的就可以了：

```
npm config set registry http://registry.npmjs.org 
```

　　2.npm包package.json中registory属性一定要填写，每次publish npm时package.json中version版本一定要大于上一次。

 　  3.npm publish failed put 500  unexpected status code 401这样的报错信息，往往是没有登录成功，操作npm login
