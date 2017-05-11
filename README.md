# API 文档中心

## 移动端项目

- [数据采集](http://gitlab.hztianque.com/docs/api-docs/tree/master/%E6%95%B0%E6%8D%AE%E9%87%87%E9%9B%86)

## 接口文档模版

[复制模版](http://gitlab.hztianque.com/docs/api-docs/raw/master/%E6%95%B0%E6%8D%AE%E9%87%87%E9%9B%86/example.md)

# 获取图书列表

| | |
| - | - |
| url | [https://~/v1/book](https://~/v1/books) | 
| method | GET | 

#### 参数

| name | type | mandatory | 描述 | 取值范围 |
| - | - | - | - | - |
| page | number | N | 当前面码 | - |
| id | string | Y | 书的编号 | - |

### 返回值

```javascript
{
  "success": true,
  "errCode": "xxx-xxx",
  "message": "",
  "data": null
}
```