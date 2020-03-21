---
title: <transport> 的 <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: cc47c01cccc931e81ba57ab37ad9e3accfaa693b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152926"
---
# <a name="transport-of-netmsmqbinding"></a>\<\<网络mq绑定>的传输>
定义传输安全设置。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统.服务模式>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<绑定>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<净Mmq绑定>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<绑定>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<安全>**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<运输>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<netMsmqBinding>
  <binding>
    <security>
      <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    </security>
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|msmqAuthenticationMode|指定 MSMQ 传输必须采用什么方式对消息进行身份验证。 有效值包括以下值：<br /><br /> - 无：无身份验证。<br />- WindowsDomain：身份验证机制使用 Active Directory 检索与消息关联的安全标识符的 X.509 证书。 然后使用它来检查队列的 ACL 以确保用户具有队列写权限。<br />- 证书：通道从证书存储中检索证书。<br /><br /> 默认为 `WindowsDomain`。<br /><br /> 如果将此属性设置为 `None`，则 `msmqProtectionLevel` 属性也必须设置为 `None`。 此特性的类型为 <xref:System.ServiceModel.MsmqAuthenticationMode>|  
|msmqEncryptionAlgorithm|指定在消息队列管理器之间传输消息时用于在网络上对消息进行加密的算法。 有效值包括以下值：<br /><br /> - RC4流<br />- AES<br />- 默认值为`RC4Stream`。 此属性的类型为 <xref:System.ServiceModel.MsmqEncryptionAlgorithm>。|  
|msmqProtectionLevel|指定在 MSMQ 传输级别采用什么方式来保护消息。 加密可确保消息的完整性，而签名和加密不仅可以确保消息的完整性，还可以确保消息的不可否认性。 也就是说，邮件确实来自发件人，发件人就是他们所说的发件人。 有效值包括以下值：<br /><br /> -无：没有保护<br />- 签名：消息已签名。<br />- 加密和签名：邮件经过加密并签名。<br />- 默认值为`Sign`。|  
|msmqSecureHashAlgorithm|指定用于计算消息摘要的哈希算法。 有效值包括以下值：<br /><br /> - MD5<br />- SHA1<br />- SHA256<br />- SHA512<br /><br /> 默认为 `SHA1`。 此属性的类型为 <xref:System.ServiceModel.MsmqSecureHashAlgorithm>。<br>由于与 MD5 和 SHA1 的碰撞问题，Microsoft 推荐 SHA256 或更高。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<安全>](security-of-netmsmqbinding.md)|定义排队传输的传输安全设置。|  
  
## <a name="see-also"></a>另请参阅

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [WCF 中的队列](../../../wcf/feature-details/queues-in-wcf.md)
- [保护服务和客户端的安全](../../../wcf/feature-details/securing-services-and-clients.md)
- [绑定](../../../wcf/bindings.md)
- [配置系统提供的绑定](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [使用绑定配置服务和客户端](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<绑定>](bindings.md)
