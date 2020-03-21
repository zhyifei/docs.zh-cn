---
title: <applicationPool> 元素（网络设置）
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
ms.openlocfilehash: 6feaa801610fa0ffbbf47575f25aff29fa46a66c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152849"
---
# <a name="applicationpool-element-web-settings"></a>\<applicationPool> 元素（Web 设置）
指定ASP.NET在 IIS 7.0 或更高版本中以集成模式运行ASP.NET应用程序时用于管理进程范围行为的配置设置。  
  
> [!IMPORTANT]
> 仅当ASP.NET应用程序托管在 IIS 7.0 或更高版本上时，此元素及其支持的功能才起作用。  
  
[**\<配置>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<系统.web>**](system-web-element-web-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<应用程序池>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<applicationPool
    maxConcurrentRequestsPerCPU="5000"
    maxConcurrentThreadsPerCPU="0"
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  

下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|指定每个 CPU ASP.NET允许的同声请求数。|  
|`maxConcurrentThreadsPerCPU`|指定每个 CPU 的应用程序池可以同时运行多少个线程。 这提供了一种控制ASP.NET并发的替代方法，因为您可以限制每个 CPU 可用于服务请求的托管线程数。 默认情况下，此设置为 0，这意味着ASP.NET不会限制每个 CPU 可以创建的线程数，尽管 CLR 线程池也限制可创建的线程数。|  
|`requestQueueLimit`|指定可在单个进程中排队等待ASP.NET的最大请求数。 当两个或两个ASP.NET多个应用程序在单个应用程序池中运行时，向应用程序池中的任何应用程序发出的请求的累积集受此设置的约束。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<系统.web>](system-web-element-web-settings.md)|包含有关ASP.NET如何与主机应用程序交互的信息。|  
  
## <a name="remarks"></a>备注  

在集成模式下运行 IIS 7.0 或更高版本时，此元素组合允许您配置在应用程序托管在 IIS 应用程序池中时ASP.NET如何管理线程和队列请求。 如果您运行 IIS 6 或在经典模式或 ISAPI 模式下运行 IIS 7.0，则忽略这些设置。  
  
这些`applicationPool`设置适用于在 .NET 框架的特定版本上运行的所有应用程序池。 这些设置包含在 aspnet.config 文件中。 对于 .NET Framework 的版本 2.0 和 4.0，有此文件的版本。 （.NET 框架的版本 3.0 和 3.5 与版本 2.0 共享 aspnet.config 文件。  
  
> [!IMPORTANT]
> 如果在 Windows 7 上运行 IIS 7.0，则可以为每个应用程序池配置单独的 aspnet.config 文件。 这允许您为每个应用程序池定制线程的性能。  
  
对于`maxConcurrentRequestsPerCPU`此设置，.NET Framework 4 中的默认设置"5000"可有效关闭由ASP.NET控制的请求限制，除非您每个 CPU 实际上有 5000 个或更多的请求。 默认设置取决于 CLR 线程池，以自动管理每个 CPU 的并发性。 大量使用异步请求处理或网络 I/O 上有许多长时间运行的请求的应用程序将受益于 .NET 框架 4 中增加的默认限制。 设置为`maxConcurrentRequestsPerCPU`零将关闭使用托管线程来处理ASP.NET请求。 当应用程序在 IIS 应用程序池中运行时，请求将停留在 IIS I/O 线程上，因此 IIS 线程设置会限制并发。  
  
该`requestQueueLimit`设置的工作方式与[processModel](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7w2sway1(v=vs.100)) `requestQueueLimit`元素的属性相同，该属性在 Web.config 文件中设置为ASP.NET应用程序。 但是，aspnet.config`requestQueueLimit`文件中的设置将覆盖 Web.config 文件中的`requestQueueLimit`设置。 换句话说，如果两个属性都设置了（默认情况下，这是 true），则`requestQueueLimit`aspnet.config 文件中的设置优先。  
  
## <a name="example"></a>示例  

下面的示例演示如何在以下情况下配置 aspnet.config 文件中ASP.NET进程范围的行为：  
  
- 应用程序托管在 IIS 7.0 应用程序池中。  
  
- IIS 7.0 以集成模式运行。  
  
- 应用程序正在使用 .NET 框架 3.5 SP1 或更高版本。  
  
示例中的值是默认值。  
  
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

- [\<系统.web>元素（Web 设置）](system-web-element-web-settings.md)
