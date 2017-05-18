#  主观风险评估接口API

[TOC]

## 1. 公司主观风险评估
### 1.1 获取公司风险评估信息 

| | |
| - | - |
| url | [/companyVoteManage/viewCompanyVote](/companyVoteManage/viewCompanyVote) | 
| method | GET | 

#### 参数

| name | type | mandatory | 描述 | 取值范围 |
| - | - | - | - | - |
| companyId | string | Y | 公司编号 | - |

#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| id | number | 公司风险评估编号 |
| companyId | string | 公司编号 |
| highNum | number | 评估为高的票数 |
| mediumNum | number | 评估为中的票数 |
| lowNum | number | 评估为低的票数 |
| description | string | 评估描述 |


```javascript
{
    "id":1
    "companyId":"1234",
    "highNum":34,
    "mediumNum":27,
    "lowNum":23，
    "description":null
}
```

### 1.2 新增公司风险评估信息
| | |
| - | - |
| url | [/companyVoteManage/addCompanyVote](/companyVoteManage/addCompanyVote) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 取值范围 |
| - | - | - | - | - |
| companyVote.companyId | string | Y | 公司编号 | - |
| companyVote.description | string | N | 评估描述 | 描述不能超过200个字符 |
| grade | number | Y | 评估等级 | 1：高，2：中，3：低 |

#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: | --- |
| success | boolean | true:成功 |
| companyVote.id | number | 公司风险评估编号 |
| companyVote.highNum | number | 评估为高的票数 |
| companyVote.mediumNum | number |  评估为中的票数 |
| companyVote.lowNum | number |  评估为低的票数 |

```javascript
{
    "success": true,
	"companyVote":{
        "id":1,
        "highNum":1,
        "mediumNum":0,
        "lowNum":0
    }
}
```

### 1.3 编辑公司风险评估信息
| | |
| - | - |
| url | [/companyVoteManage/updateCompanyVote](/companyVoteManage/updateCompanyVote) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 取值范围 |
| - | - | - | - | - |
| companyVote.id | number | Y | 公司评估信息编号 | - |
| companyVote.companyId | string | Y | 公司编号 | - |
| companyVote.description | string | N | 评估描述 | 描述不能超过200个字符 |
| grade | number | Y | 评估等级 | 1：高，2：中，3：低 |

#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: | --- |
| success | boolean | true:成功 |
| companyVote.id | number | 公司风险评估编号 |
| companyVote.highNum | number | 评估为高的票数 |
| companyVote.mediumNum | number |  评估为中的票数 |
| companyVote.lowNum | number |  评估为低的票数 |

```javascript
{
    "success": true,
	"companyVote":{
        "id":1,
        "highNum":1,
        "mediumNum":0,
        "lowNum":0
    }
}
```

## 2. 个人主观风险评估
### 2.1 获取个人风险评估信息 

| | |
| - | - |
| url | [/personVoteManage/viewPersonVote](/personVoteManage/viewPersonVote) | 
| method | GET | 

#### 参数

| name | type | mandatory | 描述 | 取值范围 |
| - | - | - | - | - |
| idNum | string | Y | 身份证号 | - |

#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| id | number | 个人风险评估编号 |
| idNum | string | 身份证号 |
| highNum | number | 评估为高的票数 |
| mediumNum | number | 评估为中的票数 |
| lowNum | number | 评估为低的票数 |
| description | string | 评估描述 |


```javascript
{
    "id":1
    "idNum":"1234",
    "highNum":34,
    "mediumNum":27,
    "lowNum":23，
    "description":null
}
```

### 2.2 新增个人风险评估信息
| | |
| - | - |
| url | [/personVoteManage/addPersonVote](/personVoteManage/addPersonVote) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 取值范围 |
| - | - | - | - | - |
| personVote.idNum | string | Y | 身份证号 | - |
| personVote.description | string | N | 评估描述 | 描述不能超过200个字符 |
| grade | number | Y | 评估等级 | 1：高，2：中，3：低 |

#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: | --- |
| success | boolean | true:成功 |
| personVote.id | number | 个人风险评估编号 |
| personVote.highNum | number |  评估为高的票数  |
| personVote.mediumNum | number | 评估为中的票数 |
| personVote.lowNum | number | 评估为低的票数 |

```javascript
{
    "success": true，
	"personVote":{
		"id":1,
		"highNum":1,
        "mediumNum":2,
        "lowNum":0,
	}
}
```

### 2.3 编辑个人风险评估信息
| | |
| - | - |
| url | [/personVoteManage/updatePersonVote](/personVoteManage/updatePersonVote) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 取值范围 |
| - | - | - | - | - |
| personVote.id | number | Y | 个人评估信息编号 | - |
| personVote.idNum | string | Y | 身份证号 | - |
| personVote.description | string | N | 评估描述 | 描述不能超过200个字符 |
| grade | number | Y | 评估等级 | 1：高，2：中，3：低 |

#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: | --- |
| success | boolean | true:成功 |
| personVote.id | number | 个人风险评估编号 |
| personVote.highNum | number |  评估为高的票数  |
| personVote.mediumNum | number | 评估为中的票数 |
| personVote.lowNum | number | 评估为低的票数 |

```javascript
{
    "success": true，
	"personVote":{
		"id":1,
		"highNum":1,
        "mediumNum":2,
        "lowNum":3,
	}
}
```
