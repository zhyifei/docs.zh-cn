---
title: "CLR 承载接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3efdf649d0039f2eb6b39d5cb17c839b90e97508
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="clr-hosting-interfaces"></a>CLR 承载接口
本部分描述的接口以及非托管主机可用于将公共语言运行时 (CLR) 集成到其应用程序。 信息适用于.NET Framework 2.0 版和更高版本。 这些接口使主机能够控制运行时比版本 1.0 和 1.1 中，可能更多方面，并提供 CLR 和主机的执行模型之间更紧密地集成。  
  
 在.NET Framework 1.0 和 1.1 版中，承载模型启用非托管的主机将 CLR 加载到进程，将配置某些设置，以及接收事件通知。 但是，一般情况下，在主机和 CLR 独立该在进程中运行。 在.NET Framework 2.0 版和更高版本中，新的抽象层让主机提供很多当前由在 Win32 程序集中，类型提供的资源和扩展的主机可以配置的功能集。  
  
## <a name="in-this-section"></a>本节内容  
 [IActionOnCLREvent 接口](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 提供为已注册的事件执行回调的方法。  
  
 [IApartmentCallback 接口](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 提供用于在单元内进行回调方法。  
  
 [IAppDomainBinding 接口](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 提供用于设置运行时配置方法。  
  
 [ICatalogServices 接口](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 提供用于编录服务的方法。 （此接口支持.NET Framework 基础结构，不宜在代码中直接使用。）  
  
 [ICLRAssemblyIdentityManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 提供用于支持在主机和有关程序集 CLR 之间的通信方法。  
  
 [ICLRAssemblyReferenceList 接口](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 管理由 CLR 而不是主机加载的程序集的列表。  
  
 [ICLRControl 接口](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 提供主机访问，并配置的 CLR 的各个方面的方法。  
  
 [ICLRDebugManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 提供使主机能够将一组任务标识符和友好名称与相关联的方法。  
  
 [ICLRErrorReportingManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 提供使主机能够为错误报告配置自定义的堆转储的方法。  
  
 [ICLRGCManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 提供使主机能够与 CLR 的垃圾回收系统进行交互的方法。  
  
 [ICLRHostBindingPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 提供用于主机评估并将程序集的策略信息中的更改通知方法。  
  
 [ICLRHostProtectionManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 使主机可以阻止特定的托管的类、 方法、 属性和字段从部分受信任的代码中运行。  
  
 [ICLRIoCompletionManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 实现使宿主能够通知指定的输入/输出请求的状态的 CLR 的回调方法。  
  
 [ICLRMemoryNotificationCallback 接口](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 允许宿主来报告内存压力情况使用类似于 Win32 方法`CreateMemoryResourceNotification`函数。  
  
 [ICLROnEventManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 提供使主机能够注册和注销 CLR 事件的回调的方法。  
  
 [ICLRPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 提供使主机能够指定要执行发生故障和超时策略操作的方法。  
  
 [ICLRProbingAssemblyEnum 接口](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 提供使主机能够通过使用是内部的 CLR，而无需了解该标识或创建的程序集的标识信息来获取程序集的探测标识的方法。  
  
 [ICLRReferenceAssemblyEnum 接口](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 提供使主机能够操作的文件或使用程序集是内部的 CLR，而无需创建或了解这些标识的标识数据的流由引用的程序集的方法。  
  
 [ICLRRuntimeHost 接口](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 提供功能类似于[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)，与其他方法将主机控件接口设置。  
  
 [ICLRSyncManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 提供方法以获取有关请求的任务的信息并在其同步实现检测死锁的主机。  
  
 [ICLRTask 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 提供一些方法，请启用主机发出请求的 CLR，或向 CLR 有关关联的任务提供通知。  
  
 [ICLRTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 提供使主机能够 CLR 创建新任务、 获取当前正在执行的任务，并设置地理语言和任务的区域性显式请求的方法。  
  
 [ICLRValidator 接口](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 提供用于验证可移植可执行 (PE) 映像和报告验证错误的方法。  
  
 [ICorConfiguration 接口](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 提供用于配置 CLR 方法。  
  
 [ICorThreadpool 接口](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 提供用于访问线程池的方法。  
  
 [IDebuggerInfo 接口](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 提供用于获取有关调试服务的状态信息的方法。  
  
 [IDebuggerThreadControl 接口](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 提供用于通知主机有关阻止和取消阻止的线程调试服务的方法。  
  
 [IGCHost 接口](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 提供用于获取有关垃圾回收系统的信息以及控制垃圾回收的某些方面的方法。  
  
 [IGCHost2 接口](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 提供[SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)方法，使主机设置为值的垃圾回收段的大小和垃圾回收系统生成零的最大大小大于`DWORD`。  
  
 [IGCHostControl 接口](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 提供一个方法，使垃圾回收器请求主机后，若要更改的虚拟内存限制。  
  
 [IGCThreadControl 接口](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 提供用于参与否则会阻止垃圾回收的线程调度的方法。  
  
 [IHostAssemblyManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 提供使主机能够指定的由 CLR 或主机应加载的程序集的方法。  
  
 [IHostAssemblyStore 接口](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 提供使主机能够加载程序集和独立于 CLR 模块的方法。  
  
 [IHostAutoEvent 接口](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 提供的表示形式由宿主实现的自动重置事件。  
  
 [IHostControl 接口](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 提供用于配置加载的程序集，以及用于确定主机支持哪些承载接口方法。  
  
 [IHostCrst 接口](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 用作主机的表示形式的线程处理关键部分。  
  
 [IHostGCManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 提供通知宿主的垃圾回收机制由 CLR 实现中的事件的方法。  
  
 [IHostIoCompletionManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 提供启用 CLR 与主机提供的 I/O 完成端口进行交互的方法。  
  
 [IHostMalloc 接口](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 提供 CLR 从通过主机堆请求细粒度分配方法。  
  
 [IHostManualEvent 接口](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 提供的表示形式的手动重置事件主机的实现。  
  
 [IHostMemoryManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 提供 CLR 发出通过主机，而不是使用标准 Win32 虚拟内存函数的虚拟内存请求的方法。  
  
 [IHostPolicyManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 提供通知的 CLR 的情况下将执行的操作主机中止、 超时或失败的方法。  
  
 [IHostSecurityContext 接口](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 启用 CLR 能够维护由宿主实现的安全上下文信息。  
  
 [IHostSecurityManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 提供启用访问，并控制当前正在执行的线程的安全上下文的方法。  
  
 [IHostSemaphore 接口](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 提供的表示形式由宿主实现的信号量。  
  
 [IHostSyncManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 提供 CLR 通过调用主机，而不是使用 Win32 同步函数创建同步基元的方法。  
  
 [IHostTask 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 提供启用 CLR 与要管理任务的主机进行通信的方法。  
  
 [IHostTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 提供启用 CLR 能够来处理通过主机而不是使用标准操作系统线程处理或纤程函数的任务的方法。  
  
 [IHostThreadPoolManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 提供 CLR 配置线程池以及排队到线程池工作项的方法。  
  
 [IManagedObject 接口](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 提供用于控制托管的对象的方法。  
  
 "IObjectHandle"  
 提供用于从间接寻址的寻址封送按值对象的方法。  
  
 [ITypeName 接口](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 提供用于获取类型名称信息的方法。 （此接口支持.NET Framework 基础结构，不宜在代码中直接使用。）  
  
 [ITypeNameBuilder 接口](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 提供用于生成的类型名称的方法。 （此接口支持.NET Framework 基础结构，不宜在代码中直接使用。）  
  
 [ITypeNameFactory 接口](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 提供用于解构类型名称的方法。 （此接口支持.NET Framework 基础结构，不宜在代码中直接使用。）  
  
 "IValidator"  
 提供用于验证可移植可执行 (PE) 映像和报告验证错误的方法。  
  
## <a name="related-sections"></a>相关章节  
 [弃用的 CLR 承载接口和组件类](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 包含描述.NET Framework 1.0 和 1.1 版中提供的托管接口的主题。  
  
 [CLR 承载接口添加在.NET Framework 4 和 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 包含描述中提供的托管接口的主题[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。
