---
title: '&lt;xmlElement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b36eb762de3864eb786d0b7157d316ab071dc2fa
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltxmlelementgt"></a>&lt;xmlElement&gt;
指定一个 XML 元素，请求令牌时，该元素在消息正文中发送到安全令牌服务。  
  
 \<系统。ServiceModel >  
\<绑定 >  
\<wsFederatedBinding >  
\<绑定 >  
\<安全 >  
\<消息 >  
\<tokenRequestParameters >  
  
## <a name="syntax"></a>语法  
  
```xml  
<tokenRequestParameters>  
      <xmlElement xmlElement="String" />  
</tokenRequestParameters>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|xmlElement|指定 XML 元素的字符串，请求令牌时，该元素在消息正文中发送到安全令牌服务。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<tokenRequestParameters >](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|令牌请求参数的集合。 每个参数都是一个 XML 元素。|  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>  
 [服务标识和身份验证](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [联合身份验证和已颁发的令牌](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [使用自定义绑定的安全功能](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [联合身份验证和已颁发的令牌](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [绑定](../../../../../docs/framework/wcf/bindings.md)
