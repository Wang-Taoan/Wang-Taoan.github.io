# ruoyi notes

## Learning Rources

<https://doc.ruoyi.vip/ruoyi-vue/>

## 目录结构

核心业务CRUD：

- admin-Controller层+springboot核心启动类
- system-SMD层

一般不需要更改和专注的目录：

- common-工具类（注解、异常、JSON处理、XSS过滤）
- framework-框架核心（注解、拦截器、权限）
- generator-代码生成
- quartz-定时任务


## 【生成代码】使用指南

- 数据库建表
- 生成代码->导入表
- 编辑相关数据
- 生成ZIP包，将前后端文件放到对应ruoyi项目下，运行生成的SQL文件

值得注意的是

- 生成模板：单表（其他暂时没用过）
- 生成功能名：就是会出现在菜单位置的名字

## 【去除权限访问限制】


`SecurityConfig.java`

```
.antMatchers("/mall/user/**").permitAll() // permitAll()所有人都可以访问
.antMatchers("/mall/user/**").anonymous() // .anonymous() 所有匿名的人都可以访问，如果带上token了就会报错
```

同时还要去掉Controller层的`@PreAuthorize`的所有注释

## 【修改默认样式】

ruoyi样式修改参考：<https://www.cnblogs.com/fzux/p/17181081.html>


## 【403Error】接口错误

这是因为屏蔽措施没有做好，也就是去掉权限访问只做了第一步`.antMatchers`，没有去掉Controller层上的方法注释`@PreAuthorize`


## 【部署】部署ruoyi到服务器


准备工作：

- 本地：
	- 购买一台云服务器
	- 本地下载 X-shell和Xftp（连接工具）
	- 打包前后端程序
- 服务器端：
	- 安装并启动jdk、nginx、mysql、redis
	- 部署后端java，一些脚本、配置文件、权限设置
	- 部署前端
	- 配置nginx、mysql数据库
	- 云服务器防火墙开放80（这个80对应的是nginx配置文件里写的80接口）、3306端口（这个mysql的端口，方便远程可以navicat连接到远程服务器的数据库）

代码位于`/home/ruoyi-vue`

启动后端

```bash
cd /home/ruoyi-vue/java
# 启动 ./ry.sh start
# 关闭 ./ry.sh stop
# 查看状态 ./ry.sh status
```

开启前端

```
# 打开配置文件 vi /usr/local/nginx/conf/nginx.conf
# 修改nginx配置文件 可以参考官网 
开启nginx
```

