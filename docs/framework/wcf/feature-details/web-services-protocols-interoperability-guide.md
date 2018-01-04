---
title: "Web 服务协议互操作性指南"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2981678-ebdb-433d-899b-467f7df95fb2
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b962452b6127d259733418969f1fb7b5036b1e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="web-services-protocols-interoperability-guide"></a>Web 服务协议互操作性指南
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 实现许多 Web 服务协议。 这些协议中有许多都包含大量留给实施者来决定的选项和扩展点。 本主题介绍 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 实现的 Web 服务协议的列表。 本节中的其他主题介绍每个受支持的协议的实现详细信息。  
  
## <a name="web-services-protocols-implemented-by-wcf"></a>由 WCF 实现的 Web 服务协议  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 通过通道提供对 Web 服务 (WS) 基础结构协议的支持，并通过协定功能提供对 Web 服务应用程序协议的支持。 通过 XML 架构描述语言 1.0 (XSD) 和 Web 服务描述语言 (WSDL) 1.1 完成应用程序协议的互操作性。  
  
 基础结构协议互操作性由 WS-* 规范提供。 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]通道提供支持的 WS-一些\*基础结构协议。 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 通道使用绑定元素进行配置。 下表包含的完整列表的 WS-\*基础结构协议实现的各种[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]绑定元素。  
  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement> 支持下表中的规范。  
  
|规范/文档|Link|  
|-----------------------------|----------|  
|HTTP 1.1|[RFC 2616](http://go.microsoft.com/fwlink/?LinkId=90372)|  
|SOAP 1.1 HTTP 绑定|[简单对象访问协议 (SOAP) 1.1](http://go.microsoft.com/fwlink/?LinkId=90520)，第 7 节|  
|SOAP 1.2 HTTP 绑定|[SOAP 版本 1.2 第 2 部分： 附属 （第二版）](http://go.microsoft.com/fwlink/?LinkId=95329)，第 7 节|  
  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> 和 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> 支持下表中的规范。  
  
|规范/文档|Link|  
|-----------------------------|----------|  
|XML|[可扩展标记语言 (XML) 1.0 （第四个版本）](http://go.microsoft.com/fwlink/?LinkId=15139)|  
|SOAP 1.1|[简单对象访问协议 (SOAP) 1.1](http://go.microsoft.com/fwlink/?LinkId=96687)|  
|SOAP 1.2 核心|[SOAP 版本 1.2 第 1 部分： 消息传递框架 （第二版）](http://go.microsoft.com/fwlink/?LinkId=94664)|  
|WS-Addressing 2004/08|[Web 服务寻址 (Ws-addressing)](http://go.microsoft.com/fwlink/?LinkId=81239)|  
|W3C Web 服务寻址 1.0 - 核心|[Web 服务寻址 1.0-核心](http://go.microsoft.com/fwlink/?LinkId=96688)|  
|W3C Web 服务寻址 1.0 - SOAP 绑定|[Web 服务寻址 1.0-SOAP 绑定](http://go.microsoft.com/fwlink/?LinkId=96689)|  
|W3C Web 服务寻址 1.0 - WSDL 绑定*|[Web 服务寻址 1.0-WSDL 绑定](http://go.microsoft.com/fwlink/?LinkId=96690)|  
|W3C Web 服务寻址 1.0 元数据|[Web 服务寻址 1.0-元数据](http://www.w3.org/TR/ws-addr-metadata/)|  
|WSDL SOAP1.1 绑定|[Web 服务描述语言 (WSDL) 1.1](http://go.microsoft.com/fwlink/?LinkId=96160)|  
|WSDL SOAP1.2 绑定|[用于 SOAP 1.2 的 WSDL 1.1 绑定扩展](http://go.microsoft.com/fwlink/?LinkId=96691)|  
  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> 支持下表中的规范。  
  
|规范/文档|Link|  
|-----------------------------|----------|  
|XOP|[XML 二进制优化打包](http://go.microsoft.com/fwlink/?LinkId=96714)|  
|MTOM + SOAP1.2 绑定|[SOAP 消息传输优化机制](http://go.microsoft.com/fwlink/?LinkId=96713)|  
|MTOM SOAP 1.1 绑定|[用于 MTOM 1.0 SOAP 1.1 绑定](http://go.microsoft.com/fwlink/?LinkId=96712)|  
|MTOM WS-PolicyAssertions|即将发布。|  
  
 <xref:System.ServiceModel.Channels.SecurityBindingElement> 支持下表中的规范。  
  
|规范/文档|Link|  
|-----------------------------|----------|  
|WSS：SOAP 消息安全 1.0|[Web 服务安全： SOAP 消息安全 1.0](http://go.microsoft.com/fwlink/?LinkId=94684)|  
|WSS：用户名令牌配置文件 1.0|[Web 服务安全用户名令牌配置文件 1.0](http://go.microsoft.com/fwlink/?LinkId=95334)<br /><br /> 需要Password/@Type= PasswordText （默认值）|  
|WSS：X.509 令牌配置文件 1.0|[Web 服务安全 X.509 证书令牌配置文件](http://go.microsoft.com/fwlink/?LinkId=95335)|  
|WSS：SAML 1.1 令牌配置文件 1.0|[Web 服务安全： SAML 令牌配置文件](http://go.microsoft.com/fwlink/?LinkId=96693)|  
|WSS：SOAP 消息安全 1.1|[Web 服务安全： SOAP 消息安全 1.1](http://go.microsoft.com/fwlink/?LinkId=91240)|  
|WSS 用户名令牌配置文件 1.1|[Web 服务安全用户名令牌配置文件 1.1](http://go.microsoft.com/fwlink/?LinkId=95331)<br /><br /> 不实现基于密码的密钥派生；<br /><br /> 需要Password/@Type= PasswordText （默认值）|  
|WSS：X509 令牌配置文件 1.1|[Web 服务安全 X.509 证书令牌配置文件 1.1](http://go.microsoft.com/fwlink/?LinkId=95332)|  
|WSS：Kerberos 令牌配置文件 1.1|[Web 服务安全 Kerberos 令牌配置文件 1.1](http://go.microsoft.com/fwlink/?LinkId=95333)|  
|WSS：SAML 1.1 令牌配置文件 1.1|[Web 服务安全 SAML 令牌配置文件 1.1](http://go.microsoft.com/fwlink/?LinkId=96694)|  
|WS-Secure 对话|[Web 服务安全对话语言](http://go.microsoft.com/fwlink/?LinkId=95317)|  
|WS-Trust 1.4|[Web 服务信任语言](http://go.microsoft.com/fwlink/?LinkId=169514)|  
|WS-SecurityPolicy 2005/07|[Web 服务安全对话语言](http://go.microsoft.com/fwlink/?LinkId=95317)<br /><br /> 已根据提交到 OASIS WS-SX 技术委员会的勘误表进行了修正。<br /><br /> [ws-sx 消息](http://go.microsoft.com/fwlink/?LinkId=96700)|  
|WS-ReliableMessaging 1.1|[可靠消息传送协议版本 1.1](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-1.md)|  
  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> 支持下表中的规范。  
  
|规范/文档|Link|  
|-----------------------------|----------|  
|WS-Coordination|[Web 服务协作](http://go.microsoft.com/fwlink/?LinkId=95324)|  
|WS-AtomicTransaction|[Web 服务原子事务](http://go.microsoft.com/fwlink/?LinkId=95323)|  
  
 <xref:System.ServiceModel.Description.MetadataExporter>， <xref:System.ServiceModel.Description.MetadataImporter>， <!--zz <xref:System.ServiceModel.Description.WSDLExporter>, <xref:System.ServiceModel.Description.WSDLImporter>, --> `System.ServiceModel.Description.MetadataImporter`， `System.ServiceModel.Description.WSDLImporter`，和<xref:System.ServiceModel.Description.MetadataResolver>类提供支持的以下元数据规范：  
  
-   [XML 架构第 1 部分： 结构第二版](http://go.microsoft.com/fwlink/?LinkId=3536)  
  
-   [XML 架构第 2 部分： 数据类型第二版](http://go.microsoft.com/fwlink/?LinkId=40138)  
  
-   [WSDL 1.1](http://go.microsoft.com/fwlink/?LinkId=96160)  
  
-   [Ws-policy 1.2](http://go.microsoft.com/fwlink/?LinkId=96705)  
  
-   [Ws-policy 1.5](http://go.microsoft.com/fwlink/?LinkId=96706)  
  
-   [Ws-policyattachment 1.2](http://go.microsoft.com/fwlink/?LinkId=96707)  
  
-   [Ws-metadataexchange 1.1](http://go.microsoft.com/fwlink/?LinkId=94868)  
  
-   [Ws-transfer Get 进行元数据检索](http://go.microsoft.com/fwlink/?LinkId=96708)  
  
 另外，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中实现了以下互操作性配置文件：  
  
-   [基本配置文件 1.1](http://go.microsoft.com/fwlink/?LinkId=69313)  
  
-   [简单 SOAP 绑定 1.0](http://go.microsoft.com/fwlink/?LinkId=96710)  
  
-   [基本安全配置文件 1.0 工作草案](http://go.microsoft.com/fwlink/?LinkId=96711)  
  
## <a name="see-also"></a>请参阅  
 [系统提供的互操作性绑定支持的 Web 服务协议](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
 [消息协议](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)  
 [数据协定架构引用](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)  
 [WSDL 和策略](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)  
 [安全协议](../../../../docs/framework/wcf/feature-details/security-protocols.md)  
 [可靠消息传送协议版本 1.0](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-0.md)  
 [可靠消息传送协议版本 1.1](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-1.md)  
 [事务协议](../../../../docs/framework/wcf/feature-details/transaction-protocols.md)  
 [上下文交换协议](../../../../docs/framework/wcf/feature-details/context-exchange-protocol.md)
