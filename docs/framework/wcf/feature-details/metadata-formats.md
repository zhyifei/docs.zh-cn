---
title: 元数据格式
ms.date: 03/30/2017
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
ms.openlocfilehash: e7208a8d5fd6d100ac2a2c4fb1369a571c63e7fc
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212173"
---
# <a name="metadata-formats"></a>元数据格式
Windows Communication Foundation （WCF）支持下表中的元数据格式。  
  
## <a name="metadata-specifications-and-usage"></a>元数据的规范和用法  
  
|协议|规范和用法|  
|--------------|-----------------------------|  
|WSDL 1.1|[Web 服务描述语言（WSDL）1。1](https://www.w3.org/TR/wsdl/)<br /><br /> WCF 使用 Web 服务描述语言（WSDL）描述服务。|  
|XML 架构|[XML 架构第2部分：数据类型第二版](https://www.w3.org/TR/2004/REC-xmlschema-2-20041028/)和[XML 架构第1部分：结构第二版](https://www.w3.org/TR/2004/REC-xmlschema-1-20041028/)<br /><br /> WCF 使用 XML 架构描述消息中使用的数据类型。|  
|WS Policy|[Web 服务策略 1.2-框架（WS 策略）](https://www.w3.org/Submission/WS-Policy/)<br /><br /> [Web 服务策略 1.5-框架](https://www.w3.org/TR/ws-policy/)<br /><br /> WCF 使用 WS 策略1.2 或1.5 规范和域特定断言来描述服务要求和功能。|  
|WS Policy 附件|[Web 服务策略 1.2-附件（Ws-policyattachment）](https://www.w3.org/Submission/WS-PolicyAttachment/)<br /><br /> WCF 实现 WS 策略附件，以在 WSDL 中的不同范围内附加策略表达式。|  
|WS 元数据交换|[Web 服务元数据交换（Ws-metadataexchange）版本1。1](https://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF 实现 Ws-metadataexchange 来检索 XML 架构、WSDL 和 WS 策略。|  
|WSDL 的 WS 寻址绑定|[Web 服务寻址 1.0-WSDL 绑定](https://www.w3.org/TR/ws-addr-wsdl/)<br /><br /> WCF 为 WSDL 实现 WS-ADDRESSING 绑定以在 WSDL 中附加寻址信息。|  
  
## <a name="see-also"></a>另请参阅

- [系统提供的互操作性绑定支持的 Web 服务协议](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [WSDL 和策略](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
