---
title: '&lt;messageSenderAuthentication&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 496542ca476d9af309a34b4b05a1c3c023c06124
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltmessagesenderauthenticationgt"></a>&lt;messageSenderAuthentication&gt;
指定消息发送方使用的对等证书的身份验证设置。  
  
 \<系统。ServiceModel >  
\<行为 >  
\<serviceBehaviors >  
\<行为 >  
\<serviceCredentials >  
\<对等 >  
\<messageSenderAuthentication >  
  
## <a name="syntax"></a>语法  
  
```xml  
<messageSenderAuthentication  
   customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
   certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`certificateValidationMode`|可选的枚举。 指定用来验证凭据的五种模式之一。 此属性的类型为 <xref:System.ServiceModel.Security.X509CertificateValidationMode>。 如果设置为 `Custom`，则还必须提供 `customCertificateValidator`。|  
|`customCertificateValidatorType`|可选的字符串。 指定用于验证自定义类型的类型和程序集。 当 `certificateValidationMode` 设置为 `Custom` 时，必须设置此属性。 此属性的类型为 <xref:System.IdentityModel.Selectors.X509CertificateValidator>。 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 提供一个默认的对等证书验证程序，该程序根据受信任的用户存储区来验证对等证书。 它还验证证书是否与有效的根相联系。 您可以实现自定义验证程序以指定不同的行为，并使用该属性指向自定义验证程序。|  
|`revocationMode`|可选的枚举。 指定证书吊销模式。 此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>。 系统通过在吊销证书列表中进行查找来验证对等证书尚未吊销。 可以联机执行该检查，也可以根据缓存的吊销列表执行该检查。 将此属性设置为 NoCheck 可禁用吊销检查。|  
|`trustedStoreLocation`|可选的枚举。 指定 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 安全系统用来验证对等证书的受信任存储区位置。 此属性的类型为 <xref:System.Security.Cryptography.X509Certificates.StoreLocation>。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<对等 >](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|指定对等节点的当前凭据。|  
  
## <a name="remarks"></a>备注  
 如果选择了消息身份验证，则必须配置此元素。 输出通道，每条消息进行签名使用提供的证书[\<证书 >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)。 在将任一消息传递到应用程序之前，都会使用由此元素的 `customCertificateValidatorType` 属性指定的验证程序对照消息凭据对其进行检查。 验证程序可以接受或拒绝凭据。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 [使用证书](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [对等网络](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [对等通道消息身份验证](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [对等通道自定义身份验证](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [保护对等通道应用程序](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
