#  采集配置>爬虫配置接口API
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
| crawlerName | string | N | 关键字 | 

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
                "id": 5,
                "crawlerName": "zsj",
				"crawlerFile":"11111",
                "crawlerlabel": 1,
                "crawlertype": 2,
                "rowkeyPrefix": "213",
                "kafkaTopic": "123111111111111112312"
            }
        ]
    },
    "errorCode": null,
    "message": null
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
| crawlerName | string | 爬虫名称 | 汉字、字母、数字、特殊符号组成，允许输入50个字符 |
| crawlerFile | string | 配置 | 由汉字、字母、数字、特殊符号组成，允许无限输入 |
| crawlerLabel | Long | 标签  |
| crawlerType | Long | 分类 | 
| rowkeyPrefix | string | rowkey | 汉字、字母、数字、特殊符号组成，允许输入4个字符 |
| kafkaTopic | string |  kafkaTopic | 汉字、字母、数字、特殊符号组成，允许输入100个字符 |

```javascript
{
    "success": true,
    "data": {
        "id": 8,
        "crawlerName": "1111",
		"crawlerFile":"11111",
        "crawlerlabel": 0,
        "crawlertype": 1,
        "rowkeyPrefix": "11",
        "kafkaTopic": "111"
    },
    "errorCode": "null",
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
| crawlerName | string | 爬虫名称 | 汉字、字母、数字、特殊符号组成，允许输入50个字符 |
| crawlerFile | string | 配置 | 由汉字、字母、数字、特殊符号组成，允许无限输入 |
| crawlerLabel | Long | 标签  |
| crawlerType | Long | 分类 | 
| rowkeyPrefix | string | rowkey | 汉字、字母、数字、特殊符号组成，允许输入4个字符 |
| kafkaTopic | string |  kafkaTopic | 汉字、字母、数字、特殊符号组成，允许输入100个字符 |

```javascript
{
    "success": true,
    "data": {
        "id": 8,
        "crawlerName": "22",
        "crawlerFile": "2",
        "crawlerlabel": 22,
        "crawlertype": 2,
        "rowkeyPrefix": "2",
        "kafkaTopic": "2"
    },
    "errorCode": "null",
    "message": null
}
```

### 1.4 爬虫多条数据删除 

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
    "success": true,
    "data": "操作成功！",
    "errorCode": "",
    "message": ""
}
```

### 1.5 爬虫单条数据删除 

| | |
| - | - |
| url | [/crawler/deleteCrawlerByIds](/crawler/deleteCrawlerById) | 
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

### 1.6 爬虫单条查询 

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
| id | Long | 修改数据ID |  
| crawlerName | string | 爬虫名称 |
| crawlerFile | string | 配置 |
| crawlerLabel | Long  | 标签  |
| crawlerType | Long | 分类 | 
| rowkeyPrefix | string  | rowkey | 
| kafkaTopic | string | kafkaTopic | 


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