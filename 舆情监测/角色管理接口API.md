#  角色管理
[TOC]仇凯
## 1. 角色管理
### 1.1 角色列表 
| | |
| - | - |
| url | [/role/findRoleForPage](/role/findRoleForPage) | 
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
			"records": 1,
			"rows": [
				{
					"roleName":"cs1",
					"description":"描述1",
				},
				{
					"roleName":"cs",
					"description":"描述",
				}
			]
		},
    "errorCode": null,
    "message": null
}
```
### 1.2 获取权限列表 
| | |
| - | - |
| url | [/role/preparePermissionTree](/role/preparePermissionTree) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 取值范围 |
| - | - | - | - | - |
| roleId | Long | N | 角色ID | ID |
| nodeid | Long | Y | 权限ID | 首次不传 |

#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| id | Long | id |
| leaf | boolean | 是否有叶级 |
| parentId | Long | 父级ID |

```javascript
{
    "success": true,
    "data":{
		"page": 1,
		"records": 3,
		"rows": [
			{
				"checked": true,
				"id": 3,
				"isParent": false,
				"leaf": true,
				"level": 3,
				"name": "首页",
				"open": false,
				"parentId": 2,
				"permissionType": 1
			},
			{
				"checked": false,
				"id": 5,
				"isParent": false,
				"leaf": false,
				"level": 3,
				"name": "消息中心",
				"open": false,
				"parentId": 2,
				"permissionType": 1
			}
		],
		"total": 1
	},
    "errorCode": "null",
    "message": null
}
```
### 1.3 判断角色是否重复 
| | |
| - | - |
| url | [/role/validateRoleName](/role/validateRoleName) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 取值范围 |
| - | - | - | - | - |
| roleName | String | Y | 角色名称 |  |
| roleId | Long | N | id | 新增不传，修改需要传 |


#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| data | boolean | true不存在，false已存在 |

```javascript
{
    "success": true,
    "data": false,
    "errorCode": null,
    "message": null
}
```

### 1.4 新增 
| | |
| - | - |
| url | [/role/addRole](/role/addRole) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 |
| - | - | - | - | - |
| addPermissionIds | String | N | 新增权限ID |
| roleName | String | Y | 角色名 |
| description | String | Y | 描述 |

#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| roleName | String | 角色名 |
| description | String |描述 |

```javascript
{
    "success": true,
    "data": {
		"createDate": "2017-07-25 15:05:28",
		"createUser": "admin",
		"description": "cs",
		"id": 5,
		"roleName": "cs",
		"updateDate": "2017-07-25 15:05:28",
		"updateUser": "admin"
	},
    "errorCode": null,
    "message": null
}
```

### 1.5  修改

| | |
| - | - |
| url | [/role/updateRole](/role/updateRole) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 |
| - | - | - | - | - |
| id | Long | Y | id |
| addPermissionIds | String | N | 新增权限ID |
| deletePermissionIds | String | N | 删除权限ID |
| roleName | String | Y | 角色名 |
| description | String | Y | 描述 |


#### 返回值（操作成功返回信息为空，失败返回以下信息）

| name | type | 描述 |
| :-: | :-: | :-: |
| roleName | String |  角色名 |
| description | String |  描述 |

```javascript
{
    "success": true,
    "data": {
		"createDate": "2017-07-25 15:05:24",
		"createUser": "admin",
		"description": "cs11",
		"id": 5,
		"roleName": "cs11",
		"updateDate": "2017-07-25 15:44:32",
		"updateUser": "admin"
	},
    "errorCode": null,
    "message": null
}
```

### 1.6 复制 
| | |
| - | - |
| url | [/role/copyAddRole](/role/copyAddRole) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 |
| - | - | - | - | - |
| addPermissionIds | String | N | 新增权限ID |
| deletePermissionIds | String | N | 删除权限ID |
| roleName | String | Y | 角色名 |
| description | String | Y | 描述 |


#### 返回值（操作成功返回信息为空，失败返回以下信息）

| name | type | 描述 |
| :-: | :-: | :-: |
| roleName | String | 角色名 |
| description | String | 描述 |

```javascript
{
    "success": true,
    "data": {
		"createDate": "2017-07-25 15:05:24",
		"createUser": "admin",
		"description": "cs11",
		"id": 5,
		"roleName": "cs11",
		"updateDate": "2017-07-25 15:44:32",
		"updateUser": "admin"
	},
    "errorCode": null,
    "message": null
}
```

### 1.7 单条查询 

| | |
| - | - |
| url | [/role/gotoEditPage](/role/gotoEditPage) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 |
| - | - | - | - | - |
| id |Long | Y | 更具数据ID查询 |


#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| id | Long | 数据ID |  
| roleName | String  | 角色名 |
| description | String | 描述 |
| roleId | Long  | 数据id |
| permissionId | Long  | 权限id |


```javascript
{
    "success": true,
    "data": {
        "role": {
            "id": 1,
            "roleName": "系统管理员",
            "description": "系统管理员",
        },
        "permissionList": [
            {
                "roleId": 1,
                "permissionId": 1
            },
            {
                "roleId": 1,
                "permissionId": 2
            }
        ]
    },
    "errorCode": null,
    "message": null
}
```

### 1.7 多条删除 
| | |
| - | - |
| url | [/role/deleteRoleByIds](/role/deleteRoleByIds) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 |
| - | - | - | - | - |
| ids | List Long | Y | 


#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| errorCode | string | 错误编码 |
| expLevel | string | 错误等级 |
| message | string | 错误信


```javascript
{
    "success": true,
    "data": "操作成功！",
    "errorCode": "",
    "message": ""
}
```

### 1.8 单条删除 
| | |
| - | - || url | [/role/deleteRoleById](/role/deleteRoleById) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 |
| - | - | - | - | - |
| id |Long | Y | id |


#### 返回值

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

### 1.9  查看
| | |
| - | - |
| url | [/role/gotoViewPage](/role/gotoViewPage) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 |
| - | - | - | - | - |
| id | Long | Y | 数据ID |


#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| roleName | String | 角色名 |
| description | String | 描述 |


```javascript
{
    "success": true,
    "data": {
        "id": 1,
        "createUser": "admin",
        "createDate": "2016-12-06 09:22:00",
        "updateUser": "admin",
        "updateDate": "2016-12-06 09:22:00",
        "roleName": "系统管理员",
        "description": "系统管理员",
    },
    "errorCode": null,
    "message": null
}
```

### 1.9  
| | |
| - | - |
| url | [/role/getAdminUserRoleList](/role/getAdminUserRoleList) | 
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