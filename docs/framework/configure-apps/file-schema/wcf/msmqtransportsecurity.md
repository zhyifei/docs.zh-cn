---
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: dc7371d694925d3ac5aa49d7d1269df323358f90
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397814"
---
# <a name="msmqtransportsecurity"></a>\<msmqTransportSecurity>
指定自定义绑定的 MSMQ 传输的安全设置。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<msmqIntegration >** ](msmqintegration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Msmqtransportsecurity.msmqprotectionlevel >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<msmqTransportSecurity msmqAuthenticationMode="None/Windows/Certificate"
                       msmqEncryptionAlgorithm="RC4Stream/AES"
                       msmqProtectionLevel="None/Sign/EncryptAndSign"
                       msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</msmqTransportSecurity>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|指定 MSMQ 传输必须采用什么方式对消息进行身份验证。 如果将此属性设置为 `None`，则 `msmqProtectionLevel` 属性的值也必须设置为 `None`。<br /><br /> 包括以下有效值：<br /><br /> 内容无身份验证。<br />Windows身份验证机制使用 Active Directory 获取与消息关联的 SID 的 x.509 证书。 然后使用它来检查队列的 ACL 以确保用户有权写入队列。<br />证书通道从证书存储区获取证书。<br /><br /> 默认值为 Windows。 此属性的类型为 <xref:System.ServiceModel.MsmqAuthenticationMode>。|  
|`msmqEncryptionAlgorithm`|指定在消息队列管理器之间传输消息时用于在网络上对消息进行加密的算法。 包括以下有效值：<br /><br /> -RC4Stream<br />-   AES<br /><br /> 默认值为 RC4Stream。 此属性的类型为 <xref:System.ServiceModel.MsmqEncryptionAlgorithm>。|  
|`msmqProtectionLevel`|指定在 MSMQ 传输级别采用什么方式来保护消息。 加密可以确保消息的完整性，而 EncryptAndSign 不仅可以确保消息的完整性，还可以确保消息的不可否认性，也就是说，消息确实来自发送者，并且发送者与其所声称的身份一致。 包括以下有效值：<br /><br /> 内容无保护。<br />表明对消息进行签名。<br />EncryptAndSign对消息进行加密和签名。<br /><br /> 默认值为 Sign。 此属性的类型为 <xref:System.Net.Security.ProtectionLevel>。|  
|`msmqSecureHashAlgorithm`|指定用于计算签名中的摘要的算法。 包括以下有效值：<br /><br /> -   MD5<br />-   SHA1<br />-   SHA256<br />-   SHA512<br /><br /> 默认值为 SHA1。 此属性的类型为 <xref:System.ServiceModel.MsmqSecureHashAlgorithm>。<br>由于 MD5 和 SHA1 出现冲突，Microsoft 建议 SHA256 或更好。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<msmqIntegration>](msmqintegration.md)|指定与消息队列 (MSMQ) 发送方或接收方进行交互所需的设置。|  
|[\<msmqTransport>](msmqtransport.md)|指定使用本机 MSMQ 协议的 Windows Communication Foundation (WCF) 服务的队列通信属性。|  
  
## <a name="remarks"></a>备注  
 有关传输安全的详细信息，请参阅[传输安全性](../../../wcf/feature-details/transport-security.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [WCF 中的队列](../../../wcf/feature-details/queues-in-wcf.md)
- [传输](../../../wcf/feature-details/transports.md)
- [选择传输](../../../wcf/feature-details/choosing-a-transport.md)
- [绑定](../../../wcf/bindings.md)
- [扩展绑定](../../../wcf/extending/extending-bindings.md)
- [自定义绑定](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [传输安全性](../../../wcf/feature-details/transport-security.md)
