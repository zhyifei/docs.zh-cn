---
title: <system.web> 元素（网络设置）
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: b37b05bdf90630251cbfcf86751243a3a8b77663
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152836"
---
# <a name="systemweb-element-web-settings"></a>\<system.web> 元素（Web 设置）
包含有关托管层如何管理进程范围行为ASP.NET的信息。  
  
[**\<配置>**](../configuration-element.md)  
&nbsp;&nbsp;**\<系统.web>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  

下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  

无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<应用程序池>](applicationpool-element-web-settings.md)|在 aspnet.config 文件中指定 IIS 应用程序池的配置设置。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<配置>](../configuration-element.md)|指定通用语言运行时和 .NET Framework 应用程序使用的每个配置文件中的根元素。|  
  
## <a name="remarks"></a>备注  

该`system.web`元素及其子`applicationPool`元素从 .NET 框架 3.5 SP1 开始添加到 .NET 框架中。 在集成模式下运行 IIS 7.0 或更高版本时，此元素组合允许您配置ASP.NET如何管理线程以及ASP.NET托管在 IIS 应用程序池中时如何排队请求。 如果在经典或 ISAPI 模式下运行 IIS 7.0 或更高版本，则忽略这些设置。  
  
## <a name="example"></a>示例  

下面的示例演示如何在 iIS 应用程序池中托管ASP.NET时，如何在 aspnet.config 文件中配置ASP.NET进程范围的行为。 该示例假定 IIS 在集成模式下运行，并且应用程序正在使用 .NET 框架 3.5 SP1 或更高版本。 此行为不会在 .NET 框架 3.5 SP1 之前的版本中发生。 示例中的值是默认值。  
  
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
  
## <a name="see-also"></a>另请参阅

- [\<应用程序池>元素（Web 设置）](applicationpool-element-web-settings.md)
