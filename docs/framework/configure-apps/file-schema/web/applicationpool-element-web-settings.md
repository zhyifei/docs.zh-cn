---
title: "&lt;applicationPool&gt;元素 （Web 设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: df4e7325a42db733fd6a7f5fbc9fe29c2cda4bd1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltapplicationpoolgt-element-web-settings"></a>&lt;applicationPool&gt;元素 （Web 设置）
指定 ASP.NET 用于 ASP.NET 应用程序在中集成模式下运行时管理进程范围的行为的配置设置[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]或更高版本。  
  
> [!IMPORTANT]
>  此元素和功能它支持才起作用，如果你的 ASP.NET 应用程序托管在[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]或更高版本。  
  
 \<configuration>  
\<.w e b > 元素 （Web 设置）  
\<applicationPool > 元素 （Web 设置）  
  
## <a name="syntax"></a>语法  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|指定 ASP.NET 允许每个 CPU 的同时请求数。|  
|`maxConcurrentThreadsPerCPU`|指定多少个并发线程可以为每个 CPU 运行应用程序池。 这会提供一种替代方式来控制 ASP.NET 的并发程度，因为你可以限制可用于每个 CPU 为请求提供服务的托管线程数。 默认情况下此设置为 0，这意味着 ASP.NET 不尽管 CLR 线程池还限制可以创建的线程数限制的每个 CPU，可以创建的线程数。|  
|`requestQueueLimit`|指定的最大可以为 ASP.NET 在一个进程中排队的请求数。 在两个或多个 ASP.NET 应用程序运行在单个应用程序池中，向应用程序池的任何应用程序发出的请求的累积集将遵循此设置。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<system.web>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|包含有关 ASP.NET 如何与宿主应用程序交互的信息。|  
  
## <a name="remarks"></a>备注  
 当你运行[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]或更高版本在集成模式下，此元素组合允许你配置 ASP.NET 应用程序承载在 IIS 应用程序池中时如何管理线程和队列的请求。 如果运行 IIS 6，或者运行[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]在经典模式下或在 ISAPI 模式下，将忽略这些设置。  
  
 `applicationPool`设置适用于特定版本的.NET framework 运行的所有应用程序池。 设置包含在 aspnet.config 文件中。 没有此文件为版本 2.0 和 4.0 的.NET framework 的版本。 （版本 3.0 和 3.5 的.NET framework 共享下的 aspnet.config 文件版本 2.0。）  
  
> [!IMPORTANT]
>  如果你运行[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]上[!INCLUDE[win7](../../../../../includes/win7-md.md)]，你可以通过配置单独的 aspnet.config 文件为每个应用程序池。 这样可以定制为每个应用程序池的线程的性能。  
  
 有关`maxConcurrentRequestsPerCPU`设置，"5000"的默认设置[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]有效地将关闭请求限制，它受 ASP.NET，除非您实际上有 5000 或更多的请求，每个 CPU。 默认设置改为依赖于 CLR 线程池来自动管理每个 CPU 的并发。 在构成广泛使用的异步请求处理负载，或已在网络 I/O 上受阻的多长时间运行请求的应用程序将受益于中的增大的默认限制[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]。 设置`maxConcurrentRequestsPerCPU`到用于处理 ASP.NET 请求零将关闭的托管线程使用。 应用程序运行时在 IIS 应用程序池中，请求将停留在 IIS I/O 线程和 IIS 线程设置因此限制并发。  
  
 `requestQueueLimit`设置相同的工作方式为`requestQueueLimit`属性[processModel](http://msdn.microsoft.com/en-us/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d)元素，它在 ASP.NET 应用程序的 Web.config 文件中设置。 但是， `requestQueueLimit` aspnet.config 文件中的设置将重写`requestQueueLimit`在 Web.config 文件中设置。 换而言之，如果未设置这两个属性 （默认情况下，此为 true）， `requestQueueLimit` aspnet.config 文件中的设置将优先。  
  
## <a name="example"></a>示例  
 下面的示例演示如何在以下情况下的 aspnet.config 文件中配置 ASP.NET 进程范围的行为：  
  
-   应用程序托管在[!INCLUDE[iisver](../../../../../includes/iisver-md.md)]应用程序池。  
  
-   [!INCLUDE[iisver](../../../../../includes/iisver-md.md)]在集成模式下运行。  
  
-   应用程序使用[!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]或更高版本。  
  
 在示例中的值是默认值。  
  
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
 [\<system.web> 元素（Web 设置）](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)
