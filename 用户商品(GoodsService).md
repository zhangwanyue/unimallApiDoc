## getGoods

#### 前端交互

返回值`data`字段新增两个字段：`shortVideo`，`type`

* 返回值数据样例：

```json
{
    "data": {
        "appraisePage": {
            "code": 0,
            "count": 0,
            "items": [],
            "msg": "第1页,共0条",
            "pageNo": 1,
            "pageSize": 10,
            "total": 0,
            "totalPageNo": 0
        },
        "attributeList": [],
        "categoryId": 1036524,
        "categoryIds": [
            1036524,
            1036523,
            1036517
        ],
        "collect": false,
        "description": "介绍",
        "detail": "正宗咪咪虾条18g",
        "freightTemplate": {
            "freightTemplateCarriageDOList": [],
            "freightTemplateDO": {
                "defaultContinueMoney": 0,
                "defaultContinueNum": 1,
                "defaultFirstMoney": 0,
                "defaultFirstNum": 1,
                "defaultFreePrice": 0,
                "deliveryDeadline": 4,
                "gmtUpdate": 1566363169000,
                "id": 13,
                "spuLocation": "重庆",
                "templateName": "全国包邮2"
            }
        },
        "freightTemplateId": 13,
        "gmtCreate": 1591006894000,
        "gmtUpdate": 1591011552000,
        "id": 1236791,
        "img": "https://easycampus-asset.oss-cn-shenzhen.aliyuncs.com/nopic.png",
        "imgList": [
            "https://easycampus-asset.oss-cn-shenzhen.aliyuncs.com/nopic.png"
        ],
        "originalPrice": 130,
        "price": 130,
        "sales": 0,
        "shortVideo": "xxx",
        "skuList": [
            {
                "barCode": "6931893420011",
                "freezeStock": 0,
                "gmtCreate": 1591006894000,
                "gmtUpdate": 1591006894000,
                "id": 2801,
                "originalPrice": 130,
                "price": 130,
                "spuId": 1236791,
                "stock": 112,
                "title": "正宗咪咪虾条18g",
                "vipPrice": 130
            }
        ],
        "status": 1,
        "stock": 112,
        "title": "正宗咪咪虾条18g",
        "type": 1,
        "unit": "件",
        "vipPrice": 130
    },
    "errmsg": "成功",
    "errno": 200,
    "timestamp": 1591012380277
}
```

## getGoodsPage

#### 前端交互

返回值`data`字段中的`items`字段新增两个字段：`shortVideo`，`type`

* 返回值数据样例

```json
{
    "data": {
        "code": 0,
        "count": 18,
        "items": [
            {
                "categoryId": 1036524,
                "description": "介绍",
                "freightTemplateId": 13,
                "id": 1236791,
                "img": "https://easycampus-asset.oss-cn-shenzhen.aliyuncs.com/nopic.png",
                "originalPrice": 130,
                "price": 130,
                "sales": 0,
                "shortVideo": "xxx",
                "status": 1,
                "title": "正宗咪咪虾条18g",
                "type": 1,
                "unit": "件",
                "vipPrice": 130
            },
            {
                "categoryId": 1036524,
                "description": "介绍",
                "freightTemplateId": 13,
                "id": 1236787,
                "img": "https://easycampus-asset.oss-cn-shenzhen.aliyuncs.com/nopic.png",
                "originalPrice": 208,
                "price": 208,
                "sales": 0,
                "status": 1,
                "title": "美汁源果粒橙450ml",
                "type": 0,
                "unit": "瓶",
                "vipPrice": 208
            }
        ],
        "msg": "第1页,共18条",
        "pageNo": 1,
        "pageSize": 2,
        "total": 18,
        "totalPageNo": 9
    },
    "errmsg": "成功",
    "errno": 200,
    "timestamp": 1591012306154
}
```