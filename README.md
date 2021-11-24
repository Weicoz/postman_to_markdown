# Postman 接口转换为 markdown 接口文档

- 对应 postman 导出接口2.1版本

## 使用说明
1. 确保 postman 中需要导出所有接口保存过接口结果并且为json格式`Save Response->Save as example`。
2. 选择需要的接口导出`Export`到`json`目录中。
3. 新建一份`.json`文件与刚刚导出的文件名相同的文件到`config`中，并进行配置。
4. 执行`postman_to_markdown.py`

## 注意事项
- 接口请求参数的注释需要在 postman 接口中对应参数的 `Description` 中进行配置，配置格式为：`参数类型|是否必填|参数说明`，例如：`price`参数->`float|是|金额`

## 目录说明
1. config 配置目录，保存一份与 json 同名的 .json 文件用于配置参数。
2. json postman json目录，存放 Postman 导出的 json 文件。
3. markdown 输出目录，接口文档内容
4. template 模板目录，存放接口文档模板

### config 配置文件说明
1. host：默认替换原接口 `{{host}}` 参数内容
2. parame：返回参数说明中参数注释，其中参数类型与说明使用 | 分隔，不使用 | 则默认 `string` 类型，例如：`name: "string|名称"`
3. module：判断开启的模块，模块包含 description，url，method，header，query，body，result，explan，设置为`false`则对应内容为空，例如：`description: false`
4. ignoreQuery：需要全局忽略`query`的参数，对应`query`输出的参数中则忽略该参数，例如：`"m": true`，
5. ignoreBody：需要全局忽略`body`的参数，对应`body`输出的参数中则忽略该参数，例如：`"errcode": true`，
6. api：对应 postman 中接口名称相同的接口，注释为其返回参数的注释