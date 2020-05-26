下文所有接口:

* url

`xxx:8080/m.api`

* 请求类型

  GET

## 1. create

### request


* 字段

\(1\) param字段

| 参数 | 说明 |
| :--- | :--- |
| `_gp` | 接口方法所在组 |
| `_mt` | 接口方法名 |
| `courseDTO` | 课程信息\(json格式，内容见下文\) |

\(2\) param字段中的courseDTO字段

| 参数 | 类型 | 说明 |
| :--- | :--- | :--- |
| type | String | 课程类型 |
| sectionNumber | int | 课程节数 |
| title | String | 课程标题 |
| img | String | 课程缩略图\(OSS\) |
| videoId | String | 课程视频id\(VOD\) |
| detail | String | 课程详情文案 |
| speaker | String | 主讲人 |
| playTimes | int | 播放次数 |
| status | int | 课程状态\(0/1\) |

样例：

```json
{
"type": "测试课程",
"sectionNumber": 10,
"title": "这是一个测试课程",
"img": "https://oss-unimall-prd.oss-cn-hangzhou.aliyuncs.com/test/avatar.jpg",
"videoId": "fc239ebf28994485a502bfd0c8f241b5",
"detail": "课程文案内容测试",
"speaker": "主讲人John",
"playTimes": 100,
"status": 1
}
```

\(3\) header字段

| 参数 | 说明 |
| :--- | :--- |
| `ADMINTOKEN` | admin token |

* 样例

```http
GET /m.api?_gp=admin.course&_mt=create&courseDTO={
  "type": "测试课程3",
  "sectionNumber": 12,
  "title": "这是一个测试课程3",
  "img": "https://oss-unimall-prd.oss-cn-hangzhou.aliyuncs.com/test/avatar.jpg",
  "videoId": "xxx",
  "detail": "课程文案内容测试3",
  "speaker": "主讲人Sigma",
  "playTimes": 100,
  "status": 0
}
 HTTP/1.1
Host: 127.0.0.1:8080
ADMINTOKEN: a98385b0150a4361acfd0a6e0b2216fe
Content-Type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW

----WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="videoid"

61b510b00a354567b6e04cc489cd47fd
----WebKitFormBoundary7MA4YWxkTrZu0gW
```

### response

* response body

| 参数 | 类型 | 说明 |
| :--- | :--- | :--- |
| data | String | / |
| errmsg | String | 错误信息（成功时为“成功”） |
| errno | int | 错误码（成功时为200） |
| timestamp | long | 时间戳 |

* 成功时

```json
{
    "data": "ok",
    "errmsg": "成功",
    "errno": 200,
    "timestamp": 1590462373477
}
```

* 错误时

```json
{
    "errmsg": " 管理员尚未登录",
    "errno": 10006,
    "timestamp": 1590471926085
}
```

courseDTO参数传递错误：
```json
{
    "errmsg": "系统未知异常",
    "errno": 10000,
    "timestamp": 1590472380829
}
```

## 2. detail

### request

* 字段

\(1\) param字段

| 参数 | 说明 |
| :--- | :--- |
| `_gp` | 接口方法所在组 |
| `_mt` | 接口方法名 |
| `courseId` | 课程Id |

\(2\) header字段

| 参数 | 说明 |
| :--- | :--- |
| `ADMINTOKEN` | admin token |

* 样例

```http
GET /m.api?_gp=admin.course&_mt=detail&courseId=1236791 HTTP/1.1
Host: localhost:8080
ADMINTOKEN: 0914700397574545ae364f63bbdd9d97
```

### response

* response body

内容格式见下文样例。
Json中的data字段和上文create接口中的request param的courseDTO字段相似，多了`id`,`gmtCreate`,`gmtUpdate`三个字段。

| 参数 | 类型 | 说明 |
| :--- | :--- | :--- |
| id | long | 课程id |
| gmtCreate | long | 创建时间 |
| gmtUpdate | long | 修改时间 |


* 成功时

```json
{
    "data": {
        "detail": "课程文案内容测试2",
        "gmtCreate": 1590429445000,
        "gmtUpdate": 1590429445000,
        "id": 1236791,
        "img": "https://oss-unimall-prd.oss-cn-hangzhou.aliyuncs.com/test/avatar.jpg",
        "playTimes": 100,
        "sectionNumber": 11,
        "speaker": "主讲人Sam",
        "status": 0,
        "title": "这是一个测试课程2",
        "type": "测试课程2",
        "videoId": "xxx"
    },
    "errmsg": "成功",
    "errno": 200,
    "timestamp": 1590472549163
}
```

* 错误时

```json
{
    "errmsg": "课程不存在",
    "errno": 60002,
    "timestamp": 1590474063429
}
```

```json
{
    "errmsg": "参数校验失败",
    "errno": 10002,
    "timestamp": 1590474091335
}
```

## 3. list

### request

\(1\) param字段

| 参数 | 说明 |
| :--- | :--- |
| `_gp` | 接口方法所在组 |
| `_mt` | 接口方法名 |
| `page` | 页码(可选，默认１) |
| `limit` | 页面长度(可选，默认20) |
| `type` | 课程类别 |
| `title` | 课程标题 |
| `status` | 课程状态(0/1) |


\(2\) header字段

| 参数 | 说明 |
| :--- | :--- |
| `ADMINTOKEN` | admin token |

* 样例

```http
GET /m.api?_gp=admin.course&_mt=list&page=2&limit=2&type=&title=&status= HTTP/1.1
Host: localhost:8080
ADMINTOKEN: dbc758f821a741d490dfd978e455cdff
```

### response

* response body

内容格式见下文样例。

data字段的格式:

| 参数 | 类型 | 说明 |
| :--- | :--- | :--- |
| code | int | / |
| count | int | 符合查询条件的结果总数量 |
| items | json | 见下文 |
| msg | int | 信息 |
| pageNo | int | 页码 |
| pageSize | int | 页面长度 |
| total | int | 符合查询条件的结果总数量 |
| totalPageNo | int | 符合查询条件的结果总页数 |

Json中的items字段和上文detail接口中的response body的data字段相同。


```json
{
    "data": {
        "code": 0,
        "count": 5,
        "items": [
            {
                "detail": "课程文案内容测试",
                "gmtCreate": 1590397528000,
                "gmtUpdate": 1590397528000,
                "id": 1236790,
                "img": "https://oss-unimall-prd.oss-cn-hangzhou.aliyuncs.com/test/avatar.jpg",
                "playTimes": 100,
                "sectionNumber": 10,
                "speaker": "主讲人John",
                "status": 1,
                "title": "这是一个测试课程",
                "type": "测试课程",
                "videoId": "fc239ebf28994485a502bfd0c8f241b5"
            },
            {
                "detail": "课程文案内容测试2",
                "gmtCreate": 1590429445000,
                "gmtUpdate": 1590429445000,
                "id": 1236791,
                "img": "https://oss-unimall-prd.oss-cn-hangzhou.aliyuncs.com/test/avatar.jpg",
                "playTimes": 100,
                "sectionNumber": 11,
                "speaker": "主讲人Sam",
                "status": 0,
                "title": "这是一个测试课程2",
                "type": "测试课程2",
                "videoId": "xxx"
            }
        ],
        "msg": "第1页,共5条",
        "pageNo": 1,
        "pageSize": 2,
        "total": 5,
        "totalPageNo": 3
    },
    "errmsg": "成功",
    "errno": 200,
    "timestamp": 1590475843923
}
```


## 4. delete

### request

* 字段

\(1\) param字段

| 参数 | 说明 |
| :--- | :--- |
| `_gp` | 接口方法所在组 |
| `_mt` | 接口方法名 |
| `courseId` | 课程Id |

\(2\) header字段

| 参数 | 说明 |
| :--- | :--- |
| `ADMINTOKEN` | admin token |

* 样例

```http
GET /m.api?_gp=admin.course&_mt=delete&courseId=1236793 HTTP/1.1
Host: localhost:8080
ADMINTOKEN: 9801cab4e9004c6db161379757bc0932
```

### response

* 成功时

```json
{
    "data": "ok",
    "errmsg": "成功",
    "errno": 200,
    "timestamp": 1590479012251
}
```

* 错误时

```json
{
    "errmsg": "课程不存在",
    "errno": 60002,
    "timestamp": 1590479190975
}
```

## 5. batchDelete

### request

* 字段

\(1\) param字段

| 参数 | 说明 |
| :--- | :--- |
| `_gp` | 接口方法所在组 |
| `_mt` | 接口方法名 |
| `courseIdsJson` | 课程Id的List |

\(2\) header字段

| 参数 | 说明 |
| :--- | :--- |
| `ADMINTOKEN` | admin token |


* 样例

```http
GET /m.api?_gp=admin.course&_mt=batchDelete&courseIdsJson=[1236798, 1236799] HTTP/1.1
Host: localhost:8080
ADMINTOKEN: 065caa8ad07b4c22ac3309ce83783df1
```

### response

* 成功时

```json
{
    "data": "ok",
    "errmsg": "成功",
    "errno": 200,
    "timestamp": 1590479012251
}
```

* 错误时

```json
{
    "errmsg": "课程不存在",
    "errno": 60002,
    "timestamp": 1590479190975
}
```








