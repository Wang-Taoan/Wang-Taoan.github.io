# 接口


## 参数类型

- url参数(默认)
	- `xxx?id=1&name=11`
	- 参数前写 `@Requestparam`
	- 一般使用场景：多条件查询、分页查询
- 路径参数
	- `xxx/1`
	- `@DeleteMapping("/delete/{id}")` 
	- 参数前写 `@PathVariable`
	- 一般使用场景：Delete
- JSON数据
	- JSON键值对
	- 参数前写  `@RequestBody`
	- 一般使用场景：Post、Put


## 写接口的逻辑

顺序：C->S->M->D

- Controller
- Service
- Mapper
- Domain

[![](https://pic.imgdb.cn/item/6565da98c458853aef13cdcd.jpg)](https://pic.imgdb.cn/item/6565da98c458853aef13cdcd.jpg)

