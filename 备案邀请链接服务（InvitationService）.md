下文所有接口:

* url

`xxx:8080/m.api`

* 请求类型

`GET`或者`POST`都可以。下文只选择了一种请求为例说明。**如果使用`POST`请求，就把下文所写的`GET`请求`url`中的`param`放入`POST`请求的`form-data`中就可以了。反之亦然。**

# 1. create

## request

#### 字段

\(1\) param字段

| 参数 | 说明 |
| :--- | :--- |
| `_gp` | 接口方法所在组 |
| `_mt` | 接口方法名 |
| `invitationDTO` | 备案邀请链接信息\(json格式，内容见下文\) |

\(2\) param字段中的invitationDTO字段

| 参数 | 类型 | 说明 |
| :--- | :--- | :--- |
| `pageNo` | int | 可省，默认1 |
| `pageSize` | int | 可省，默认10 |


#### 样例

```http
GET 
--url /m.api?_gp=invitation&_mt=getInvitationPage&pageNo=&pageSize= 
--header access_token=undefined
```

## response

#### response body

items中的参数：

| 参数 | 类型 | 说明 |
| :--- | :--- | :--- |
| `filing_invitation_link_tb` | String | 淘宝备案邀请链接 |
| `filing_invitation_link_jd` | String | 京东备案邀请链接 |
| `filing_invitation_link_vip` | String | 唯品会备案邀请链接 |


#### 样例

* 成功时

```json
{
    "data": {
        "code": 0,
        "count": 1,
        "items": [
            {
                "filingInvitationLinkJd": "xxx",
                "filingInvitationLinkTb": "xxx",
                "filingInvitationLinkVip": "123",
                "gmtCreate": 1594663344000,
                "gmtUpdate": 1594664241000,
                "id": 1236790
            }
        ],
        "msg": "第1页,共1条",
        "pageNo": 1,
        "pageSize": 10,
        "total": 1,
        "totalPageNo": 1
    },
    "errmsg": "成功",
    "errno": 200,
    "timestamp": 1594664359013
}
```

