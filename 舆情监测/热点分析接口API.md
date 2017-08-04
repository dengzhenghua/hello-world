#  热点分析
[TOC]仇凯
## 1. 热点分析
### 1.1 热门数据源 
| | |
| - | - |
| url | [/hotSpotAnalysis/countSentimentAnalysiForMap](/hotSpotAnalysis/countSentimentAnalysiForMap) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 
| - | - | - | - | - |
| programmeId | Long | Y | 方案ID | 

#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| websit | String | 网站 |
| percent | Double | 百分比|


```javascript
{
    "success": true,
    "data": [
        {
            "websit": "新浪",
            "percent": 23.11
        }, {
            "websit": "腾讯",
            "percent": 15.34
        }
    ],
    "errorCode": null,
    "message": null
}
```

### 1.2 微博热门账号 
| | |
| - | - |
| url | [/hotSpotAnalysis/findHotMicroblog](/hotSpotAnalysis/findHotMicroblog) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 
| - | - | - | - | - |

#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| profileImageUrl | String | 头像 |
| screenName | String | 账号|
| followersCount | Long | 粉丝数|
| total | Long | 文章数|


```javascript
{
    "success": true,
    "data": [
        {
            "total": 28519039,
            "screenName": "人民网",
            "profileImageUrl": "https://tva3.sinaimg.cn/crop.1.0.179.179.180/884f7263jw8ev7jo9p7gtj20500500sy.jpg",
            "followersCount": 38628578
        },
        {
            "total": 19482963,
            "screenName": "成都商报",
            "profileImageUrl": "https://tva2.sinaimg.cn/crop.0.0.1000.1000.180/655dd5f3jw8ev7qcyp08ij20rs0rs77h.jpg",
            "followersCount": 9489415
        }
    ],
    "errorCode": null,
    "message": null
}
```

### 1.3 热门监测词
| | |
| - | - |
| url | [/hotSpotAnalysis/hotKeyWordsAnalysis](/hotSpotAnalysis/hotKeyWordsAnalysis) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 
| - | - | - | - | - |

#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| hotKeyWordsAnalysisList | Map | key日期，value值 |
| hotKeyWordsAnalysis | Map | key监测词，value值 |


```javascript
{
    "success": true,
    "data": {
        "hotKeyWordsAnalysisList": [
            {
                "2017-07-26": 0,
                "2017-07-27": 0,
                "2017-07-28": 0,
                "2017-07-29": 0,
                "2017-07-30": 0,
                "2017-07-31": 0,
                "2017-08-01": 0,
                "2017-08-02": 13
            },
            {
                "2017-07-26": 0,
                "2017-07-27": 0,
                "2017-07-28": 0,
                "2017-07-29": 0,
                "2017-07-30": 0,
                "2017-07-31": 0,
                "2017-08-01": 0,
                "2017-08-02": 13
            }
        ],
        "hotKeyWordsAnalysis": {
            "杭州": 29,
            "消防": 26
        }
    },
    "errorCode": null,
    "message": null
}
```

### 1.4 热门事件
| | |
| - | - |
| url | [/hotSpotAnalysis/monitorHotIssueAnalysis](/hotSpotAnalysis/monitorHotIssueAnalysis) | 
| method | POST | 

#### 参数

| name | type | mandatory | 描述 | 
| - | - | - | - | - |
| programmeId | Long | N | 传方案ID查询监测热门事件，不传查询其它热门事件 | 

#### 返回值

| name | type | 描述 |
| :-: | :-: | :-: |
| title | String | 标题 |
| dataSources | Long | 数据来源 |
| publishDate | Date | 文章的发布时间 |
| contentText | String | 文章 |


```javascript
{
    "success": true,
    "data": {
        "page": 1,
        "total": 1,
        "records": 2,
        "rows":  [
        {
            "title": "刘国梁不再担任总教练",
            "dataSources": "2",
            "publishDate": "2017/7/20 18:24:05",
            "contentText": "qwafdgasdfasfawerwsafds"
        },
        {
            "title": "刘国梁不再担任总教练1",
            "dataSources": "1",
            "publishDate": "2017/7/20 18:24:05",
            "contentText": "刘国梁不再担任总教练1刘国梁不再担任总教练1刘国梁不再担任总教练1"
        }
    ]
    },
    "errorCode": null,
    "message": null
}
```