下文所有接口:

* url

`xxx:8080/m.api`

* 请求类型

`GET`或者`POST`都可以。下文只选择了一种请求为例说明。**如果使用`POST`请求，就把下文所写的`GET`请求`url`中的`param`放入`POST`请求的`form-data`中就可以了。反之亦然。**

# 1.getCoursePage

## request

* param说明

| 参数 | 类型 | 说明 |
| :--- | :--- | :--- |
| `_gp` | String | 接口方法所在组,此处填course |
| `_mt` | String | 接口方法名，此处填getCoursePage |
| pageNo | int | 页码(可选，默认1) |
| pageSize | int | 页面长度(可选，默认10) |
| level | int | 会员等级(对应用户等级：0.普通 1-3.VIP会员)(可选) |
| title | String | 课程标题(可选) |

* 样例

```
GET 
--url /m.api?_gp=course&_mt=getCoursePage&pageNo=1&pageSize=2&level=0&title= 
--header access_token=undefined
```

## response

* 字段格式

| 参数 | 类型 | 说明 |
| :--- | :--- | :--- |
| data | String | / |
| errmsg | String | 错误信息（成功时为“成功”） |
| errno | int | 错误码（成功时为200） |
| timestamp | long | 时间戳 |

* data字段格式

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

* items字段格式

| 参数 | 类型 | 说明 |
| :--- | :--- | :--- |
| id | long | 课程id |
| gmtCreate | long | 创建时间 |
| gmtUpdate | long | 修改时间 |
| type | String | 课程类型 |
| level | int | 会员等级（对应用户等级：0.普通 1-3.VIP会员） |
| sectionNumber | int | 课程节数 |
| title | String | 课程标题 |
| img | String | 课程缩略图\(OSS\) |
| videoId | String | 课程视频id\(VOD\) |
| detail | String | 课程详情文案 |
| speaker | String | 主讲人 |
| playTimes | int | 播放次数 |
| status | int | 课程状态\(0/1\) |


* 样例

```json
{
    "data": {
        "code": 0,
        "count": 1,
        "items": [
            {
                "detail": "课程文案内容测试2",
                "gmtCreate": 1588262400000,
                "gmtUpdate": 1593685263000,
                "id": 1,
                "img": "https://oss-unimall-prd.oss-cn-hangzhou.aliyuncs.com/test/avatar.jpg",
                "level": 0,
                "playTimes": 100,
                "sectionNumber": 10,
                "speaker": "主讲人John",
                "status": 0,
                "title": "这是一个测试课程",
                "type": "测试课程",
                "videoId": "fc239ebf28994485a502bfd0c8f241b5"
            }
        ],
        "msg": "第1页,共1条",
        "pageNo": 1,
        "pageSize": 2,
        "total": 1,
        "totalPageNo": 1
    },
    "errmsg": "成功",
    "errno": 200,
    "timestamp": 1593709377193
}
```