# 房天下OPENAPI文档
本文档为房天下经纪云OPENAPI的使用说明文档，主要针对经纪云OPENAPI接口的调用方法、数据传输格式、数据返回格式进行描述。用于帮助接入公司现有的系统快速集成经纪云功能。

经纪云OPENAPI所提供的功能是在现有经纪云功能的范围之内。

使用经纪云OPENAPI，客户按照经纪云要求的使用说明及技术规则发送给指定的OPENAPI接口。以供内部应用和第三方应用程序使用，用于经纪云和外部系统的数据交互和信息共享。

## 接入前的准备


1. 公司向经纪云提出接入申请，经纪云向用户提供接入授权的ID和秘钥。
2. 根据授权接口文档，了解经纪云OPENAPI的加密方式和整理介绍。
3. 查看经纪云openapi房源接口等操作文档，了解要使用的功能接口。

## 接口调用流程

<img src="https://raw.githubusercontent.com/fangjjy/openapi_document/master/doc_images/authorizationprocess.jpg" width=600 height=900 />

## 接口的服务地址

南方城市：*http://openapi.agents.fang.com*

北方城市：*http://openapi.agentn.fang.com*

**服务地址的选取：**


1. 可以参考经纪云南北方城市分布.xlsx这个文档，根据经纪人所在城市确定服务接口地址。


2. 也可以根据授权接口返回的URL作为请求的接口地址（请参考授权接口文档中的描述），之后的OPENAPI请求使用该地址即可。


## 接口的授权认证

从V2.0.0版本开始，经纪云OPENAPI采用OAuth2.0授权方式（**之前版本的授权方式可兼容**，但是建议升级修改为新授权方式）。

### 请求在header中附带授权信息
#### 示例 POST请求 header

```
Token:0B81664A55BB06543E11A83E7EB4F2A8066BD7ECD91A6FB2A209F05C8769491436B71E6360660C5AC17A419A1429B0B26C7482F6C2C3106922617F1FC5BE
KeyId:60122333234556
DataType:json
Content-Type:application/x-www-form-urlencoded
```

<font color="#dd0000">注意：post请求目前只支持form提交</font>


## SDK下载
### 1.Java SDK

  [下载地址](https://github.com/fangjjy/openapi_sdk_java) 敬请期待

### 2.PHP SDK

敬请期待


## FAQ

敬请期待
