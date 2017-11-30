---
title: '&lt;servicePrincipalName&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e472c7fcfd57341074489a75f7954be38291523b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltserviceprincipalnamegt"></a>&lt;servicePrincipalName&gt;
利用对应的服务主体名称 (SPN) 指定服务的标识。  
  
 有关设置 SPN 的详细信息，请参阅[服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)。  
  
 \<标识 >  
\<servicePrincipalName >  
  
## <a name="syntax"></a>语法  
  
```xml  
<servicePrincipalName value = "String" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 以下几节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|值|客户端用来唯一地标识服务实例的名称。 如果在计算机的整个目录林上安装多个服务实例，那么每个实例都必须有自己的 SPN。 如果客户端有多个名称可用于身份验证，则给定的服务实例可以有多个 SPN。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<标识 >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|指定要由客户端进行身份验证的服务的标识。|  
  
## <a name="remarks"></a>备注  
 通过此标识连接到终结点的安全 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 客户端在使用终结点进行 SSPI 身份验证时将使用 SPN。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.SpnEndpointIdentity>  
 [服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [\<标识 >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
