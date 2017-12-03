---
title: "&lt;服务&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ca55770da8da0fe91a12aeb5fa72e61d6dcd67ae
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicesgt"></a>&lt;服务&gt;
服务是在配置文件的 `services` 节中定义的。 每个服务都有自己的 `service` 配置节。  
  
 \<系统。ServiceModel >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.serviceModel>  
        <services>  
        <service>  
        </service>  
        </services>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<服务 >](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|定义特定服务的服务协定、行为和终结点。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|所有 Windows Communication Foundation (WCF) 配置元素的根元素。|  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Configuration.ServicesSection>
