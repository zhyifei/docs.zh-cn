---
title: '&lt;issuedTokenParameters&gt; 的 &lt;issuerMetadata&gt;'
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: 76956c54739219bbde78f378a12d59563ab785c4
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148742"
---
# <a name="ltissuermetadatagt-of-ltissuedtokenparametersgt"></a>&lt;issuedTokenParameters&gt; 的 &lt;issuerMetadata&gt;
\<system.serviceModel>  
\<绑定 >  
\<customBinding>  
\<绑定 >  
\<安全 >  
\<issuedTokenParameters >  
\<issuerMetadata >  
  
## <a name="syntax"></a>语法  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|address|必需。 一个指定终结点地址的字符串。 该地址必须为绝对 URI。 默认值为一个空字符串。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<headers>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|一个地址标头集合。|  
|[\<标识 >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|一个标识，与某个终结点交换消息的其他终结点可以使用该标识对该终结点进行身份验证。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|指定在联合安全方案中颁发的安全令牌的参数。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [联合令牌与颁发的令牌](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [使用自定义绑定的安全功能](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [联合令牌与颁发的令牌](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [绑定](../../../../../docs/framework/wcf/bindings.md)  
 [扩展绑定](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [自定义绑定](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [如何：创建自定义绑定使用 SecurityBindingElement](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [自定义绑定安全性](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
