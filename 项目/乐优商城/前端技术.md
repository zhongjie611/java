## 解决400 QS工具

 乐优商城第八天 品牌新增

问题原因

​	axios处理请求体的原则会根据请求数据的格式来定：

- 如果请求体是对象：会转为json发送

- 如果请求体是String：会作为普通表单请求发送，但需要我们自己保证String的格式是键值对。

  如：name=jack&age=12

QS工具QS，即Query String，请求参数字符串。

什么是请求参数字符串？例如： <u>*name=jack&age=21*</u>

QS工具可以便捷的实现 JS的Object与QueryString的转换。

### 编写校验

乐优商城第八天 品牌新增