# 房天下OPENAPI文档
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

## 接口文档
[参见wiki](https://github.com/fangjjy/openapi_document/wiki/%E5%87%BA%E5%94%AE%E4%BD%8F%E5%AE%85%E6%88%BF%E6%BA%90%E5%AF%BC%E5%85%A5%E6%8E%A5%E5%8F%A3)

## SDK下载
### 1.Java SDK

  [下载地址](https://github.com/fangjjy/openapi_sdk_java) 敬请期待

### 2.PHP SDK

敬请期待



## FAQ
请参考 [FAQ](https://github.com/fangjjy/openapi_document/wiki/FAQ)

