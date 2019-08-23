---
title: <windows>of <clientCredentials>元素
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: e9f0ed9879cc42ea25b83e6b626139a40a593112
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940298"
---
# <a name="windows-of-clientcredentials-element"></a>\<clientCredentials > 元素\<的 windows >
指定用于表示客户端的 Windows 凭据的设置。  
  
 \<system.ServiceModel>  
\<行为 >  
\<endpointBehaviors>  
\<行为 >  
\<clientCredentials>  
\<windows>  
  
## <a name="syntax"></a>语法  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|设置客户端用于与服务器进行通信的模拟首选项。 服务器上不强制使用客户端所选择的模拟模式。 包括以下有效值：<br /><br /> 标识服务器可以获取客户端的标识和特权, 但不能模拟客户端。<br />模仿服务器可以在本地系统上模拟客户端的安全上下文。<br />委托服务器可以模拟客户端在远程系统上的安全上下文。<br />匿名服务器无法模拟或标识客户端。<br />内容未分配模拟级别。<br /><br /> 默认值为 Identification。 此属性的类型为 <xref:System.Security.Principal.TokenImpersonationLevel>。|  
|`allowNtlm`|如果 Kerberos 不可用，则将此属性设置为 `true` 可令身份验证降级到 NTLM。<br /><br /> 如果将此属性`false`设置为, 则会导致 Windows Communication Foundation (WCF) 在使用 NTLM 时尽力引发异常。 请注意，将此属性设置为 `false` 可能不阻止通过网络发送 NTLM 凭据。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|指定用于向服务证明客户端身份的凭据。|  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [保护客户端](../../../wcf/securing-clients.md)
- [使用证书](../../../wcf/feature-details/working-with-certificates.md)
- [保护服务和客户端的安全](../../../wcf/feature-details/securing-services-and-clients.md)
