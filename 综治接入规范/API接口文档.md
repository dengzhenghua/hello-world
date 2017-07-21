# 用户查询

#### 支持第三方代理调用
## 接口描述



# 公共参数

## 请求地址

环境	HTTP请求地址
正式环境	http://XX/api/XX/gateway.do
## 公共请求参数

参数 | 类型 | 是否必填 | 最大长度 | 描述 | 示例值
------------ | ------------- |-------- |-------- |-------- |--------
 name| String | Y | 100 | 名称 | Johe
# 请求参数

参数 | 类型 | 是否必填 | 最大长度 | 描述 | 示例值
------------ | ------------- |-------- |-------- |-------- |--------
 name| String | Y | 100 | 名称 | Johe
# 公共响应参数

参数 | 类型 | 是否必填 | 最大长度 | 描述 | 示例值
------------ | ------------- |-------- |-------- |-------- |--------
 name| String | Y | 100 | 名称 | Johe
# 响应参数

参数 | 类型 | 是否必填 | 最大长度 | 描述 | 示例值
------------ | ------------- |-------- |-------- |-------- |--------
 name| String | Y | 100 | 名称 | Johe

# 请求示例

JAVA    HTTP请求源码
```java
DefaultTqClientApi defaultTqClientApi = new DefaultTqClientApi(
				host + "api/test/testDubboService/findalluser1.json");
{
    defaultTqClientApi = new DefaultTqClientApi(host + "api/cooperation/appeal/appealWithdraw.json");
    TqParam tqParam = new TqParam("app1");
    tqParam.setVersion("1.0");
    tqParam.addBizParam("serialNumber", "serialNumber2221");
    tqParam.addBizParam("dealUserId", 100);
    tqParam.addBizParam("dealMessage", "dealMessage哈哈哈哈哈");
    tqParam.addBizParam("appKey", "app1");

    // String json =
    // "{name:'附件1',fileType:'',fileLength:'1000',transferype:'issue',}";
    JSONObject attachments =new JSONObject();
    JSONArray array = new JSONArray();
    JSONObject json = new JSONObject();
    json.put("name", "附件1");
    json.put("fileType", "1");
    json.put("url", "issue");
    attachments.put("uploadFiles", array);
    array.add(json);
    tqParam.addBizParam("attachments", attachments);

    System.out.println(defaultTqClientApi.execute(tqParam,
            "MIICdgIBADANBgkqhkiG9w0BAQEFAASCAmAwggJcAgEAAoGBAIayHQA4W5V1zrTTgmap62OF57Rh3D7Elm7DDt3kdmPfsw6t+N2PSBTrF37jxr/FUH5BQzEgbpIcB09zhIMKbvyjQ9q/Xvy/V7BI/giICw9OVa1n72qNrG6UEx8KDZoTM8DwJW43inOH8qN/ZQt4mu4Yr0BIiRZWN5Pu27dXdsgHAgMBAAECgYAhE0m1zSEIIYahtrJ1vVH0/WO5UrJ/o0yBZFqZOEmuGrdgam4LEe0UXepGGW6rlqs+ZY43WQxtyn4tD2PBveUkvZpLWeVpWV9wtNWc1t4A7k6VW2XnUqkNRCF6KLrJYgiBdH+bhE+tdnG7BaPiIvg5EtHBVs0dW6GLyOxA5huwqQJBAOEaWEPS/mrZ1j1tr5z4uEwxWit1rdijxpCUxWarKTd5DG6xiYoVcEf+W5TDr/DqwIwW4h5J0SXAUmOpXnkByFUCQQCZLwvXVk04DWJaPMpMrssxLBv5RyfV4H2uR+0ErQeNpBe8oLReH4NmJShJVFIlnM1Gry09kU2LeXHU4Ti2zlrrAkBgSUWSFXGQQQe8FOv2aAllRgL87gRj04I/G/PoO7SQru2bd8OOVidGFE4WLzJWCgQ8qBkmvYqB7GcRjEQF3LZVAkAXq6RpxwUxpyfOh9w+0zfExmsgLvWh4Amrt6OReGdVZMjiNfcJIFd+njlGc4gqFbvGs2ULQXu5FLAZVCAeZ263AkEAwmm2SLI0bkKfPLrTaTSyUBGuXdinfituzEW2gFcYuyMrMNaF1eeM0nP7n5yPJChzRorxi22HQZlDtYl9yuTlMg==",
            "SHA1WithRSA"));
}
```
# 响应示例

```java
JSON 示例  XML 示例
{
    "success":true,
    "response":{
        
    },
    "requestId": "1500607040557_603",
    "errorInfo": {
        "errorCode": "null",
        "errorMsg": "null",
        "success":"true"
    }
}
```
# 异常示例

JSON 示例
```java
{
    "success": false,
    "requestId": "1500607040557_603",
    "errorInfo": {
        "errorCode": "201",
        "errorMsg": "解析attachments失败,value:{\"uploadFiles\":[{\"name\":\"附件1\",\"fileType\":\"1\",\"url\":\"issue\"}]}"
    }
}
```
# 业务错误码

### 公共错误码

错误码 | 错误描述 | 解决方案 |
------------ | ------------- |--------
 201| 网关请求失败 | 请检查网络问题



