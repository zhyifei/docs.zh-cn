---
title: <transport> 的 <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
ms.openlocfilehash: 1cb165fed9266307335482166116c4c1d62efe7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152952"
---
# <a name="transport-of-msmqintegrationbinding"></a>\<msmq\<集成绑定>传输>
定义消息队列集成传输的安全设置。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统.服务模式>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<绑定>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmq集成绑定>**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<绑定>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<安全>**](security-of-msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<运输>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<security>
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</security>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 以下几节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|指定 MSMQ 传输必须采用什么方式对消息进行身份验证。 如果将此属性设置为 `None`，则 `msmqProtectionLevel` 属性的值也必须设置为 `None`。<br /><br /> 有效值包括以下值：<br /><br /> - 无：无身份验证。<br />- WindowsDomain：身份验证机制使用 Active Directory 获取与消息关联的 SID 的 X.509 证书。 然后使用它来检查队列的 ACL 以确保用户有权写入队列。<br />- 证书：通道从证书存储获取证书。<br /><br /> 默认值为 WindowsDomain。 此属性的类型为 <xref:System.ServiceModel.MsmqAuthenticationMode>。|  
|`msmqEncryptionAlgorithm`|指定在消息队列管理器之间传输消息时用于在网络上对消息进行加密的算法。 有效值包括以下值：<br /><br /> - RC4流<br />- AES<br /><br /> 默认值为 RC4Stream。 此属性的类型为 <xref:System.ServiceModel.MsmqEncryptionAlgorithm>。|  
|`msmqProtectionLevel`|指定在 MSMQ 传输级别采用什么方式来保护消息。 加密可确保邮件完整性，而加密和签名可确保邮件的完整性和非否认性;也就是说，邮件确实来自发件人，发件人是他们说的。<br /><br /> - 有效值包括以下内容：<br />-无：没有保护<br />- 签名：消息已签名。<br />- 加密和签名：邮件经过加密并签名。<br /><br /> 默认值为 Sign。 此属性的类型为 ProtectionLevel。|  
|`msmqSecureHashAlgorithm`|- 指定用于计算摘要作为签名的一部分的算法。 有效值包括以下值：<br />- MD5<br />- SHA1<br />- SHA256<br />- SHA512<br /><br /> 默认值为 SHA1。 此属性的类型为 <xref:System.ServiceModel.MsmqSecureHashAlgorithm>。<br>由于与 MD5 和 SHA1 的碰撞问题，Microsoft 推荐 SHA256 或更高。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<安全>](security-of-basichttpbinding.md)|定义 MSMQ 绑定的安全设置。|  
  
## <a name="remarks"></a>备注  
 此元素包装消息队列集成传输的安全设置。 消息队列集成传输和排队传输的设置是相同的。 使用此元素可以设置身份验证模式、加密算法、安全哈希算法和保护级别。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [保护服务和客户端的安全](../../../wcf/feature-details/securing-services-and-clients.md)
- [绑定](../../../wcf/bindings.md)
- [配置系统提供的绑定](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [使用绑定配置服务和客户端](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<绑定>](bindings.md)
