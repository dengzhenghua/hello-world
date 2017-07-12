#  采集配置接口API

[TOC]仇凯

## 1. 爬虫配置
### 1.1 爬虫列表 

| | |
| - | - |
| url | [/crawler/findCrawlerForPage](/crawler/findCrawlerForPage) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 
| - | - | - | - | - |
| crawler.crawlerName | string | Y | 关键字 | 

#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| page | string | 每页数 |
| total | string | 总页数|
| records | string | 总条数 |
| rows | object |  |


```javascript
{
    "page": 1,
        "total": 1,
        "records": 1,
        "rows": [
            {
                "id": 6,
                "createUser": "admin",
                "createDate": "2017-07-10 14:56:32",
                "updateUser": null,
                "updateDate": null,
                "sortField": null,
                "order": null,
                "tqmobile": null,
                "crawlerName": "zsj",
                "crawlerFile": "1312312311111111111111111111111231231",
                "user": {
                    "id": 1
                },
                "crawlerlabel": null,
                "crawlertype": null,
                "rowkeyPrefix": "213",
                "collectionType": null,
                "configType": 1,
                "kafkaTopic": "123111111111111112312"
            }
        ]
}
```
### 1.2 爬虫新增 

| | |
| - | - |
| url | [/crawler/addCrawler](/crawler/addCrawler) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 取值范围 |
| - | - | - | - | - |
| crawlerName | string | Y | 爬虫名称 | 汉字、字母、数字、特殊符号组成，允许输入50个字符 |
| crawlerFile | string | Y| 配置 | 由汉字、字母、数字、特殊符号组成，允许无限输入 |
| crawlerLabel | Long | N | 标签  |
| crawlerType | Long | Y | 分类 | 
| rowkeyPrefix | string | Y | rowkey | 汉字、字母、数字、特殊符号组成，允许输入4个字符 |
| kafkaTopic | string | Y | kafkaTopic | 汉字、字母、数字、特殊符号组成，允许输入100个字符 |


#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| id | Long | 新增数据ID |


```javascript
{
    "success": true,
    "data": {
        "id": 7
    },
    "errorCode": "500",
    "message": null
}
```
### 1.3 爬虫修改 

| | |
| - | - |
| url | [/crawler/updateCrawler](/crawler/updateCrawler) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 取值范围 |
| - | - | - | - | - |
| id | Long | Y | 修改数据ID |  |
| crawlerName | string | Y | 爬虫名称 | 汉字、字母、数字、特殊符号组成，允许输入50个字符 |
| crawlerFile | string | Y| 配置 | 由汉字、字母、数字、特殊符号组成，允许无限输入 |
| crawlerLabel | Long | N | 标签  |
| crawlerType | Long | Y | 分类 | 
| rowkeyPrefix | string | Y | rowkey | 汉字、字母、数字、特殊符号组成，允许输入4个字符 |
| kafkaTopic | string | Y | kafkaTopic | 汉字、字母、数字、特殊符号组成，允许输入100个字符 |


#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| id | Long | 修改ID |

```javascript
{
    "success": true,
    "data": {
        "id": 7
    },
    "errorCode": "500",
    "message": null
}
```

### 1.4 爬虫删除 

| | |
| - | - |
| url | [/crawler/deleteCrawlerByIds](/crawler/deleteCrawlerByIds) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 |
| - | - | - | - | - |
| id |Long | Y | id |


#### 返回值（操作成功返回信息为空，失败返回以下信息）

| name | type | 描述 |
| :-: | :-: | :-: |
| errorCode | string | 错误编码 |
| expLevel | string | 错误等级 |
| message | string | 错误信息 |


```javascript
{
    "errorCode":'BE100-01',
    "expLevel":'error',
    "message":'参数错误！'
}
```

### 1.5爬虫单条查询 

| | |
| - | - |
| url | [/crawler/getCrawlerById](/crawler/getCrawlerById) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 |
| - | - | - | - | - |
| id |Long | Y | 修改时查询数据 |


#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| id | Long | Y | 修改数据ID |  
| crawlerName | string | Y | 爬虫名称 |
| crawlerFile | string | Y| 配置 |
| crawlerLabel | Long | N | 标签  |
| crawlerType | Long | Y | 分类 | 
| rowkeyPrefix | string | Y | rowkey | 
| kafkaTopic | string | Y | kafkaTopic | 


```javascript
{
    "success": true,
    "data": {
        "id": 7,
        "crawlerName": "1111",
        "crawlerFile": "111",
        "crawlerlabel": null,
        "crawlertype": null,
        "rowkeyPrefix": "11",
        "kafkaTopic": "111"
    },
    "errorCode": "500",
    "message": null
}
```

## 2. 主数据配置
### 2.1 主数据列表 

| | |
| - | - |
| url | [/masterData/findMasterDataForPage](/masterData/findMasterDataForPage) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 
| - | - | - | - | - |
| crawler.crawlerName | string | Y | 关键字 | 

#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| page | string | 每页数 |
| total | string | 总页数|
| records | string | 总条数 |
| rows | object |  |


```javascript
{
     "page": 1,
        "total": 1,
        "records": 1,
        "rows": [
            {
                "id": 5,
                "createUser": "admin",
                "createDate": "2017-07-10 14:54:25",
                "updateUser": null,
                "updateDate": null,
                "sortField": null,
                "order": null,
                "tqmobile": null,
                "crawlerName": "zsj",
                "crawlerFile": "1312312311111111111111111111111231231",
                "user": {
                    "id": 1
                },
                "crawlerlabel": null,
                "crawlertype": null,
                "rowkeyPrefix": "213",
                "collectionType": null,
                "configType": 2,
                "kafkaTopic": "123111111111111112312"
            }
        ]
}
```
### 2.2 主数据新增 

| | |
| - | - |
| url | [/masterData/addMasterData](/masterData/addMasterData) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 取值范围 |
| - | - | - | - | - |
| crawlerName | string | Y | 爬虫名称 | 汉字、字母、数字、特殊符号组成，允许输入50个字符 |
| crawlerLabel | Long | N | 标签  |
| crawlerType | Long | Y | 分类 | 
| rowkeyPrefix | string | Y | rowkey | 汉字、字母、数字、特殊符号组成，允许输入4个字符 |
| kafkaTopic | string | Y | kafkaTopic | 汉字、字母、数字、特殊符号组成，允许输入100个字符 |
| collectionType | Long | Y | 类型 |


#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| id | Long | 新增数据ID |


```javascript
{
    "success": true,
    "data": {
        "id": 5
    },
    "errorCode": "500",
    "message": null
}
```
### 2.3 主数据修改 

| | |
| - | - |
| url | [/masterData/updateMasterData](/masterData/updateMasterData) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 取值范围 |
| - | - | - | - | - |
| id | Long | Y | 修改数据ID |  |
| crawlerName | string | Y | 爬虫名称 | 汉字、字母、数字、特殊符号组成，允许输入50个字符 |
| crawlerLabel | Long | N | 标签  |
| crawlerType | Long | Y | 分类 | 
| rowkeyPrefix | string | Y | rowkey | 汉字、字母、数字、特殊符号组成，允许输入4个字符 |
| kafkaTopic | string | Y | kafkaTopic | 汉字、字母、数字、特殊符号组成，允许输入100个字符 |
| collectionType | Long | Y | 类型 |


#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| id | Long | 修改ID |

```javascript
{
    "success": true,
    "data": {
        "id": 5
    },
    "errorCode": "500",
    "message": null
}
```

### 2.4 主数据删除 

| | |
| - | - |
| url | [/masterData/deleteMasterDataByIds](/masterData/deleteMasterDataByIds) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 |
| - | - | - | - | - |
| id |Long | Y | id |


#### 返回值（操作成功返回信息为空，失败返回以下信息）

| name | type | 描述 |
| :-: | :-: | :-: |
| errorCode | string | 错误编码 |
| expLevel | string | 错误等级 |
| message | string | 错误信息 |


```javascript
{
    "errorCode":'BE100-01',
    "expLevel":'error',
    "message":'参数错误！'
}
```

### 2.5主数据单条查询 

| | |
| - | - |
| url | [/masterData/getMasterDataById](/masterData/getMasterDataById) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 |
| - | - | - | - | - |
| id |Long | Y | 修改时查询数据 |


#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| id | Long | Y | 修改数据ID |  
| crawlerName | string | Y | 爬虫名称 |
| crawlerLabel | Long | N | 标签  |
| crawlerType | Long | Y | 分类 | 
| rowkeyPrefix | string | Y | rowkey | 
| kafkaTopic | string | Y | kafkaTopic | 
| collectionType | Long | Y | 类型 | 


```javascript
{
    "success": true,
    "data": {
        "id": 7,
        "crawlerName": "1111",
        "crawlerlabel": null,
        "crawlertype": null,
        "rowkeyPrefix": "11",
        "kafkaTopic": "111",
        "collectionType": "111"
    },
    "errorCode": "500",
    "message": null
}
```