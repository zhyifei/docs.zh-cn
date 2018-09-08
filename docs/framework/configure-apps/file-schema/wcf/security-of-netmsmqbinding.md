---
title: '&lt; netMsmqBinding&gt; 的 &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: c525344b18322cef05f64e46c75cdab7b271561a
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44205927"
---
# <a name="ltsecuritygt-of-ltnetmsmqbindinggt"></a>&lt; netMsmqBinding&gt; 的 &lt;security&gt;
定义 MSMQ 绑定的安全设置。 它指定是否启用传输或 SOAP 安全；如果启用，还指定所使用的身份验证模式和保护级别。  
  
 \<system.ServiceModel>  
\<绑定 >  
\<netMsmqBinding>  
\<绑定 >  
\<安全 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<security mode="None/Transport/Message/Both">  
   <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
      msmqEncryptionAlgorithm="RC4Stream/AES"  
      msmqProtectionLevel="None/Sign/EncryptAndSign"  
      msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
      <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="None/Windows/UserName/Certificate/CardSpace"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|mode|指定用于控制完整性、保密性和身份验证的安全类型。 包括以下有效值：<br /><br /> -None： 禁用安全性。<br />-传输： 提供保护和身份验证由传输。 这适用于两个队列管理器之间的消息安全性。 未在应用程序和队列管理器之间提供安全性。 现有的 Msmq 应用程序与此类型的安全模式功能等效。<br />-消息： 指定端端应用程序安全性。 未在传输层提供安全性。 这类似于其他标准绑定提供的安全性。<br />-两者： 提供了传输和 SOAP 消息传送层的安全性。 在这两个层上需要相同的凭据。<br /><br /> 默认值为 Transport。 此属性的类型为 <xref:System.ServiceModel.NetMsmqSecurityMode>。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<message>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|定义 SOAP 消息安全设置。 此元素的类型为 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>。|  
|[\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|定义 MSMQ 传输的安全设置。 此元素的类型为 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|绑定|绑定元素[ \<netMsmqBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>  
 <xref:System.ServiceModel.NetMsmqBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity>  
 [保护服务和客户端的安全](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [绑定](../../../../../docs/framework/wcf/bindings.md)  
 [配置系统提供的绑定](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [使用绑定来配置 Windows Communication Foundation 服务和客户端](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<绑定 >](../../../../../docs/framework/misc/binding.md)  
 [WCF 中的队列](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
