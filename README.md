﻿# 房天下OPENAPI文档
本文档为房天下经纪云OPENAPI的使用说明文档，主要针对经纪云OPENAPI接口的调用方法、数据传输格式、数据返回格式进行描述。用于帮助接入公司现有的系统快速集成经纪云功能。

经纪云OPENAPI所提供的功能是在现有经纪云功能的范围之内。适用范围包括新搜房帮、租房帮、办公帮、商铺帮。

使用经纪云OPENAPI，客户按照经纪云要求的使用说明及技术规则发送给指定的OPENAPI接口。以供内部应用和第三方应用程序使用，用于经纪云和外部系统的数据交互和信息共享。

## 接入前的准备

公司向经纪云提出接入申请，经纪云向用户提供接入授权的ID和秘钥。请参考  [申请接入](https://github.com/fangjjy/openapi_document/wiki/%E7%94%B3%E8%AF%B7%E6%8E%A5%E5%85%A5)


## 接口调用流程

<img src="https://raw.githubusercontent.com/fangjjy/openapi_document/master/doc_images/authorizationprocess.jpg" width=600 height=900 />

## 接口的服务地址

**服务地址的选取：**
不同的经纪人对应的服务接口地址不同，请按授权接口返回的url节点进行调用房源或其他接口，跨机房调用会导致很多问题，如接口超时，数据不一致，数据错误等。请参考 [服务地址](https://github.com/fangjjy/openapi_document/wiki/%E6%9C%8D%E5%8A%A1%E5%9C%B0%E5%9D%80)


## 接口的授权认证

从V2.0.0版本开始，经纪云OPENAPI采用OAuth2.0授权方式（**之前版本的授权方式可兼容**，但是建议升级修改为新授权方式）。请参考 [接口的授权](https://github.com/fangjjy/openapi_document/wiki/%E6%8E%A5%E5%8F%A3%E7%9A%84%E6%8E%88%E6%9D%83)

### 请求在header中附带授权信息
#### 示例 POST请求 header

```
Token:0B81664A55BB06543E11A83E7EB4F2A8066BD7ECD91A6FB2A209F05C8769491436B71E6360660C5AC17A419A1429B0B26C7482F6C2C3106922617F1FC5BE
KeyId:60122333234556
DataType:json
Content-Type:application/x-www-form-urlencoded
```

**注意：post请求目前只支持form提交**

接口调用请参见[文档](https://github.com/fangjjy/openapi_document/wiki/%E6%8E%A5%E5%8F%A3%E7%9A%84%E8%B0%83%E7%94%A8%E5%8F%8A%E7%A4%BA%E4%BE%8B)

## 接口文档
[参见wiki](https://github.com/fangjjy/openapi_document/wiki/%E5%87%BA%E5%94%AE%E4%BD%8F%E5%AE%85%E6%88%BF%E6%BA%90%E5%AF%BC%E5%85%A5%E6%8E%A5%E5%8F%A3)


***


## 重要版本更新

### V2.7.0
2019.03.05
1. 出售商铺录入、修改新增字段：使用面积、服务介绍 。
2. 出租商铺录入、修改新增字段：使用面积,服务介绍,入驻时间,起租期,免租期,转让方式,剩余租期,转让费。

### V2.6.0
2019.02.28
1. 出售写字楼录入、修改新增字段：使用面积、服务介绍 、平台标签。
2. 出售写字楼录入、修改新增字段：使用面积、服务介绍 、平台标签、起租日期。
3. 添加VR查询接口以及VR的绑定、解绑接口。


### V2.5.0
2018.12.13
### 住宅新增字段
1. 出售、出租新增房源字段。
2. 企管房源录入控制细化。

### V2.4.0
2018.09.17
### 导入房源推广配置迁移到企业后台
1. 导入房源是否到已推广配置功能迁移到企业后台，可以登录经纪云企业帐号，在后台配置房源导入到已发布/待发布。
2. 宁波支持核验码功能，参见房源录入修改接口。

### V2.3.0
2018.08.15
### 新增权限查询，修改图像上传格式、图片数量限制
1. 新增[权限查询](https://github.com/fangjjy/openapi_document/wiki/%E6%9D%83%E9%99%90%E6%9F%A5%E8%AF%A2%E6%8E%A5%E5%8F%A3)接口
2. 房源录入、修改、房源图片批量上传接口图像字段（image1-image7）格式修改，支持:[{"url":"url","name":name},{"url":"url","name":name}],url表示图片地址，name表示名称，原格式仍然支持，但不建议使用
3. 房源图片数量支持最多30张
4. [新版授权](https://github.com/fangjjy/openapi_document/wiki/%E6%8E%A5%E5%8F%A3%E7%9A%84%E6%8E%88%E6%9D%83)方式支持企业组织架构跨城市。如果使用旧版授权接口，需要升级到新版授权接口才能支持

### V2.2.0
#### 支持视频上传功能
1. 支持视频上传
2. 详情接口，返回房源描述字段

### V2.1.0
#### 增加多产品推广，包括新搜房帮，品牌公寓，新租房帮，商铺帮，办公帮。

接口字段调整如下：
1. 房源录入接口：传入参数增加推广产品字段：ptype 
2. 房源推广接口：传入参数增加推广产品字段：ptype 
3. 房源列表接口：传入参数增加查询列表字段：ptype  返回增加房源标题图字段photourl。
4. 住宅、别墅房源描述传参增加新字段（业主心态，社区配套，服务介绍，税费分析）。

### V2.0.0
#### 授权接口升级

1. 采用了新的OAuth2.0授权方式，兼容原api认证方式。
用户通过授权接口获取token，并保存。在token有效期时间内，通过在http请求header中加上token来访问OPENAPI。
2. 权限认证接口返回增加接口URL。
    该经纪人授权后请求的openapi接口地址请使用这个URL


**全部版本请参见** [版本更新](https://github.com/fangjjy/openapi_document/wiki/%E7%89%88%E6%9C%AC%E6%9B%B4%E6%96%B0)

***

## SDK下载
### 1.Java SDK

  [下载地址](https://github.com/fangjjy/openapi_sdk_java) 
 
### 2.Go SDK

  [下载地址](https://github.com/fangjjy/openapi-go-sdk)

### 3.PHP SDK

敬请期待


## FAQ
请参考 [FAQ](https://github.com/fangjjy/openapi_document/wiki/FAQ)

## 联系我们
Email: api@fang.com

