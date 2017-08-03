#  用户管理
[TOC]仇凯
## 1. 用户管理
### 1.1 用户列表 
| | |
| - | - |
| url | [/user/findAdminUserList](/user/findAdminUserList) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 
| - | - | - | - | - |
| userName | string | N | 查询字段 | 

#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| page | string | 每页数 |
| total | string | 总页数|
| records | string | 总条数 |
| rows | object |  |

```javascript
{
    "success": true,
    "data": {
        "page": 1,
        "total": 1,
        "records": 14,
        "rows": [
            {
                "id": 1,
                "userName": "admin",
                "name": "管理员",
                "password": "1bbd886460827015e5d605ed44252251",
                "mobile": "13111111111",
                "administrator": true,
                "userRoleName": null
            },
            {
                "id": 21,
                "userName": "cs",
                "name": "测试",
                "password": "1bbd886460827015e5d605ed44252251",
                "mobile": "13332211122",
                "administrator": true,
                "userRoleName": "cs"
            }
        ]
    },
    "errorCode": null,
    "message": null
}
```
### 1.2 新增 
| | |
| - | - |
| url | [/user/addAdminUser](/user/addAdminUser) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 取值范围 |
| - | - | - | - | - |
| userName | string | Y | 用户名 | 汉字、字母、数字允许输入20个字符 |
| name | string | Y| 用户姓名 | 由汉字、字母、数字允许输入20个字符 |
| password | String | Y | 密码   | 由字母、数字允许输入24个字符 |
| confirmPwd | String | Y | 确认密码  | 由字母、数字允许输入24个字符 |
| mobile | String | Y | 手机 | 数字组成，允许输入11个数字 |
| administrator | Boolean | Y | 系统管理员 |  |
| roleIdList | string | N | 角色id |


#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| id | Long | 新增数据ID |
| userName | string | Y | 用户名 | 汉字、字母、数字允许输入20个字符 |
| name | string | Y| 用户姓名 | 由汉字、字母、数字允许输入20个字符 |
| password | String | Y | 密码   | 由字母、数字允许输入24个字符 |
| confirmPwd | String | Y | 确认密码  | 由字母、数字允许输入24个字符 |
| mobile | String | Y | 手机 | 数字组成，允许输入11个数字 |
| administrator | Boolean | Y | 系统管理员 |  |

```javascript
{
    "success": true,
    "data":{
		"id": 21,
		"createDate": "2017-07-24 14:52:59",
		"userName": "cs",
		"name": "测试",
		"password": "1bbd886460827015e5d605ed44252251",
		"mobile": "13332211122",
		"administrator": true
	},
    "errorCode": "null",
    "message": null
}
```
### 1.3 修改 

| | |
| - | - |
| url | [/user/updateAdminUser](/user/updateAdminUser) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 取值范围 |
| - | - | - | - | - |
| id | Long | Y | 修改数据ID |  |
| userName | string | Y | 用户名 | 汉字、字母、数字允许输入20个字符 |
| name | string | Y| 用户姓名 | 由汉字、字母、数字允许输入20个字符 |
| password | String | Y | 密码   | 由字母、数字允许输入24个字符 |
| confirmPwd | String | Y | 确认密码  | 由字母、数字允许输入24个字符 |
| mobile | String | Y | 手机 | 数字组成，允许输入11个数字 |
| administrator | Boolean | Y | 系统管理员 |  |
| roleIdList | string | N | 角色id |


#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| id | Long | 新增数据ID |
| userName | string | Y | 用户名 | 汉字、字母、数字允许输入20个字符 |
| name | string | Y| 用户姓名 | 由汉字、字母、数字允许输入20个字符 |
| password | String | Y | 密码   | 由字母、数字允许输入24个字符 |
| confirmPwd | String | Y | 确认密码  | 由字母、数字允许输入24个字符 |
| mobile | String | Y | 手机 | 数字组成，允许输入11个数字 |
| administrator | Boolean | Y | 系统管理员 |  |

```javascript
{
    "success": true,
    "data":{
		"id": 21,
		"createDate": "2017-07-24 14:52:59",
		"userName": "cs11",
		"name": "测试11",
		"password": "1bbd886460827015e5d605ed44252251",
		"mobile": "133322111211",
		"administrator": true
	},
    "errorCode": "null",
    "message": null
}
```

### 1.4 验证用户名是否存在 
| | |
| - | - |
| url | [/user/validateAdminUserName](/user/validateAdminUserName) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 |
| - | - | - | - | - |
| id | Long | N | 新增不用传，修改需要传 |
| userName | String | Y | 用户名 |


#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| data | boolean | false存在，true不存在 |  


```javascript
{
    "success": true,
    "data": false,
    "errorCode": null,
    "message": null
}
```

### 1.5 获取角色列表 
| | |
| - | - |
| url | [/role/getRoleList](/role/getRoleList) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 |
| - | - | - | - | - |


#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| id | Long | id |  
| roleName | String | 角色名称 |  
| description | String | 描述 |  


```javascript
{
    "success": true,
    "data": {
        "page": 1,
        "total": 1,
        "records": 2,
        "rows": [
            {
                "id": 1,
                "roleName": "系统管理员",
                "description": "系统管理员",
            },
            {
                "id": 2,
                "roleName": "cs",
                "description": "cs"
            }
        ]
    },
    "errorCode": null,
    "message": null
}
```

### 1.6 多条数据删除 

| | |
| - | - |
| url | [/user/deleteAdminUsers](/user/deleteAdminUsers) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 |
| - | - | - | - | - |
| ids | List Long | Y | id |


#### 返回值（操作成功返回信息为空，失败返回以下信息）

| name | type | 描述 |
| :-: | :-: | :-: |
| errorCode | string | 错误编码 |
| expLevel | string | 错误等级 |
| message | string | 错误信息 |


```javascript
{
    "success": true,
    "data": "操作成功！",
    "errorCode": "",
    "message": ""
}
```

### 1.7 单条数据删除 

| | |
| - | - |
| url | [/user/deleteAdminUserById](/user/deleteAdminUserById) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 |
| - | - | - | - | - |
| id |Long | Y | id |


#### 返回值（操作成功返回信息为空，失败返回以下信息）

| name | type | 描述 |
| :-: | :-: | :-: |
success | boolean | 成功与否
errorCode | string | 错误编码
message | string | 错误信息

```javascript
{
    "success":true,
    "data":null,
    "errorCode":null,
    "message":""
}
```

### 1.8 单条查询 

| | |
| - | - |
| url | [/user/gotoEditPage](/user/gotoEditPage) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 |
| - | - | - | - | - |
| id |Long | Y | 更具数据ID查询 |


#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| id | Long | 数据ID |  
| userName | string | 用户名称 |
| name | string | 用户名称 |
| password | String  | 密码  |
| mobile | String | 电话 | 
| administrator | boolean  | 是否管理员 | 
| roleIdList | String | 角色id | 


```javascript
{
    "success": true,
    "data": {
        "page": 1,
        "rows": 15,
        "adminUser": {
            "id": 1,
            "userName": "admin",
            "name": "管理员",
            "password": "1bbd886460827015e5d605ed44252251",
            "mobile": "13111111111",
            "administrator": true
        },
        "roleIdList": "1"
    },
    "errorCode": null,
    "message": null
}
```

### 1.9 重置密码 

| | |
| - | - |
| url | [/user/updateAdminUser](/user/updateAdminUser) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 |
| - | - | - | - | - |
| id | Long | Y | 数据ID |
| password | String  | 密码  |


#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| id | Long | 数据ID |  
| userName | string | 用户名称 |
| name | string | 用户名称 |
| password | String  | 密码  |
| mobile | String | 电话 | 
| administrator | boolean  | 是否管理员 | 


```javascript
{
    "success": true,
    "data": {
        "id": 4,
        "userName": "byj",
        "name": "管理员",
        "password": "1bbd886460827015e5d605ed44252251",
        "mobile": "13111111111",
        "administrator": true,
    },
    "errorCode": null,
    "message": null
}
```

### 1.10 查看 
| | |
| - | - |
| url | [/user/gotoViewPage](/user/gotoViewPage) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 |
| - | - | - | - | - |
| id | Long | Y | 数据ID |


#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| id | Long | 数据ID |  
| userName | string | 用户名称 |
| name | string | 用户名称 |
| password | String  | 密码  |
| mobile | String | 电话 | 
| administrator | boolean  | 是否管理员 | 
| roleIdList | String  | 角色id | 


```javascript
{
    "success": true,
    "data": {
        "page": 1,
        "rows": 15,
        "adminUser": {
            "id": 1,
            "userName": "admin",
            "name": "管理员",
            "password": "1bbd886460827015e5d605ed44252251",
            "mobile": "13111111111",
            "administrator": true
        },
        "roleIdList": "1,2"
    },
    "errorCode": null,
    "message": null
}
```

### 1.11 查看时获取角色 
| | |
| - | - |
| url | [/role/getAdminUserRoleList](/role/getAdminUserRoleList) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 |
| - | - | - | - | - |
| roleIdList | String | Y | 角色ID |


#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| id | Long | 数据ID |  
| roleName | String | 角色名 |
| description | String |描述 |


```javascript
{
    "success": true,
    "data": {
        "page": 1,
        "total": 1,
        "records": 2,
        "rows": [
            {
                "id": 1,
                "roleName": "系统管理员",
                "description": "系统管理员",
            },
            {
                "id": 2,
                "roleName": "cs",
                "description": "cs",
            }
        ]
    },
    "errorCode": null,
    "message": null
}
```