# Vue2 Notes

## Learning Resources

Vue2：<https://v2.cn.vuejs.org/>

风格指南：<https://v2.cn.vuejs.org/v2/style-guide/>

## 指令


1. `v-html` 解析HTML标签 相关
2. `v-show` 显示隐藏（频繁需要显示、隐藏的时候用）
3. `v-if-else`  
4. `v-on` （@）事件相关
5. `v-for` 
6. `v-model` 表单相关
7. `v-bind` 地址、样式相关
	1. `:src` `:class`


## 选项

1. `data`
2. `props`
3. `computed`
4. `methods`
5. `watch`

## 生命周期钩子

1. `created`
2. `mounted`
3. `destroyed`
## Vuex

Vuex：管理vue通用数据

1. `state`
2. `mutations`提供修改数据的方法
3. `actions`处理异步，调用接口
4. `getters`类似于计算属性

## 全局文件main.js 

用来挂载一些全局的东西，比如store、router、Vue

## 模块化

1. 解决样式冲突 scoped
2. 父子通信
3. **插槽** (slots) 将模板片段传递给子组件。插口中的内容将被当作“默认”内容：它会在父组件没有传递任何插槽内容时显示：
4. 路由传参、路由嵌套、router-link、router-view、重定向redirect


1. 父子通信
2. slots
3. 路由
	- 查询参数传参：` ？参数=参数值`
	- 动态路由传参：`路径 /参数`