---
title: '&lt;enableWebScript&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f6dc2654b8c51dad53c05a37f5febe15d6d69fd1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltenablewebscriptgt"></a>&lt;enableWebScript&gt;
通过此元素启用的终结点行为可以使用 ASP.NET AJAX 网页中的服务。  
  
 \<系统。ServiceModel >  
\<行为 >  
\<endpointBehaviors >  
\<行为 >  
\<enableWebScript >  
  
## <a name="syntax"></a>语法  
  
```xml  
<enableWebScript />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<行为 >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|指定终结点行为集。|  
  
## <a name="remarks"></a>备注  
 此行为只应该使用结合使用[ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)标准绑定，或[ \<webMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md)绑定元素。  有关此行为的更多信息，请参见 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>  
 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>  
 [AJAX 集成和 JSON 支持](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [\<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
