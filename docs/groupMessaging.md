## 5 短信群发（json）

**简要描述:**
* 国际群发接口（json版本）

**请求URL:**
* http://intapi.253.com/send

**请求方式:**
* POST<br/>
content-type：application/json

**参数：**

|参数名|必选|类型|说明|
|:---|:---|:---|:---|
|account|是|string|账户|
|password|是|string|密码|
|msg|是|string|短信内容|
|mobile|是|string|手机号|

**请求示例**
{<br/>
    `"account"`:"I6428061",<br/>
    `"password"`:"123456",<br/> 
    `"msg":"`【253】你好，您的验证码是：123456",<br/>
    `"mobile"`:"8613011111111,8613022222222,8613033333333"<br/>
}<br/>

**返回参数说明**

|参数名|类型|说明|
|:---|:---|:---|
|code|string|返回码|
|message|string|消息|
|data|object|数据包|
|messageId|string|消息id|
|errorPhone|array|群发错误手机号|

**返回示例(单发)**<br/>
 {<br/>
    `"code"`: "0",<br/>
    `"message"`: "成功",<br/>
    `"data"`: {<br/>
        "messageId": "17122614541000000355"<br/> 
    }<br/>
}<br/>
单发返回单个消息id
<br/>
<br/>

**返回示例(群发)**<br/>
{<br/>
    `"code"`: "0",<br/>
    `"message"`: "成功",<br/>
    `"data"`: {<br/>
        `"messageId"`: "I6428061_1712261459_40",<br/>
         `"errorPhone"`: []<br/>
    }<br/>
}<br/>
群发返回批次消息id
<br/>
<br/>

**返回示例(发送错误)**

{<br/>
    `"code"`: "123",<br/>
    `"message"`: "短信内容不能为空",<br/>
    `"data"`: null<br/>
}<br/>

**返回码**

|code|说明|
|:---|:---|
|0|成功|
|101|账号不存在|
|102|密码错误|
|106|短信内容长度超过536字符限制|
|108|手机号码格式错误|
|109|手机号码数量错误|
|110|余额不足|
|112|产品错误|
|114|客户端IP错误|
|115|发送权限错误|
|123|短信内容为空|
|125|特定客户手机号码同一天不能超过十次|
|128|账号长度超过50位|
|129|产品价格配置错误|


