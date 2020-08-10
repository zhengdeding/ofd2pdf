# ofd2pdf

## apk介绍

本apk为ofd转pdf的demo，实现读取本地的ofd文件转换为pdf并展现，其中转ofd为离线sdk

## 服务接口介绍

host: donal-tong.ticp.io
port: 80

### OFD发票转PDF

URL：http://host:port/api/v1/ts/ofd/ofdConvertPdf

请求方式：POST

报文格式：Content-Type: application/json

请求参数：

| 参数        | 说明                                                         | 类型    | 是否必填 |
| ----------- | ------------------------------------------------------------ | ------- | -------- |
| ofdBase64   | 待转换的OFD发票版式文件，BASE64编码的字符串                  | String  | 是       |


请求参数示例：

```json
{
    "ofdBase64":"{{ofdBase64}}",
}
```

返回数据：

| 数据    | 说明                                                   |
| ------- | ------------------------------------------------------ |
| code    | 返回码。"0"表示成功，其余表示失败，失败原因参考message |
| message | 请求结果信息                                           |
| data    | 转后的pdf文件，BASE64编码的字符串            |

返回数据示例：

```json
{
	"code": "0",
	"data": "xxx",
	"message": "成功"
}
```

### OFD发票转图片

URL：http://host:port/api/v1/ts/ofd/ofdConvertImage

请求方式：POST

报文格式：Content-Type: application/json

请求参数：

| 参数        | 说明                                                         | 类型    | 是否必填 |
| ----------- | ------------------------------------------------------------ | ------- | -------- |
| ofdBase64   | 待转换的OFD发票版式文件，BASE64编码的字符串                  | String  | 是       |


请求参数示例：

```json
{
    "ofdBase64":"{{ofdBase64}}",
}
```

返回数据：

| 数据    | 说明                                                   |
| ------- | ------------------------------------------------------ |
| code    | 返回码。"0"表示成功，其余表示失败，失败原因参考message |
| message | 请求结果信息                                           |
| data    | 转后的图片文件列表，BASE64编码的字符串            |

返回数据示例：

```json
{
	"code": "0",
	"data": "xxx",
	"message": "成功"
}
```