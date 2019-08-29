---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 423a3249a9298675517f0cff08566c3735fa35f1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940512"
---
# <a name="userprincipalname"></a>\<userPrincipalName>
指定要由客户端进行身份验证的服务的用户主体名称 (UPN)。  
  
 有关设置 UPN 的详细信息, 请参阅[服务标识和身份验证](../../../wcf/feature-details/service-identity-and-authentication.md)。  
  
\<身份 >  
\<userPrincipalName>  
  
## <a name="syntax"></a>语法  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 以下几节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|值|一个用户帐户名（有时称为“用户登录名”）和一个域名（标识用户帐户所在的域）。 这是登录到 Windows 域的标准用法。 格式为: someone@example.com (用于电子邮件地址)。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<identity>](identity.md)|指定要由客户端进行身份验证的服务的标识。|  
  
## <a name="remarks"></a>备注  
 使用此标识连接到终结点的安全 Windows Communication Foundation (WCF) 客户端在使用该终结点执行 SSPI 身份验证时将使用 UPN。  
  
## <a name="example"></a>示例  
 下面的配置代码指定要由客户端进行身份验证的服务的 UPN。  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [服务标识和身份验证](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
