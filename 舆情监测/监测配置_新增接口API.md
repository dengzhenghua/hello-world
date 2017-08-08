#  监测配置
[TOC]仇凯
## 1.监测配置
### 1.1新增列表
| | |
| - | - |
| url | [/crawler/findAllForPage](/crawler/findAllForPage) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 
| - | - | - | - | - |
| configType | Long | N | 爬虫配置：1，主数据配置分类：2 | 
| programmeId | Long | Y | 方案ID |

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
        "records": 3,
        "rows": [
            {
                "id": 1,
                "crawlerName": "1",
                "crawlerlabel": 1,
                "configType": 1,
            },
            {
                "id": 2,
                "crawlerName": "1",
                "crawlerlabel": 0,
                "configType": 1,
            },
            {
                "id": 3,
                "crawlerName": "1",
                "crawlerlabel": 1,
                "configType": 1,
            }
        ]
    },
    "errorCode": null,
    "message": null
}
```