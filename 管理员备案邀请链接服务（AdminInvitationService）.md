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
| `_gp` | 接口方法所在组（admin.invitation） |
| `_mt` | 接口方法名（create） |
| `invitationDTO` | 备案邀请链接信息\(json格式，内容见下文\) |

\(2\) param字段中的invitationDTO字段

| 参数 | 类型 | 说明 |
| :--- | :--- | :--- |
| `filing_invitation_link_tb` | String | 淘宝备案邀请链接（可省） |
| `filing_invitation_link_jd` | String | 京东备案邀请链接（可省） |
| `filing_invitation_link_vip` | String | 唯品会备案邀请链接（可省） |

样例：

```json
{
  "filing_invitation_link_tb": "xxx",
  "filing_invitation_link_jd": "xxx",
  "filing_invitation_link_vip": "xxx"
}
```

\(3\) header字段

| 参数 | 说明 |
| :--- | :--- |
| `ADMINTOKEN` | admin token |

#### 样例

```http
GET 
--url /m.api?_gp=admin.invitation&_mt=create&invitationDTO={   "filing_invitation_link_tb": "xxx",   "filing_invitation_link_jd": "xxx",   "filing_invitation_link_vip": "xxx" }&adminId=undefined 
--header access_token=undefined
```

## response

#### response body

| 参数 | 类型 | 说明 |
| :--- | :--- | :--- |
| data | String | / |
| errmsg | String | 错误信息（成功时为“成功”） |
| errno | int | 错误码（成功时为200） |
| timestamp | long | 时间戳 |

#### 样例

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

# 2. edit

## request

#### 字段

\(1\) param字段

| 参数 | 说明 |
| :--- | :--- |
| `_gp` | 接口方法所在组（admin.invitation） |
| `_mt` | 接口方法名（edit） |
| `invitationDTO` | 备案邀请链接信息\(json格式，内容见下文\) |

\(2\) param字段中的invitationDTO字段

样例：

```json
{
  "id": xxx,
  "filing_invitation_link_tb": "xxx",
  "filing_invitation_link_jd": "xxx",
  "filing_invitation_link_vip": "xxx"
}
```

\(3\) header字段

| 参数 | 说明 |
| :--- | :--- |
| `ADMINTOKEN` | admin token |

#### 样例

```http
GET 
--url /m.api?_gp=admin.invitation&_mt=edit&invitationDTO={   "id": 1236790,   "filing_invitation_link_tb": "xxx",   "filing_invitation_link_jd": "xxx",   "filing_invitation_link_vip": "123" }&adminId=undefined 
--header access_token=undefined
```

## response

#### response body

| 参数 | 类型 | 说明 |
| :--- | :--- | :--- |
| data | String | / |
| errmsg | String | 错误信息（成功时为“成功”） |
| errno | int | 错误码（成功时为200） |
| timestamp | long | 时间戳 |

#### 样例

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


