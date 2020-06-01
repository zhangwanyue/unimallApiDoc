下文所有接口:

* url

`xxx:8080/m.api`

* 请求类型

`GET`或者`POST`都可以。下文只选择了一种请求为例说明。**如果使用`POST`请求，就把下文所写的`GET`请求`url`中的`param`放入`POST`请求的`form-data`中就可以了。反之亦然。**

* 参数

`_gp=admin.goods`

## create

`_mt=create`

#### `spuDTO`参数要点

（这条是写给我自己看的，前端应该不需要注意这些点，本来应该就是满足的）

* `skuList`不能为空
* `gmtUpdate`字段不需要
* `gmtCreate`字段不需要
* `sales`字段不需要
* `id`字段不需要
* skuDO中的`id`,`gmtUpdate`,`gmtCreate`,`freezeStock`字段也不需要
* skuDO中的`barcode`不能重复
* `imgList`不能为空

#### 前端交互

参数`spuDTO`新增两个字段：`shortVideo`，`type`

* `spuDTO`样例：

```json
{
  "shortVideo": "xxx",
  "type": 1,
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
  "img": "https://easycampus-asset.oss-cn-shenzhen.aliyuncs.com/nopic.png",
  "imgList": [
    "https://easycampus-asset.oss-cn-shenzhen.aliyuncs.com/nopic.png"
  ],
  "originalPrice": 130,
  "price": 130,
  "skuList": [
    {
      "barCode": "6931893420011",
      "originalPrice": 130,
      "price": 130,
      "spuId": 1236789,
      "stock": 112,
      "title": "正宗咪咪虾条18g",
      "vipPrice": 130
    }
  ],
  "status": 1,
  "stock": 112,
  "title": "正宗咪咪虾条18g",
  "unit": "件",
  "vipPrice": 130
}
```

## getSpuBigTree

`_mt=getSpuBigTree`

#### 前端交互

没有需要修改的

## edit

`_mt=edit`

#### 前端交互

参数`spuDTO`新增两个字段：`shortVideo`，`type`

* `spuDTO`样例:

```json
{
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
  "gmtCreate": 1590997614000,
  "gmtUpdate": 1590997614000,
  "id": 1236790,
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
      "gmtCreate": 1590997614000,
      "gmtUpdate": 1590997614000,
      "id": 2800,
      "originalPrice": 130,
      "price": 130,
      "spuId": 1236790,
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
}
```

## list

`_mt=list`

#### 前端交互

返回值`data`字段的`items`字段新增两个字段：`shortVideo`，`type`

* 返回值数据样例

```json
{
    "data": {
        "code": 0,
        "count": 1,
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
                "title": "正宗咪咪虾条18g",
                "type": 1,
                "unit": "件",
                "vipPrice": 130
            }
        ],
        "msg": "第1页,共1条",
        "pageNo": 1,
        "pageSize": 20,
        "total": 1,
        "totalPageNo": 1
    },
    "errmsg": "成功",
    "errno": 200,
    "timestamp": 1591013000991
}
```

## detail 

`_mt=detail`

#### 前端交互

返回值`data`字段新增两个字段：`shortVideo`，`type`

* 返回值数据样例

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
    "timestamp": 1591012673807
}
```

## delete

`_mt=delete`

#### 前端交互

没有需要修改的

## batchDelete

`_mt=batchDelete`

#### 前端交互

没有需要修改的

## freezeOrActivation

`_mt=freezeOrActivation`

#### 前端交互

返回值`data`字段新增两个字段：`shortVideo`，`type`

* 返回值数据样例

```json
{
    "data": {
        "categoryId": 1036524,
        "description": "介绍",
        "detail": "正宗咪咪虾条18g",
        "freightTemplateId": 13,
        "gmtCreate": 1591006894000,
        "gmtUpdate": 1591013099311,
        "id": 1236791,
        "img": "https://easycampus-asset.oss-cn-shenzhen.aliyuncs.com/nopic.png",
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
        "status": 0,
        "title": "正宗咪咪虾条18g",
        "type": 1,
        "unit": "件",
        "vipPrice": 130
    },
    "errmsg": "成功",
    "errno": 200,
    "timestamp": 1591013099291
}
```





