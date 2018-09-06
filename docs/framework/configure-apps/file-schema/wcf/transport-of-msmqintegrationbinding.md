---
title: '&lt;msmqIntegrationBinding&gt; 的 &lt;transport&gt;'
ms.date: 03/30/2017
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
ms.openlocfilehash: eb992a79a4a5a65404aec99cc84e9f1d78cb3f4b
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43738945"
---
# <a name="lttransportgt-of-ltmsmqintegrationbindinggt"></a>&lt;msmqIntegrationBinding&gt; 的 &lt;transport&gt;
定义消息队列集成传输的安全设置。  
  
 \<system.ServiceModel>  
\<绑定 >  
msmqIntegrationBinding  
\<绑定 >  
\<安全 >  
\<transport>  
  
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
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|指定 MSMQ 传输必须采用什么方式对消息进行身份验证。 如果将此属性设置为 `None`，则 `msmqProtectionLevel` 属性的值也必须设置为 `None`。<br /><br /> 包括以下有效值：<br /><br /> -None： 无身份验证。<br />-WindowsDomain： 身份验证机制使用 Active Directory 获取与消息关联的 SID 的 X.509 证书。 然后使用它来检查队列的 ACL 以确保用户有权写入队列。<br />-证书： 通道从证书存储中获取的证书。<br /><br /> 默认值为 WindowsDomain。 此属性的类型为 <xref:System.ServiceModel.MsmqAuthenticationMode>。|  
|`msmqEncryptionAlgorithm`|指定在消息队列管理器之间传输消息时用于在网络上对消息进行加密的算法。 包括以下有效值：<br /><br /> -RC4Stream<br />-AES<br /><br /> 默认值为 RC4Stream。 此属性的类型为 <xref:System.ServiceModel.MsmqEncryptionAlgorithm>。|  
|`msmqProtectionLevel`|指定在 MSMQ 传输级别采用什么方式来保护消息。 加密可以确保消息的完整性，而 EncryptAndSign 不仅可以确保消息的完整性，还可以确保消息的不可否认性，也就是说，消息确实来自发送者，并且发送者与其所声称的身份一致。<br /><br /> -有效的值包括：<br />-None： 无保护。<br />登录： 对消息进行签名。<br />-EncryptAndSign： 消息进行加密和签名。<br /><br /> 默认值为 Sign。 此属性的类型为 ProtectionLevel。|  
|`msmqSecureHashAlgorithm`|-指定用于计算作为签名摘要算法。 包括以下有效值：<br />-   MD5<br />-   SHA1<br />-   SHA256<br />-   SHA512<br /><br /> 默认值为 SHA1。 此属性的类型为 <xref:System.ServiceModel.MsmqSecureHashAlgorithm>。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|定义 MSMQ 绑定的安全设置。|  
  
## <a name="remarks"></a>备注  
 此元素包装消息队列集成传输的安全设置。 消息队列集成传输和排队传输的设置是相同的。 使用此元素可以设置身份验证模式、加密算法、安全哈希算法和保护级别。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.MsmqTransportSecurity>  
 [保护服务和客户端的安全](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [保护服务和客户端的安全](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [绑定](../../../../../docs/framework/wcf/bindings.md)  
 [配置系统提供的绑定](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [使用绑定来配置 Windows Communication Foundation 服务和客户端](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<绑定 >](../../../../../docs/framework/misc/binding.md)
