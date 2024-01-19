# uniapp notes

## 参考

<https://zh.uniapp.dcloud.io/>


## 开发工具

- HBuilderX
- uni-ui


## 目录结构

```
┌─uniCloud              云空间目录，支付宝小程序云为uniCloud-alipay，阿里云为uniCloud-aliyun，腾讯云为uniCloud-tcb（详见uniCloud）
│─components            符合vue组件规范的uni-app组件目录
│  └─comp-a.vue         可复用的a组件
├─pages                 业务页面文件存放的目录
│  ├─index
│  │  └─index.vue       index页面
│  └─list
│     └─list.vue        list页面
├─static                存放应用引用的本地静态资源（如图片、视频等）的目录，注意：静态资源都应存放于此目录
├─uni_modules           存放uni_module 详见
├─hybrid                App端存放本地html文件的目录，详见
├─wxcomponents          存放小程序组件的目录，详见
├─main.js               Vue初始化入口文件
├─App.vue               应用配置，用来配置App全局样式以及监听 应用生命周期
├─pages.json            配置页面路由、导航条、选项卡等页面类信息，详见
├─manifest.json         配置应用名称、appid、logo、版本等打包信息，详见
└─uni.scss              内置的常用样式变量
```

## 与H5的差异

- 介绍uniapp和平常的h5、vue开发的不同点

1. [easycom](https://uniapp.dcloud.net.cn/collocation/pages?id=easycom)不再需要导入、注册组件。可以直接使用
2. html标签和uni-app内置组件一一进行了映射。e.g.`div->view`
3. 新增了一批手机端常用新组件
4. uni-app的api是参考小程序的，所以和浏览器的js api有很多不同
5. 标准的css基本都是支持的。选择器有2个变化：*选择器不支持；元素选择器里没有body，改为了page。
6. 单位方面，px无法动态适应不同宽度的屏幕，rem无法用于nvue/weex。如果想使用根据屏幕宽度自适应的单位，推荐使用rpx，全端支持。
7. 工程结构和页面管理：每个可显示的页面，都必须在 [pages.json](https://uniapp.dcloud.io/collocation/pages) 中注册。app和小程序中，为了提升体验，页面提供了原生的导航栏和底部tabbar，注意这些配置是在pages.json中做，


