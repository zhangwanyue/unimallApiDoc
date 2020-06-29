### SpuDTO

| 参数 | 原类型 | Json中的类型 | 说明 |
| :--- | :--- | :--- | :--- |
| id | Long | Number | / |
| gmtCreate | Date | String | / |
| gmtUpdate | Date | String | / |
| **shortVideo**(新增字段) | String | String | 短视频链接\(oss\) |
| **type**(新增字段) | Integer | Number | 0:普通商品; 1:黄金会员专属商品; 2:铂金会员专属商品; 3:钻石会员专属商品; 4:黄金会员; 5:铂金会员; 6:钻石会员 |
| originalPrice | Integer | Number | 原价 |
| price | Integer | Number | 价格 |
| vipPrice | Integer | Number | 会员价格 |
| stock | Integer | Number | ?? |
| sales | Integer | Number | 销量 |
| title | String | String | 商品标题 |
| img | String | String\(oss\) | 主图 |
| imgList | `List<String>` | Array\(String\) | 商品详情图 |
| detail | String | String | 商品详情 |
| description | String | String | 商品一句话介绍 |
| categoryId | String | String | 所在最细分的类别 |
| categoryIds | `List<Long>` | Array\(Number\) | 所在全部类别（包括最细分类别的所有父类\) |
| attributeList | `List<SpuAttributeDO>` | Array\(SpuAttributeDO\) | 属性列表 |
| appraisePage | `Page<AppraiseResponseDTO>` | Array\(Number\) | 商品评价 |
| groupShop | GroupShopDTO | GroupShopDTO | 团购信息 |
| unit | String | String | 单位 |
| freightTemplateId | Long | Number | 运单模板id |
| freightTemplate | FreightTemplateDTO | FreightTemplateDTO | 运单模板 |
| collect | Boolean | Boolean | ?? |
| status | Integer | Number | 商品状态 |

### 样例

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
    "gmtCreate": 1571288272000,
    "gmtUpdate": 1571288272000,
    "id": 1236789,
    "img": "https://easycampus-asset.oss-cn-shenzhen.aliyuncs.com/nopic.png",
    "imgList": [],
    "originalPrice": 130,
    "price": 130,
    "sales": 0,
    "skuList": [
        {
            "barCode": "6931893420009",
            "freezeStock": 0,
            "gmtCreate": 1571288272000,
            "gmtUpdate": 1571288272000,
            "id": 2798,
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

