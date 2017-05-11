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