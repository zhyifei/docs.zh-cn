---
title: "&lt;system.web&gt;元素 （Web 设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 59899178fd9fc8da2334883ed62d9f8655eb335b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltsystemwebgt-element-web-settings"></a>&lt;system.web&gt;元素 （Web 设置）
包含有关如何在 ASP.NET 承载层管理进程范围的行为的信息。  
  
 \<configuration>  
\<.w e b > 元素 （Web 设置）  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<applicationPool>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|在 aspnet.config 文件中指定 IIS 应用程序池配置的设置。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|指定公共语言运行时和 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 应用程序所使用的每个配置文件中的根元素。|  
  
## <a name="remarks"></a>备注  
 `system.web`元素及其子`applicationPool`元素已添加到[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]在[!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]。 当你运行[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]或在集成模式下的更高版本，此元素组合允许你配置 ASP.NET 如何管理线程，以及当 ASP.NET 承载于 IIS 应用程序池进行排队请求的方式。 如果你运行[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]或更高版本在经典或 ISAPI 模式下，这些设置将被忽略。  
  
## <a name="example"></a>示例  
 下面的示例演示如何配置 ASP.NET 进程范围的行为的 aspnet.config 文件中，当 ASP.NET 承载于 IIS 应用程序池。 该示例假设在集成的正在运行 IIS 模式和应用程序正在使用[!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]或更高版本。 版本中不会发生此行为[!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]早于[!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]。 在示例中的值是默认值。  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"   
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a>元素信息  
  
|||  
|-|-|  
|命名空间||  
|架构名称||  
|验证文件||  
|可以为空||  
  
## <a name="see-also"></a>请参阅  
 [\<applicationPool> 元素（Web 设置）](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
