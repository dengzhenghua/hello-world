#  ��ɫ����
[TOC]��
## 1. ��ɫ����
### 1.1 ��ɫ�б� 
| | |
| - | - |
| url | [/role/findRoleForPage](/role/findRoleForPage) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� | 
| - | - | - | - | - |
| userName | string | N | ��ѯ�ֶ� | 

#### ����ֵ

| name | type | ���� |
| :-: | :-: | :-: |
| page | string | ÿҳ�� |
| total | string | ��ҳ��|
| records | string | ������ |
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
					"description":"����1",
				},
				{
					"roleName":"cs",
					"description":"����",
				}
			]
		},
    "errorCode": null,
    "message": null
}
```
### 1.2 ��ȡȨ���б� 
| | |
| - | - |
| url | [/role/preparePermissionTree](/role/preparePermissionTree) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� | ȡֵ��Χ |
| - | - | - | - | - |
| roleId | Long | N | ��ɫID | ID |
| nodeid | Long | Y | Ȩ��ID | �״β��� |

#### ����ֵ

| name | type | ���� |
| :-: | :-: | :-: |
| id | Long | id |
| leaf | boolean | �Ƿ���Ҷ�� |
| parentId | Long | ����ID |

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
				"name": "��ҳ",
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
				"name": "��Ϣ����",
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
### 1.3 �жϽ�ɫ�Ƿ��ظ� 
| | |
| - | - |
| url | [/role/validateRoleName](/role/validateRoleName) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� | ȡֵ��Χ |
| - | - | - | - | - |
| roleName | String | Y | ��ɫ���� |  |
| roleId | Long | N | id | �����������޸���Ҫ�� |


#### ����ֵ

| name | type | ���� |
| :-: | :-: | :-: |
| data | boolean | true�����ڣ�false�Ѵ��� |

```javascript
{
    "success": true,
    "data": false,
    "errorCode": null,
    "message": null
}
```

### 1.4 ���� 
| | |
| - | - |
| url | [/role/addRole](/role/addRole) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� |
| - | - | - | - | - |
| addPermissionIds | String | N | ����Ȩ��ID |
| roleName | String | Y | ��ɫ�� |
| description | String | Y | ���� |

#### ����ֵ

| name | type | ���� |
| :-: | :-: | :-: |
| roleName | String | ��ɫ�� |
| description | String |���� |

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

### 1.5  �޸�

| | |
| - | - |
| url | [/role/updateRole](/role/updateRole) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� |
| - | - | - | - | - |
| id | Long | Y | id |
| addPermissionIds | String | N | ����Ȩ��ID |
| deletePermissionIds | String | N | ɾ��Ȩ��ID |
| roleName | String | Y | ��ɫ�� |
| description | String | Y | ���� |


#### ����ֵ�������ɹ�������ϢΪ�գ�ʧ�ܷ���������Ϣ��

| name | type | ���� |
| :-: | :-: | :-: |
| roleName | String |  ��ɫ�� |
| description | String |  ���� |

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

### 1.6 ���� 
| | |
| - | - |
| url | [/role/copyAddRole](/role/copyAddRole) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� |
| - | - | - | - | - |
| addPermissionIds | String | N | ����Ȩ��ID |
| deletePermissionIds | String | N | ɾ��Ȩ��ID |
| roleName | String | Y | ��ɫ�� |
| description | String | Y | ���� |


#### ����ֵ�������ɹ�������ϢΪ�գ�ʧ�ܷ���������Ϣ��

| name | type | ���� |
| :-: | :-: | :-: |
| roleName | String | ��ɫ�� |
| description | String | ���� |

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

### 1.7 ������ѯ 

| | |
| - | - |
| url | [/role/gotoEditPage](/role/gotoEditPage) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� |
| - | - | - | - | - |
| id |Long | Y | ��������ID��ѯ |


#### ����ֵ

| name | type | ���� |
| :-: | :-: | :-: |
| id | Long | ����ID |  
| roleName | String  | ��ɫ�� |
| description | String | ���� |
| roleId | Long  | ����id |
| permissionId | Long  | Ȩ��id |


```javascript
{
    "success": true,
    "data": {
        "role": {
            "id": 1,
            "roleName": "ϵͳ����Ա",
            "description": "ϵͳ����Ա",
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

### 1.7 ����ɾ�� 
| | |
| - | - |
| url | [/role/deleteRoleByIds](/role/deleteRoleByIds) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� |
| - | - | - | - | - |
| ids | List Long | Y | 


#### ����ֵ

| name | type | ���� |
| :-: | :-: | :-: |
| errorCode | string | ������� |
| expLevel | string | ����ȼ� |
| message | string | ������


```javascript
{
    "success": true,
    "data": "�����ɹ���",
    "errorCode": "",
    "message": ""
}
```

### 1.8 ����ɾ�� 
| | |
| - | - || url | [/role/deleteRoleById](/role/deleteRoleById) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� |
| - | - | - | - | - |
| id |Long | Y | id |


#### ����ֵ

| name | type | ���� |
| :-: | :-: | :-: |
success | boolean | �ɹ����
errorCode | string | �������
message | string | ������Ϣ

```javascript
{
    "success":true,
    "data":null,
    "errorCode":null,
    "message":""
}
```

### 1.9  �鿴
| | |
| - | - |
| url | [/role/gotoViewPage](/role/gotoViewPage) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� |
| - | - | - | - | - |
| id | Long | Y | ����ID |


#### ����ֵ

| name | type | ���� |
| :-: | :-: | :-: |
| roleName | String | ��ɫ�� |
| description | String | ���� |


```javascript
{
    "success": true,
    "data": {
        "id": 1,
        "createUser": "admin",
        "createDate": "2016-12-06 09:22:00",
        "updateUser": "admin",
        "updateDate": "2016-12-06 09:22:00",
        "roleName": "ϵͳ����Ա",
        "description": "ϵͳ����Ա",
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

#### ����

| name | type | mandatory | ���� |
| - | - | - | - | - |
| id | Long | Y | ����ID |


#### ����ֵ

| name | type | ���� |
| :-: | :-: | :-: |
| id | Long | ����ID |  
| userName | string | �û����� |
| name | string | �û����� |
| password | String  | ����  |
| mobile | String | �绰 | 
| administrator | boolean  | �Ƿ����Ա | 
| roleIdList | String  | ��ɫid | 


```javascript
{
    "success": true,
    "data": {
        "page": 1,
        "rows": 15,
        "adminUser": {
            "id": 1,
            "userName": "admin",
            "name": "����Ա",
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