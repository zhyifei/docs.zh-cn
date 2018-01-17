---
title: "&lt;超时&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 04003584cf12355116d32cccffdcb2b9990b1b85
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="lttimeoutsgt"></a>&lt;超时&gt;
表示一个配置元素，该元素指定允许服务主机打开或关闭的时间间隔。  
  
 \<系统。ServiceModel >  
\<客户端 >  
\<终结点 >  
\<主机 >  
\<超时 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<timeOuts closeTimeout="TimeSpan"  
   openTimeout="TimeSpan" >  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`closeTimeout`|一个 <xref:System.TimeSpan> 值，指定为关闭服务主机预留的时间间隔。|  
|`openTimeout`|一个 <xref:System.TimeSpan> 值，指定为打开或关闭服务主机预留的时间间隔。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<主机 >](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|一个指定服务主机设置的配置元素。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [承载](../../../../../docs/framework/wcf/feature-details/hosting.md)
