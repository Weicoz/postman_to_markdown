## config 配置文件说明
1. **host**：默认替换原接口 {{host}} 参数内容
2. **parame**：返回参数说明中参数注释，其中参数类型与说明使用 | 分隔，不使用 | 则默认 string 类型，例如：name: "string|名称"
3. **module**：判断开启的模块，模块包含 description，url，method，header，query，body，result，explan，设置为false则对应内容为空，例如：description: false
4. **ignoreQuery**：需要全局忽略query的参数，对应query输出的参数中则忽略该参数，例如："m": true，
5. **ignoreBody**：需要全局忽略body的参数，对应body输出的参数中则忽略该参数，例如："errcode": true，
6. **api**：对应 postman 中接口名称相同的接口，注释为其返回参数的注释