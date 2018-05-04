---
title: '&lt;serviceTimeouts&gt;'
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: a0f0725bffe0c3c83e412348dea97b16736ef3a8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltservicetimeoutsgt"></a>&lt;serviceTimeouts&gt;
指定服务的超时。  
  
 \<system.ServiceModel>  
\<行为 >  
\<serviceBehaviors>  
\<行为 >  
\<serviceTimeouts >  
  
## <a name="syntax"></a>语法  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a>类型  
 `Type`  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`transactionTimeout`|一个 <xref:System.TimeSpan> 值，指定事务从客户端流动到服务器所必须经历的时间间隔。 默认值为"00: 00:00"。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<行为 >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|指定行为元素。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
