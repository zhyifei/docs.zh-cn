---
title: '&lt;identity&gt; 的 &lt;certificate&gt;'
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: e7d8e7abbc95521d85dc5999c36687f9becea9fb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltcertificategt-for-ltidentitygt"></a>&lt;identity&gt; 的 &lt;certificate&gt;
指定用于向客户端验证服务器的 X.509 证书。  
  
 有关设置此元素的值的详细信息，请参阅[服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)。  
  
 \<标识 >  
\<证书 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<certificate encodedValue = "String" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|encodedValue|证书的 Base64 编码。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<标识 >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|指定要由客户端进行身份验证的服务的标识。|  
  
## <a name="example"></a>示例  
 下面的代码指定用于向客户端验证服务器的证书的编码表示形式。  
  
```xml  
<identity>  
  <certificate encodedValue = " MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />  
</identity>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.EndpointIdentity>  
 [服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [\<标识 >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
