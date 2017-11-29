---
title: '&lt;userPrincipalName&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b93a0cc24953024e265df418ec6dd738598dd0f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltuserprincipalnamegt"></a>&lt;userPrincipalName&gt;
指定要由客户端进行身份验证的服务的用户主体名称 (UPN)。  
  
 有关设置 UPN 的详细信息，请参阅[服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)。  
  
\<标识 >  
\<userPrincipalName >  
  
## <a name="syntax"></a>语法  
  
```xml  
<userPrincipalName value="String" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 以下几节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|值|一个用户帐户名（有时称为“用户登录名”）和一个域名（标识用户帐户所在的域）。 这是登录到 Windows 域的标准用法。 格式： someone@example.com （对于电子邮件地址）。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<标识 >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|指定要由客户端进行身份验证的服务的标识。|  
  
## <a name="remarks"></a>备注  
 通过此标识连接到终结点的安全 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 客户端在使用终结点进行 SSPI 身份验证时将使用 UPN。  
  
## <a name="example"></a>示例  
 下面的配置代码指定要由客户端进行身份验证的服务的 UPN。  
  
```xml  
<identity>  
  <userPrincipalName value="someone@cohowinery.com" />  
</identity>  
```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.UpnEndpointIdentity>  
 [服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [\<标识 >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
