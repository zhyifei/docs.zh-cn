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
ms.openlocfilehash: 687398e47ad95e3234c29571eeeac0c9d2d83a39
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2019
ms.locfileid: "66832791"
---
# <a name="systemweb-element-web-settings"></a>\<system.web > 元素 （Web 设置）
包含有关 ASP.NET 托管层管理进程范围的行为方式的信息。  
  
 \<configuration>  
\<system.web > 元素 （Web 设置）  
  
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
|[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|在公共语言运行时和.NET Framework 应用程序使用每个配置文件中指定的根元素。|  
  
## <a name="remarks"></a>备注  
 `system.web`元素及其子`applicationPool`元素已添加到.NET Framework 对于.NET Framework 3.5 SP1。 当你运行[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]或更高版本中集成模式下，此元素组合可让你配置 ASP.NET 如何管理线程以及当 ASP.NET 承载于 IIS 应用程序池进行排队请求的方式。 如果您运行[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]或更高版本在经典或 ISAPI 模式下，将忽略这些设置。  
  
## <a name="example"></a>示例  
 下面的示例演示如何配置 ASP.NET 进程范围行为的 aspnet.config 文件中，当 ASP.NET 承载于 IIS 应用程序池。 该示例假定 IIS 正在运行以集成模式和应用程序使用.NET Framework 3.5 SP1 或更高版本。 在.NET Framework 3.5 SP1 之前的.NET framework 的版本中不出现此行为。 在示例中的值是默认值。  
  
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

- [\<applicationPool> 元素（Web 设置）](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
