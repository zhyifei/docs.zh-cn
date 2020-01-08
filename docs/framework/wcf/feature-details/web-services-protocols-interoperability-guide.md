---
title: Web 服务协议互操作性指南
ms.date: 03/30/2017
ms.assetid: f2981678-ebdb-433d-899b-467f7df95fb2
ms.openlocfilehash: 1b949880b3ebbaf121b79a958d17cf5708affcf3
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636141"
---
# <a name="web-services-protocols-interoperability-guide"></a>Web 服务协议互操作性指南

Windows Communication Foundation （WCF）实现了许多 Web 服务协议。 这些协议中有许多都包含大量留给实施者来决定的选项和扩展点。 本主题提供 WCF 实现的 Web 服务协议的列表。 本节中的其他主题介绍每个受支持的协议的实现详细信息。

## <a name="web-services-protocols-implemented-by-wcf"></a>WCF 实现的 Web 服务协议

WCF 通过协定功能，通过通道和 Web 服务应用程序协议提供对 Web 服务（WS）基础结构协议的支持。 通过 XML 架构描述语言 1.0 (XSD) 和 Web 服务描述语言 (WSDL) 1.1 完成应用程序协议的互操作性。

基础结构协议互操作性由 WS-* 规范提供。 WCF 通道提供对许多 WS\* 基础结构协议的支持。 WCF 信道使用绑定元素进行配置。 下表包含由各种 WCF 绑定元素实现的 WS\* 基础结构协议的完整列表。

<xref:System.ServiceModel.Channels.HttpTransportBindingElement> 支持下表中的规范。

|规范/文档|链接|
|-----------------------------|----------|
|HTTP 1.1|[RFC 2616](https://www.rfc-editor.org/rfc/rfc2616.txt)|
|SOAP 1.1 HTTP 绑定|[简单对象访问协议（SOAP） 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)，第7部分|
|SOAP 1.2 HTTP 绑定|[SOAP 版本1.2 第2部分：附属（第二版）](https://www.w3.org/TR/soap12-part2/)，第7部分|

<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> 和 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> 支持下表中的规范。

|规范/文档|链接|
|-----------------------------|----------|
|XML|[可扩展标记语言（XML）1.0 （第四版）](https://www.w3.org/TR/REC-xml/)|
|SOAP 1.1|[简单对象访问协议（SOAP）1。1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)|
|SOAP 1.2 核心|[SOAP 版本1.2 第1部分：消息传递框架（第二版）](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)|
|WS-Addressing 2004/08|[Web 服务寻址（WS-ADDRESSING）](https://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/)|
|W3C Web 服务寻址 1.0 - 核心|[Web 服务寻址 1.0-核心](https://www.w3.org/TR/2006/REC-ws-addr-core-20060509/)|
|W3C Web 服务寻址 1.0 - SOAP 绑定|[Web 服务寻址 1.0-SOAP 绑定](https://www.w3.org/TR/2006/REC-ws-addr-soap-20060509/)|
|W3C Web 服务寻址 1.0 - WSDL 绑定*|[Web 服务寻址 1.0-WSDL 绑定](https://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/)|
|W3C Web 服务寻址 1.0 元数据|[Web 服务寻址 1.0-元数据](https://www.w3.org/TR/ws-addr-metadata/)|
|WSDL SOAP1.1 绑定|[Web 服务描述语言（WSDL）1。1](https://www.w3.org/TR/wsdl/)|
|WSDL SOAP1.2 绑定|[用于 SOAP 1.2 的 WSDL 1.1 绑定扩展](https://www.w3.org/Submission/wsdl11soap12/)|

<xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> 支持下表中的规范。

|规范/文档|链接|
|-----------------------------|----------|
|XOP|[XML 二进制优化打包](https://www.w3.org/TR/xop10/)|
|MTOM + SOAP1.2 绑定|[SOAP 消息传输优化机制](https://www.w3.org/TR/soap12-mtom/)|
|MTOM SOAP 1.1 绑定|[MTOM 1.0 的 SOAP 1.1 绑定](https://www.w3.org/Submission/soap11mtom10/)|
|MTOM WS-PolicyAssertions|[MTOM 序列化策略断言（MTOMPolicy）](https://www.w3.org/Submission/WS-MTOMPolicy/)|

<xref:System.ServiceModel.Channels.SecurityBindingElement> 支持下表中的规范。

|规范/文档|链接|
|-----------------------------|----------|
|WSS：SOAP 消息安全 1.0|[Web Services 安全性： SOAP 消息安全1。0](https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf)|
|WSS：用户名令牌配置文件 1.0|[Web Services 安全性 UsernameToken 配置文件1。0](https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf)<br /><br /> 需要 Password/@Type= PasswordText （默认值）|
|WSS：X.509 令牌配置文件 1.0|[Web Services 安全性 x.509 证书令牌配置文件](https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf)|
|WSS：SAML 1.1 令牌配置文件 1.0|[Web Services 安全性： SAML 令牌配置文件](https://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf)|
|WSS：SOAP 消息安全 1.1|[Web Services 安全性： SOAP 消息安全1。1](https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf)|
|WSS 用户名令牌配置文件 1.1|[Web Services 安全性 UsernameToken 配置文件1。1](https://www.oasis-open.org/committees/download.php/16782/wss-v1.1-spec-os-UsernameTokenProfile.pdf)<br /><br /> 不实现基于密码的密钥派生；<br /><br /> 需要 Password/@Type= PasswordText （默认值）|
|WSS：X509 令牌配置文件 1.1|[Web Services 安全性 x.509 证书令牌配置文件1。1](https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf)|
|WSS：Kerberos 令牌配置文件 1.1|[Web Services 安全性 Kerberos 令牌配置文件1。1](https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf)|
|WSS：SAML 1.1 令牌配置文件 1.1|[Web Services 安全性 SAML 令牌配置文件1。1](https://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf)|
|WS-Secure 对话|[Web 服务安全对话语言](https://specs.xmlsoap.org/ws/2005/02/sc/ws-secureconversation.pdf)|
|WS-Trust 1.4|[Web 服务信任语言](https://docs.oasis-open.org/ws-sx/ws-trust/200802)|
|WS-SecurityPolicy 2005/07|[Web 服务安全对话语言](https://specs.xmlsoap.org/ws/2005/02/sc/ws-secureconversation.pdf)<br /><br /> 已根据提交到 OASIS WS-SX 技术委员会的勘误表进行了修正。<br /><br /> [ws-rm 消息](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html)|
|WS-ReliableMessaging 1.1|[可靠消息传送协议版本 1.1](reliable-messaging-protocol-version-1-1.md)|

<xref:System.ServiceModel.Channels.TransactionFlowBindingElement> 支持下表中的规范。

|规范/文档|链接|
|-----------------------------|----------|
|WS-Coordination|[Web 服务协调](https://docs.microsoft.com/previous-versions/ms951231(v=msdn.10))|
|WS-AtomicTransaction|[Web 服务原子事务](https://specs.xmlsoap.org/ws/2004/10/wsat/wsat.pdf)|

<xref:System.ServiceModel.Description.MetadataExporter>、<xref:System.ServiceModel.Description.MetadataImporter>、<xref:System.ServiceModel.Description.WsdlExporter>、<xref:System.ServiceModel.Description.WsdlImporter> 和 <xref:System.ServiceModel.Description.MetadataResolver> 类支持以下元数据规范：

- [XML 架构第1部分：结构第二版](https://www.w3.org/TR/xmlschema-1/)

- [XML 架构第2部分：数据类型第二版](https://www.w3.org/TR/xmlschema-2/)

- [WSDL 1.1](https://www.w3.org/TR/wsdl/)

- [WS 策略1。2](https://www.w3.org/Submission/2006/SUBM-WS-Policy-20060425/)

- [WS 策略1。5](https://www.w3.org/TR/ws-policy/)

- [WS-PolicyAttachment 1.2](https://www.w3.org/Submission/2006/SUBM-WS-PolicyAttachment-20060425/)

- [WS-MetadataExchange 1.1](https://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)

- [用于元数据检索的 WS 传输获取](https://www.w3.org/Submission/2006/SUBM-WS-Transfer-20060315/)

此外，以下互操作性配置文件通过 WCF 实现：

- [基本配置文件1。1](http://www.ws-i.org/Profiles/BasicProfile-1.1-2004-08-24.html)

- [简单 SOAP 绑定1。0](http://www.ws-i.org/Profiles/SimpleSoapBindingProfile-1.0-2004-08-24.html)

- [基本安全配置文件1.0 工作草案](http://www.ws-i.org/Profiles/BasicSecurityProfile-1.0-2006-03-29.html)

## <a name="see-also"></a>另请参阅

- [系统提供的互操作性绑定支持的 Web 服务协议](web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [消息协议](messaging-protocols.md)
- [数据协定架构引用](data-contract-schema-reference.md)
- [WSDL 和策略](wsdl-and-policy.md)
- [安全协议](security-protocols.md)
- [可靠消息传送协议版本 1.0](reliable-messaging-protocol-version-1-0.md)
- [可靠消息传送协议版本 1.1](reliable-messaging-protocol-version-1-1.md)
- [事务协议](transaction-protocols.md)
- [上下文交换协议](context-exchange-protocol.md)
