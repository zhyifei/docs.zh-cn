---
title: "应用程序域资源监控"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- monitoring managed memory use by application domain
- application domains, memory use
- memory use, monitoring
- application domains, resource monitoring
ms.assetid: 318bedf8-7f35-4f00-b34a-2b7b8e3fa315
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 62a514f94857044af5020d36a1cfd6ce06741ac7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="application-domain-resource-monitoring"></a>应用程序域资源监控
应用程序域资源监视 (ARM) 使主机可以监视由应用程序域的 CPU 和内存使用情况。 这很有用，例如，ASP.NET 使用在长时间运行的进程中的许多应用程序域的主机。 宿主可以卸载的应用程序有不利影响的整个过程，但仅的性能，如果它可以确定有问题的应用程序的应用程序域。 ARM 提供可用于协助进行此类决策的信息。  
  
 例如，托管服务可能有许多 ASP.NET 服务器上运行的应用程序。 如果在进程中的一个应用程序开始消耗太多内存或处理器时间太长，托管服务可以使用 ARM 来标识问题的原因的应用程序域。  
  
 ARM 是一个轻量实时应用程序中使用。 可以通过使用事件跟踪 Windows (ETW) 或直接通过托管或本机 Api 来访问信息。  
  
## <a name="enabling-resource-monitoring"></a>启用监视功能资源  
 ARM 可以启用通过四种方法： 通过公共语言运行时 (CLR) 启动时，请提供配置文件，通过使用非托管承载 API，通过使用托管的代码中，或通过侦听 ARM ETW 事件。  
  
 一旦启用了 ARM，它将开始收集进程中的所有应用程序域上的数据。如果启用 ARM 之前，已创建应用程序域，累计数据启动时创建的应用程序域时不启用 ARM。一旦启用，则不能禁用 ARM。  
  
-   你也可以通过添加在 CLR 启动启用 ARM [ \<appDomainResourceMonitoring >](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)元素的配置文件和设置到`enabled`属性设为`true`。 值为`false`（默认值） 只表示在启动时不启用 ARM; 你可以将其激活更高版本使用其他激活机制之一。  
  
-   主机可以通过请求启用 ARM [ICLRAppDomainResourceMonitor](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)承载接口。 一旦成功获得此接口，会启用 ARM。  
  
-   托管的代码可以通过设置静态启用 ARM (`Shared`在 Visual Basic 中)<xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>属性`true`。 一旦设置该属性，则会启用 ARM。  
  
-   在启动之后，你可以侦听 ETW 事件启用 ARM。 ARM 启用和开始时启用公共提供程序引发的所有应用程序域的事件`Microsoft-Windows-DotNETRuntime`使用`AppDomainResourceManagementKeyword`关键字。 若要将数据与应用程序域和线程相关联，你必须启用`Microsoft-Windows-DotNETRuntimeRundown`具有提供程序`ThreadingKeyword`关键字。  
  
## <a name="using-arm"></a>使用 ARM  
 ARM 提供一个应用程序域和三种类型的有关内存使用情况信息使用的总处理器时间。  
  
-   **应用程序域中，以秒为单位的处理器时间总计**： 这通过将报告由操作系统在其生存期内应用程序域中执行时所用的所有线程的线程时间相加计算得出。 阻止或处于睡眠状态的线程不使用处理器时间。 当一个线程调用到本机代码时，线程在本机代码中所花的时间包含在其中调用应用程序域计数。  
  
    -   托管 API:<xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>属性。  
  
    -   托管 API: [iclrappdomainresourcemonitor:: Getcurrentcputime](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md)方法。  
  
    -   ETW 事件： `ThreadCreated`， `ThreadAppDomainEnter`，和`ThreadTerminated`事件。 有关提供程序和关键字的信息，请参阅"应用程序域资源监视事件"中[CLR ETW 事件](../../../docs/framework/performance/clr-etw-events.md)。  
  
-   **在其生存期内，以字节为单位由应用程序域进行的托管的分配的总**： 总分配并不总是反映内存使用情况应用程序域中，这是因为分配的对象可能生存期较短。 但是，如果应用程序分配和释放大量对象，则分配的开销可能是重要的。  
  
    -   托管 API:<xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>属性。  
  
    -   托管 API: [iclrappdomainresourcemonitor:: Getcurrentallocated](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md)方法。  
  
    -   ETW 事件：`AppDomainMemAllocated`事件，`Allocated`字段。  
  
-   **托管的内存，以字节为单位，所引用的应用程序域和最新的完整、 阻碍性回收后保留下来**： 此数字在是准确仅完整、 阻碍性回收。 （这是与并发集合，在后台进行，不会阻止应用程序相反值。）例如，<xref:System.GC.Collect?displayProperty=nameWithType>方法重载将导致的完整、 阻碍性回收。  
  
    -   托管 API:<xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>属性。  
  
    -   托管 API: [iclrappdomainresourcemonitor:: Getcurrentsurvived](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)方法，`pAppDomainBytesSurvived`参数。  
  
    -   ETW 事件：`AppDomainMemSurvived`事件，`Survived`字段。  
  
-   **托管的内存总量，以字节为单位，所引用的过程和最新的完整、 阻碍性回收后保留下来**： 单个应用程序域保留的内存可以与此数字进行比较。  
  
    -   托管 API:<xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>属性。  
  
    -   托管 API: [iclrappdomainresourcemonitor:: Getcurrentsurvived](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)方法，`pTotalBytesSurvived`参数。  
  
    -   ETW 事件：`AppDomainMemSurvived`事件，`ProcessSurvived`字段。  
  
### <a name="determining-when-a-full-blocking-collection-occurs"></a>确定完整、 阻碍性回收发生  
 若要确定当保留的内存的计数为准确，你需要知道只发生在完整的阻塞集合。 执行此操作的方法取决于你用来检查 ARM 统计信息的 API。  
  
#### <a name="managed-api"></a>托管的 API  
 如果你使用的属性<xref:System.AppDomain>类，可以使用<xref:System.GC.RegisterForFullGCNotification%2A?displayProperty=nameWithType>方法来注册通知的完整集合。 你使用的阈值并不重要，因为正在等待完成的集合，而不是集合的方法。 然后，你可以调用<xref:System.GC.WaitForFullGCComplete%2A?displayProperty=nameWithType>方法，阻塞，直到已完成完整的集合。 你可以创建在循环中调用的方法，并执行任何必需的分析，只要该方法返回的线程。  
  
 或者，可以调用<xref:System.GC.CollectionCount%2A?displayProperty=nameWithType>方法定期以查看已增加了第 2 代回收的计数。 具体取决于轮询频率，此方法可能无法提供一样准确相对值的完整集合中的匹配项。  
  
#### <a name="hosting-api"></a>托管 API  
 如果你使用非托管的托管 API，则你的主机必须传递 CLR 的实现[IHostGCManager](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)接口。 CLR 调用[ihostgcmanager:: Suspensionending](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)方法时才会继续执行的回收发生时已挂起的线程。 使主机可以确定集合是否已完整或部分，CLR 将作为该方法的参数传递已完成的回收的代。 实现[ihostgcmanager:: Suspensionending](../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)方法可以查询有关保留的内存，以确保在更新时，就会立即检索的计数。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
 [ICLRAppDomainResourceMonitor 接口](../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 [\<appDomainResourceMonitoring>](../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)  
 [CLR ETW 事件](../../../docs/framework/performance/clr-etw-events.md)
