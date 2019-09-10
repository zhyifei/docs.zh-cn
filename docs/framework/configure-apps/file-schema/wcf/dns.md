---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: c68cabd03eca71b41a0d0acce26897fa2653f4d3
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855372"
---
# <a name="dns"></a>\<dns>
指定服务器的所需标识。 如果服务器的证书包含具有相同值的 DNS，则此标识对于 X509 证书身份验证模式有效。 如果 SPN 具有相同值，则它对于 Windows 身份验证模式同样有效。  
  
有关设置元素值的详细信息，请参阅[服务标识和身份验证](../../../wcf/feature-details/service-identity-and-authentication.md)。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<客户端 >** ](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<终结点 >** ](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<身份 >** ](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<dns >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|value|证书的 DNS。 DNS 是一个用于在基于 IP 网络上定位计算机的行业标准协议。 用户可以记住显示名称（ <https://go.microsoft.com/fwlink/?prd=10929>如或[https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165)）比基于数字的地址更简单（如207.46.131.137）。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<identity>](identity.md)|指定要由客户端进行身份验证的服务的标识。|  
  
## <a name="example"></a>示例  
 下面的配置代码指定用于对服务器进行身份验证的 X.509 证书的 DNS。  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [服务标识和身份验证](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
