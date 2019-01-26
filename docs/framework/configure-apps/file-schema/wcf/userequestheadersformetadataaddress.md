---
title: '&lt;useRequestHeadersForMetadataAddress&gt;'
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 6c03057fca23b037702c702b9a574045ebb302b4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656617"
---
# <a name="ltuserequestheadersformetadataaddressgt"></a>&lt;useRequestHeadersForMetadataAddress&gt;
允许从请求消息头中检索元数据地址信息。  
  
\<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<useRequestHeadersForMetadataAddress>  
  
## <a name="syntax"></a>语法  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<defaultPorts>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|一个默认端口集合，列出客户端应用程序侦听的默认通信终结点。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|指定行为元素。|  
  
## <a name="see-also"></a>请参阅
- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
