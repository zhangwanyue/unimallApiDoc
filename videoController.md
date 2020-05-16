### 获取视频上传凭证和上传地址

* request类型  
  
  POST

* url  
  
  `xxx:8080/video/upload`

* request body

| 参数 | 说明 |
| :--- | :--- |
| filename | 视频名（必须包含文件类型后缀） |
| title | 视频标题 |

* response body

| 参数 | 说明 |
| :--- | :--- |
| videoid | 视频id |
| uploadauth | 视频上传凭证(base64编码) |
| uploadaddress | 视频上传地址(baseh64编码) |
| path | 请求url |
| status | 状态码 |
| message | 状态消息 |
| error | 错误消息 |
| timestamp | 时间戳 |

正确时：
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

错误时：
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

### 获取视频播放凭证

* request类型

  POST

* url
  
  `xxx:8080/video/playauth`

* request body

| 参数 | 说明 |
| :--- | :--- |
| videoid | 视频id |

* response body

| 参数 | 说明 |
| :--- | :--- |
| videoid | 视频id |
| playauth | 视频播放凭证(base64编码) |
| path | 请求url |
| status | 状态码 |
| message | 状态消息 |
| error | 错误消息 |
| timestamp | 时间戳 |

正确时：

```json
{
    "path": "/video/playauth",
    "requestid": "F6C21CE6-AF84-4001-8F53-FFE5AE66B84B",
    "videotitle": "this is title",
    "videoid": "c5bcec9584e64422992830f1e23d7446",
    "message": "success",
    "playauth": "xxx(base64编码)",
    "status": 200,
    "timestamp": 1589613331729
}
```

错误时：

```json
{
    "path": "/video/playauth",
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
    "path": "/video/playauth"
}
```





