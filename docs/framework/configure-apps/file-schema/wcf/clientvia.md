---
title: '&lt;clientVia&gt;'
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 6218bb3f205f2825eb3f10fabf834cfd0396ac87
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltclientviagt"></a>&lt;clientVia&gt;
指定应为其创建传输通道的 URI。 有关详细信息，请参阅<xref:System.ServiceModel.Description.ClientViaBehavior>。  
  
 \<system.ServiceModel>  
\<行为 >  
\<endpointBehaviors>  
\<行为 >  
\<clientVia >  
  
## <a name="syntax"></a>语法  
  
```xml  
<clientVia viaUri="String"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`viaUri`|一个指定 URI 的字符串，此 URI 指示消息应采用的路由。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<行为 >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|指定终结点行为。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.ClientViaElement>  
 <xref:System.ServiceModel.Description.ClientViaBehavior>
