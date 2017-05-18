#  主观风险评估接口API

[TOC]

## 1. 主观风险评估
### 1.1 获取风险评估信息 

| | |
| - | - |
| url | [/voteManage/viewVoteItem](/voteManage/viewVoteItem) | 
| method | GET | 

#### 参数

| name | type | mandatory | 描述 | 取值范围 |
| - | - | - | - | - |
| businessNo | string | Y | 业务编号 | 评估公司时为公司编号，评估个人时为身份证号 |
| voteType | number | Y | 投票类型 | 1:公司，2:个人 |


#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| highNum | number | 评估为高的票数 |
| mediumNum | number | 评估为中的票数 |
| lowNum | number | 评估为低的票数 |


```javascript
{
    "highNum":34,
    "mediumNum":27,
    "lowNum":23
}
```

### 1.2 新增风险评估信息
| | |
| - | - |
| url | [/voteManage/addVoteItem](/voteManage/addVoteItem) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 取值范围 |
| - | - | - | - | - |
| businessNo | string | Y | 业务编号 | 评估公司时为公司编号，评估个人时为身份证号 |
| voteType | number | Y | 投票类型 | 1:公司，2:个人 |
| description | string | N | 评估描述 | 描述不能超过200个字符 |
| grade | number | Y | 评估等级 | 1:高，2:中，3:低 |

#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| highNum | number | 评估为高的票数 |
| mediumNum | number | 评估为中的票数 |
| lowNum | number | 评估为低的票数 |

```javascript
{
    "highNum":1,
    "mediumNum":2,
    "lowNum":3
}
```