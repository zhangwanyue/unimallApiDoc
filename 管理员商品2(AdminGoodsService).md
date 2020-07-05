# 修改接口

## 1.create

### request

request中新增参数`spuOuterDTO`:

```sql
CREATE TABLE `unimall_spu_outer` (
  `id` bigint(20) NOT NULL AUTO_INCREMENT,
  `spu_id` bigint(20) NOT NULL,
  `gmt_start` datetime NOT NULL COMMENT '商品生效时间',
  `gmt_end` datetime NOT NULL COMMENT '商品失效时间',
  `outer_store_name` varchar(255) DEFAULT NULL, # 外链店铺名称
  `outer_store_url` varchar(255) DEFAULT NULL, # 外链店铺链接
  `outer_comment_url` varchar(255) DEFAULT NULL, # 外链评论地址
  `outer_spu_usr_url` varchar(255) DEFAULT NULL, # 外链商品地址（客户自购）
  `outer_spu_usr_price` int(11) NOT NULL, # 外链商品价格（客户自购）
  `outer_spu_recommend_url` varchar(255) DEFAULT NULL, # 外链商品地址（客户导购）
  `outer_spu_recommend_price` int(11) NOT NULL, # 外链商品价格（客户导购）
  `spu_type` int(11) NOT NULL, # 商品分组（1.自营商品 2.淘宝商品 3.京东商品）
  `promotion_30_days` int(11) NOT NULL, # 30天推广量
  `commission_rate` int(11) NOT NULL, # 佣金比例. 1234表示12.34%
  `gmt_update` datetime NOT NULL,
  `gmt_create` datetime NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=100 DEFAULT CHARSET=utf8mb4;
```

`spuOuterDTO`参数格式：

```json
{
  "commissionRate": 1234,
  "gmtEnd": 1602662110000,
  "gmtStart": 1602662110000,
  "outerCommentUrl": "comment_url1",
  "outerSpuRecommendPrice": 1002,
  "outerSpuRecommendUrl": "spu_recommend_url1",
  "outerSpuUsrPrice": 1001,
  "outerSpuUsrUrl": "spu_usr_url1",
  "outerStoreName": "store name1",
  "outerStoreUrl": "store_url1",
  "promotion30Days": 100,
  "spuId": 1236789,
  "spuTyte": 0
}
```

### 请求样例：

```
GET 
--url /m.api?_gp=admin.goods&_mt=create&spuDTO={   "shortVideo": "xxx",   "type": 1,   "appraisePage": {     "code": 0,     "count": 0,     "items": [],     "msg": "第1页,共0条",     "pageNo": 1,     "pageSize": 10,     "total": 0,     "totalPageNo": 0   },   "attributeList": [],   "categoryId": 1036524,   "categoryIds": [     1036524,     1036523,     1036517   ],   "collect": false,   "description": "介绍",   "detail": "正宗咪咪虾条18g",   "freightTemplate": {     "freightTemplateCarriageDOList": [],     "freightTemplateDO": {       "defaultContinueMoney": 0,       "defaultContinueNum": 1,       "defaultFirstMoney": 0,       "defaultFirstNum": 1,       "defaultFreePrice": 0,       "deliveryDeadline": 4,       "gmtUpdate": 1566363169000,       "id": 13,       "spuLocation": "重庆",       "templateName": "全国包邮2"     }   },   "freightTemplateId": 13,   "img": "https://easycampus-asset.oss-cn-shenzhen.aliyuncs.com/nopic.png",   "imgList": [     "https://easycampus-asset.oss-cn-shenzhen.aliyuncs.com/nopic.png"   ],   "originalPrice": 130,   "price": 130,   "skuList": [     {       "barCode": "6931893420023",       "originalPrice": 130,       "price": 130,       "spuId": 1236789,       "stock": 112,       "title": "正宗咪咪虾条18g",       "vipPrice": 130     }   ],   "status": 1,   "stock": 112,   "title": "正宗咪咪虾条18g",   "unit": "件",   "vipPrice": 130 }&adminId=undefined&spuOuterDTO={   "commissionRate": 1234,   "gmtEnd": 1602662110000,   "gmtStart": 1602662110000,   "outerCommentUrl": "comment_url1",   "outerSpuRecommendPrice": 1002,   "outerSpuRecommendUrl": "spu_recommend_url1",   "outerSpuUsrPrice": 1001,   "outerSpuUsrUrl": "spu_usr_url1",   "outerStoreName": "store name1",   "outerStoreUrl": "store_url1",   "promotion30Days": 100,   "spuId": 1236789,   "spuTyte": 0 } 
--header access_token=undefined
```

# 新增接口

## 1.outerDetail

### request

```
GET 
--url /m.api?_gp=admin.goods&_mt=outerDetail&spuId=1236789&adminId=undefined 
--header access_token=undefined
```

### response

```json
{
    "data": {
        "commissionRate": 1234,
        "gmtEnd": 1602662110000,
        "gmtStart": 1602662110000,
        "id": 1,
        "outerCommentUrl": "comment_url1",
        "outerSpuRecommendPrice": 1002,
        "outerSpuRecommendUrl": "spu_recommend_url1",
        "outerSpuUsrPrice": 1001,
        "outerSpuUsrUrl": "spu_usr_url1",
        "outerStoreName": "store name1",
        "outerStoreUrl": "store_url1",
        "promotion30Days": 100,
        "spuId": 1236789,
        "spuTyte": 0
    },
    "errmsg": "成功",
    "errno": 200,
    "timestamp": 1593960204719
}
```



