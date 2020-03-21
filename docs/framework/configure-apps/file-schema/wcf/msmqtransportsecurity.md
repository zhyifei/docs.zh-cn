---
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: 5899c609b3cf52c4a275ba6fb10c5826fcf37f1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153004"
---
# <a name="msmqtransportsecurity"></a>\<msmq运输安全>
指定自定义绑定的 MSMQ 传输的安全设置。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统.服务模式>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<绑定>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<自定义绑定>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<绑定>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmq集成>**](msmqintegration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<msmq传输安全>**  
  
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
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|指定 MSMQ 传输必须采用什么方式对消息进行身份验证。 如果将此属性设置为 `None`，则 `msmqProtectionLevel` 属性的值也必须设置为 `None`。<br /><br /> 有效值包括以下值：<br /><br /> - 无：无身份验证。<br />- Windows：身份验证机制使用 Active Directory 获取与消息关联的 SID 的 X.509 证书。 然后使用它来检查队列的 ACL 以确保用户有权写入队列。<br />- 证书：通道从证书存储获取证书。<br /><br /> 默认值为 Windows。 此属性的类型为 <xref:System.ServiceModel.MsmqAuthenticationMode>。|  
|`msmqEncryptionAlgorithm`|指定在消息队列管理器之间传输消息时用于在网络上对消息进行加密的算法。 有效值包括以下值：<br /><br /> - RC4流<br />- AES<br /><br /> 默认值为 RC4Stream。 此属性的类型为 <xref:System.ServiceModel.MsmqEncryptionAlgorithm>。|  
|`msmqProtectionLevel`|指定在 MSMQ 传输级别采用什么方式来保护消息。 加密可确保邮件完整性，而加密和签名可确保邮件的完整性和非否认性;也就是说，邮件确实来自发件人，发件人是他们说的。 有效值包括以下值：<br /><br /> -无：没有保护<br />- 签名：消息已签名。<br />- 加密和签名：邮件经过加密并签名。<br /><br /> 默认值为 Sign。 此属性的类型为 <xref:System.Net.Security.ProtectionLevel>。|  
|`msmqSecureHashAlgorithm`|指定用于计算签名中的摘要的算法。 有效值包括以下值：<br /><br /> - MD5<br />- SHA1<br />- SHA256<br />- SHA512<br /><br /> 默认值为 SHA1。 此属性的类型为 <xref:System.ServiceModel.MsmqSecureHashAlgorithm>。<br>由于与 MD5 和 SHA1 的碰撞问题，Microsoft 推荐 SHA256 或更高。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<msmq集成>](msmqintegration.md)|指定与消息队列 (MSMQ) 发送方或接收方进行交互所需的设置。|  
|[\<msmq 传输>](msmqtransport.md)|指定使用本机 MSMQ 协议的 Windows Communication Foundation (WCF) 服务的队列通信属性。|  
  
## <a name="remarks"></a>备注  
 有关运输安全的详细信息，请参阅[运输安全](../../../wcf/feature-details/transport-security.md)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [WCF 中的队列](../../../wcf/feature-details/queues-in-wcf.md)
- [传输](../../../wcf/feature-details/transports.md)
- [选择传输](../../../wcf/feature-details/choosing-a-transport.md)
- [绑定](../../../wcf/bindings.md)
- [扩展绑定](../../../wcf/extending/extending-bindings.md)
- [自定义绑定](../../../wcf/extending/custom-bindings.md)
- [\<自定义绑定>](custombinding.md)
- [运输安全](../../../wcf/feature-details/transport-security.md)
