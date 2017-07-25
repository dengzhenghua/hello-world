#  �û�����
[TOC]��
## 1. �û�����
### 1.1 �û��б� 
| | |
| - | - |
| url | [/user/findAdminUserList](/user/findAdminUserList) | 
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
			"page": 0,
			"total": 0,
			"records": 0,
			"rows": [
				{
					"page": 1,
					"rows": 15,
					"adminUser": {
						"id": 11,
						"userName": "admin3",
						"name": "����Ա",
						"password": "1bbd886460827015e5d605ed44252251",
						"mobile": "13111111111",
						"administrator": true,
						"roleIdList": null
					},
					"roleIdList": null,
					"userRoleName": null
				},
				{
					"page": 1,
					"rows": 15,
					"adminUser": {
						"id": 10,
						"userName": "admin2",
						"name": "����Ա",
						"password": "1bbd886460827015e5d605ed44252251",
						"mobile": "13111111111",
						"administrator": true,
						"roleIdList": null
					},
					"roleIdList": null,
					"userRoleName": null
				}
			]
		},
    "errorCode": null,
    "message": null
}
```
### 1.2 ���� 
| | |
| - | - |
| url | [/user/addAdminUser](/user/addAdminUser) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� | ȡֵ��Χ |
| - | - | - | - | - |
| userName | string | Y | �û��� | ���֡���ĸ��������������20���ַ� |
| name | string | Y| �û����� | �ɺ��֡���ĸ��������������20���ַ� |
| password | String | Y | ����   | ����ĸ��������������24���ַ� |
| confirmPwd | String | Y | ȷ������  | ����ĸ��������������24���ַ� |
| mobile | String | Y | �ֻ� | ������ɣ���������11������ |
| administrator | Boolean | Y | ϵͳ����Ա |  |
| roleIdList | string | N | ��ɫid |


#### ����ֵ

| name | type | ���� |
| :-: | :-: | :-: |
| id | Long | ��������ID |
| userName | string | Y | �û��� | ���֡���ĸ��������������20���ַ� |
| name | string | Y| �û����� | �ɺ��֡���ĸ��������������20���ַ� |
| password | String | Y | ����   | ����ĸ��������������24���ַ� |
| confirmPwd | String | Y | ȷ������  | ����ĸ��������������24���ַ� |
| mobile | String | Y | �ֻ� | ������ɣ���������11������ |
| administrator | Boolean | Y | ϵͳ����Ա |  |

```javascript
{
    "success": true,
    "data":{
		"id": 21,
		"createDate": "2017-07-24 14:52:59",
		"userName": "cs",
		"name": "����",
		"password": "1bbd886460827015e5d605ed44252251",
		"mobile": "13332211122",
		"administrator": true
	},
    "errorCode": "null",
    "message": null
}
```
### 1.3 �޸� 

| | |
| - | - |
| url | [/user/updateAdminUser](/user/updateAdminUser) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� | ȡֵ��Χ |
| - | - | - | - | - |
| id | Long | Y | �޸�����ID |  |
| userName | string | Y | �û��� | ���֡���ĸ��������������20���ַ� |
| name | string | Y| �û����� | �ɺ��֡���ĸ��������������20���ַ� |
| password | String | Y | ����   | ����ĸ��������������24���ַ� |
| confirmPwd | String | Y | ȷ������  | ����ĸ��������������24���ַ� |
| mobile | String | Y | �ֻ� | ������ɣ���������11������ |
| administrator | Boolean | Y | ϵͳ����Ա |  |
| roleIdList | string | N | ��ɫid |


#### ����ֵ

| name | type | ���� |
| :-: | :-: | :-: |
| id | Long | ��������ID |
| userName | string | Y | �û��� | ���֡���ĸ��������������20���ַ� |
| name | string | Y| �û����� | �ɺ��֡���ĸ��������������20���ַ� |
| password | String | Y | ����   | ����ĸ��������������24���ַ� |
| confirmPwd | String | Y | ȷ������  | ����ĸ��������������24���ַ� |
| mobile | String | Y | �ֻ� | ������ɣ���������11������ |
| administrator | Boolean | Y | ϵͳ����Ա |  |

```javascript
{
    "success": true,
    "data":{
		"id": 21,
		"createDate": "2017-07-24 14:52:59",
		"userName": "cs11",
		"name": "����11",
		"password": "1bbd886460827015e5d605ed44252251",
		"mobile": "133322111211",
		"administrator": true
	},
    "errorCode": "null",
    "message": null
}
```

### 1.4 ��֤�û����Ƿ���� 
| | |
| - | - |
| url | [/user/validateAdminUserName](/user/validateAdminUserName) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� |
| - | - | - | - | - |
| id | Long | N | �������ô����޸���Ҫ�� |
| userName | String | Y | �û��� |


#### ����ֵ

| name | type | ���� |
| :-: | :-: | :-: |
| data | boolean | false���ڣ�true������ |  


```javascript
{
    "success": true,
    "data": false,
    "errorCode": null,
    "message": null
}
```

### 1.5 ��ȡ��ɫ�б� 
| | |
| - | - |
| url | [/role/getRoleList](/role/getRoleList) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� |
| - | - | - | - | - |


#### ����ֵ

| name | type | ���� |
| :-: | :-: | :-: |
| id | Long | id |  
| roleName | String | ��ɫ���� |  
| description | String | ���� |  


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
                "roleName": "ϵͳ����Ա",
                "description": "ϵͳ����Ա",
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

### 1.6 ��������ɾ�� 

| | |
| - | - |
| url | [/user/deleteAdminUsers](/user/deleteAdminUsers) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� |
| - | - | - | - | - |
| ids | List Long | Y | id |


#### ����ֵ�������ɹ�������ϢΪ�գ�ʧ�ܷ���������Ϣ��

| name | type | ���� |
| :-: | :-: | :-: |
| errorCode | string | ������� |
| expLevel | string | ����ȼ� |
| message | string | ������Ϣ |


```javascript
{
    "success": true,
    "data": "�����ɹ���",
    "errorCode": "",
    "message": ""
}
```

### 1.7 ��������ɾ�� 

| | |
| - | - |
| url | [/user/deleteAdminUserById](/user/deleteAdminUserById) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� |
| - | - | - | - | - |
| id |Long | Y | id |


#### ����ֵ�������ɹ�������ϢΪ�գ�ʧ�ܷ���������Ϣ��

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

### 1.8 ������ѯ 

| | |
| - | - |
| url | [/user/gotoEditPage](/user/gotoEditPage) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� |
| - | - | - | - | - |
| id |Long | Y | ��������ID��ѯ |


#### ����ֵ

| name | type | ���� |
| :-: | :-: | :-: |
| id | Long | ����ID |  
| userName | string | �û����� |
| name | string | �û����� |
| password | String  | ����  |
| mobile | String | �绰 | 
| administrator | boolean  | �Ƿ����Ա | 
| roleIdList | String | ��ɫid | 


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
        "roleIdList": "1"
    },
    "errorCode": null,
    "message": null
}
```

### 1.9 �������� 

| | |
| - | - |
| url | [/user/gotoRetPasswordPage](/user/gotoRetPasswordPage) | 
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


```javascript
{
    "success": true,
    "data": {
        "id": 4,
        "userName": "byj",
        "name": "����Ա",
        "password": "1bbd886460827015e5d605ed44252251",
        "mobile": "13111111111",
        "administrator": true,
    },
    "errorCode": null,
    "message": null
}
```

### 1.10 �鿴 
| | |
| - | - |
| url | [/user/gotoViewPage](/user/gotoViewPage) | 
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

### 1.11 �鿴ʱ��ȡ��ɫ 
| | |
| - | - |
| url | [/role/getAdminUserRoleList](/role/getAdminUserRoleList) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� |
| - | - | - | - | - |
| roleIdList | String | Y | ��ɫID |


#### ����ֵ

| name | type | ���� |
| :-: | :-: | :-: |
| id | Long | ����ID |  
| roleName | String | ��ɫ�� |
| description | String |���� |


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
                "roleName": "ϵͳ����Ա",
                "description": "ϵͳ����Ա",
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