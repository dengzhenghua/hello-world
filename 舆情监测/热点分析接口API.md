#  �ȵ����
[TOC]��
## 1. �ȵ����
### 1.1 ��������Դ 
| | |
| - | - |
| url | [/hotSpotAnalysis/countSentimentAnalysiForMap](/hotSpotAnalysis/countSentimentAnalysiForMap) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� | 
| - | - | - | - | - |
| programmeId | Long | Y | ����ID | 

#### ����ֵ

| name | type | ���� |
| :-: | :-: | :-: |
| websit | String | ��վ |
| percent | Double | �ٷֱ�|


```javascript
{
    "success": true,
    "data": [
        {
            "websit": "����",
            "percent": 23.11
        }, {
            "websit": "��Ѷ",
            "percent": 15.34
        }
    ],
    "errorCode": null,
    "message": null
}
```

### 1.2 ��������Դ 
| | |
| - | - |
| url | [/hotSpotAnalysis/findHotMicroblog](/hotSpotAnalysis/findHotMicroblog) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� | 
| - | - | - | - | - |

#### ����ֵ

| name | type | ���� |
| :-: | :-: | :-: |
| profileImageUrl | String | ͷ�� |
| screenName | String | �˺�|
| followersCount | Long | ��˿��|
| total | Long | ������|


```javascript
{
    "success": true,
    "data": [
        {
            "total": 28519039,
            "screenName": "������",
            "profileImageUrl": "https://tva3.sinaimg.cn/crop.1.0.179.179.180/884f7263jw8ev7jo9p7gtj20500500sy.jpg",
            "followersCount": 38628578
        },
        {
            "total": 19482963,
            "screenName": "�ɶ��̱�",
            "profileImageUrl": "https://tva2.sinaimg.cn/crop.0.0.1000.1000.180/655dd5f3jw8ev7qcyp08ij20rs0rs77h.jpg",
            "followersCount": 9489415
        }
    ],
    "errorCode": null,
    "message": null
}
```

### 1.3 ���ż���
| | |
| - | - |
| url | [/hotSpotAnalysis/hotKeyWordsAnalysis](/hotSpotAnalysis/hotKeyWordsAnalysis) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� | 
| - | - | - | - | - |

#### ����ֵ

| name | type | ���� |
| :-: | :-: | :-: |
| profileImageUrl | Map | key���ƣ�valueֵ |


```javascript
{
    "success": true,
    "data": {
        "qqq": "222",
        "ww": "333"
    },
    "errorCode": null,
    "message": null
}
```

### 1.4 �����¼�
| | |
| - | - |
| url | [/hotSpotAnalysis/monitorHotIssueAnalysis](/hotSpotAnalysis/monitorHotIssueAnalysis) | 
| method | POST | 

#### ����

| name | type | mandatory | ���� | 
| - | - | - | - | - |
| programmeId | Long | N | ������ID��ѯ��������¼���������ѯ���������¼� | 

#### ����ֵ

| name | type | ���� |
| :-: | :-: | :-: |
| title | String | ���� |
| dataSources | Long | ������Դ |
| publishDate | Date | ���µķ���ʱ�� |
| contentText | String | ���� |


```javascript
{
    "success": true,
    "data": {
        "page": 1,
        "total": 1,
        "records": 2,
        "rows":  [
        {
            "title": "���������ٵ����ܽ���",
            "dataSources": "2",
            "publishDate": "2017/7/20 18:24:05",
            "contentText": "qwafdgasdfasfawerwsafds"
        },
        {
            "title": "���������ٵ����ܽ���1",
            "dataSources": "1",
            "publishDate": "2017/7/20 18:24:05",
            "contentText": "���������ٵ����ܽ���1���������ٵ����ܽ���1���������ٵ����ܽ���1"
        }
    ]
    },
    "errorCode": null,
    "message": null
}
```