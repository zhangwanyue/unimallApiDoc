## 1. 获取视频上传凭证和上传地址

### request

* request类型

  POST

* url

  `xxx:8080/video/upload`

* request body(form-data)

| 参数 | 类型 | 说明 |
| :--- | :--- | :--- |
| filename | String | 视频名**（必须包含文件类型后缀）** |
| title | String | 视频标题 |

* 样例：

```js
var form = new FormData();
form.append("filename", "test.mp4");
form.append("title", "file");

var settings = {
  "url": "xxx:8080/video/upload",
  "method": "POST",
  "timeout": 0,
  "processData": false,
  "mimeType": "multipart/form-data",
  "contentType": false,
  "data": form
};

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

### response

* response body

| 参数 | 类型 | 说明 |
| :--- | :--- | :--- |
| videoid | String | 视频id |
| uploadauth | String | 视频上传凭证\(base64编码\) |
| uploadaddress | String | 视频上传地址\(baseh64编码\) |
| path | String | 请求url |
| status | int | 状态码 |
| message | String | 状态消息 |
| error | String | 错误标识 |
| timestamp | long | 时间戳 |

* 正确时：

```json
{
    "uploadauth": "xxx(base64编码)",
    "path": "/video/upload",
    "videoid": "7f5bc39495ef4669a235de45242dc3b0",
    "uploadaddress": "xxx(base64编码)",
    "message": "success",
    "status": 200,
    "timestamp": 1589600504060
}
```

* 错误时：

```json
{
    "path": "/video/upload",
    "message": "The specified FileName's extension is illegal.",
    "error": "VOD CLIENT ERROR",
    "status": 11000,
    "timestamp": 1589613087515
}
```

```json
{
    "timestamp": "2020-05-16T03:43:21.157+0000",
    "status": 400,
    "error": "Bad Request",
    "message": "Required String parameter 'title' is not present",
    "path": "/video/upload"
}
```

## 2. 刷新视频上传凭证

### request

* request类型

  POST

* url

  `xxx:8080/video/refresh-upload`

* request body(form-data)

| 参数 | 类型 | 说明 |
| :--- | :--- | :--- |
| videoid | String | 视频id |

* 样例：

```js
var form = new FormData();
form.append("videoid", "61b510b00a354567b6e04cc489cd47fd");

var settings = {
  "url": "xxx:8080/video/refresh-upload",
  "method": "POST",
  "timeout": 0,
  "processData": false,
  "mimeType": "multipart/form-data",
  "contentType": false,
  "data": form
};

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

### reponse

* reponse body

| 参数 | 类型 | 说明 |
| :--- | :--- | :--- |
| videoid | String | 视频id |
| uploadauth | String | 视频上传凭证\(base64编码\) |
| uploadaddress | String |视频上传地址\(baseh64编码\) |
| path | String | 请求url |
| status | int | 状态码 |
| message | String | 状态消息 |
| error | String | 错误标识 |
| timestamp | long | 时间戳 |

* 正确时：

```json
{
    "uploadauth": "xxx(base64编码)",
    "path": "/video/refresh-upload",
    "videoid": "61b510b00a354567b6e04cc489cd47fd",
    "uploadaddress": "xxx(base64编码)",
    "message": "success",
    "status": 200,
    "timestamp": 1590035306291
}
```

* 错误时：

```json
{
    "path": "/video/refresh-upload",
    "message": "The video does not exist.",
    "error": "VOD CLIENT ERROR",
    "status": 11000,
    "timestamp": 1590035102492
}
```

```json
{
    "timestamp": "2020-05-21T04:25:43.040+0000",
    "status": 400,
    "error": "Bad Request",
    "message": "Required String parameter 'videoid' is not present",
    "path": "/video/refresh-upload"
}
```

## 3. 获取视频播放凭证

### request

* request类型

  POST

* url

  `xxx:8080/video/play-auth`

* request body(form-data)

| 参数 | 类型 | 说明 |
| :--- | :--- | :--- |
| videoid | String | 视频id |

* 样例：

```js
var form = new FormData();
form.append("videoid", "c5bcec9584e64422992830f1e23d7446");

var settings = {
  "url": "xxx:8080/video/play-auth",
  "method": "POST",
  "timeout": 0,
  "processData": false,
  "mimeType": "multipart/form-data",
  "contentType": false,
  "data": form
};

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

### response

* response body

| 参数 | 类型 | 说明 |
| :--- | :--- | :--- |
| videoid | String | 视频id |
| playauth | String | 视频播放凭证\(base64编码\) |
| path | String | 请求url |
| status | int | 状态码 |
| message | String | 状态消息 |
| error | String | 错误标识 |
| timestamp | long | 时间戳 |

* 正确时：

```json
{
    "path": "/video/play-auth",
    "requestid": "F6C21CE6-AF84-4001-8F53-FFE5AE66B84B",
    "videotitle": "this is title",
    "videoid": "c5bcec9584e64422992830f1e23d7446",
    "message": "success",
    "playauth": "xxx(base64编码)",
    "status": 200,
    "timestamp": 1589613331729
}
```

* 错误时：

```json
{
    "path": "/video/play-auth",
    "message": "The video does not exist.",
    "error": "VOD CLIENT ERROR",
    "status": 11000,
    "timestamp": 1589613942294
}
```

```json
{
    "timestamp": "2020-05-16T07:26:07.257+0000",
    "status": 400,
    "error": "Bad Request",
    "message": "Required String parameter 'videoid' is not present",
    "path": "/video/play-auth"
}
```



