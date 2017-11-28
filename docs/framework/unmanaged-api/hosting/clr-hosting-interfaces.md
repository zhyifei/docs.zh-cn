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
# <a name="clr-hosting-interfaces"></a><span data-ttu-id="596af-102">CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="596af-102">CLR Hosting Interfaces</span></span>
<span data-ttu-id="596af-103">本部分描述的接口以及非托管主机可用于将公共语言运行时 (CLR) 集成到其应用程序。</span><span class="sxs-lookup"><span data-stu-id="596af-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span> <span data-ttu-id="596af-104">信息适用于.NET Framework 2.0 版和更高版本。</span><span class="sxs-lookup"><span data-stu-id="596af-104">The information pertains to the .NET Framework version 2.0 and later versions.</span></span> <span data-ttu-id="596af-105">这些接口使主机能够控制运行时比版本 1.0 和 1.1 中，可能更多方面，并提供 CLR 和主机的执行模型之间更紧密地集成。</span><span class="sxs-lookup"><span data-stu-id="596af-105">These interfaces enable the host to control many more aspects of the runtime than was possible in versions 1.0 and 1.1, and provide much tighter integration between the CLR and the host's execution model.</span></span>  
  
 <span data-ttu-id="596af-106">在.NET Framework 1.0 和 1.1 版中，承载模型启用非托管的主机将 CLR 加载到进程，将配置某些设置，以及接收事件通知。</span><span class="sxs-lookup"><span data-stu-id="596af-106">In the .NET Framework version 1.0 and 1.1, the hosting model enabled an unmanaged host to load the CLR into a process, to configure certain settings, and to receive event notifications.</span></span> <span data-ttu-id="596af-107">但是，一般情况下，在主机和 CLR 独立该在进程中运行。</span><span class="sxs-lookup"><span data-stu-id="596af-107">However, in general, the host and the CLR ran independently in that process.</span></span> <span data-ttu-id="596af-108">在.NET Framework 2.0 版和更高版本中，新的抽象层让主机提供很多当前由在 Win32 程序集中，类型提供的资源和扩展的主机可以配置的功能集。</span><span class="sxs-lookup"><span data-stu-id="596af-108">In the .NET Framework version 2.0 and later versions, new layers of abstraction let the host provide many of the resources currently provided by the types in the Win32 assembly, and extend the set of capabilities that the host can configure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="596af-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="596af-109">In This Section</span></span>  
 [<span data-ttu-id="596af-110">IActionOnCLREvent 接口</span><span class="sxs-lookup"><span data-stu-id="596af-110">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 <span data-ttu-id="596af-111">提供为已注册的事件执行回调的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-111">Provides a method that performs a callback for a registered event.</span></span>  
  
 [<span data-ttu-id="596af-112">IApartmentCallback 接口</span><span class="sxs-lookup"><span data-stu-id="596af-112">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 <span data-ttu-id="596af-113">提供用于在单元内进行回调方法。</span><span class="sxs-lookup"><span data-stu-id="596af-113">Provides methods for making callbacks within an apartment.</span></span>  
  
 [<span data-ttu-id="596af-114">IAppDomainBinding 接口</span><span class="sxs-lookup"><span data-stu-id="596af-114">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 <span data-ttu-id="596af-115">提供用于设置运行时配置方法。</span><span class="sxs-lookup"><span data-stu-id="596af-115">Provides methods for setting run-time configuration.</span></span>  
  
 [<span data-ttu-id="596af-116">ICatalogServices 接口</span><span class="sxs-lookup"><span data-stu-id="596af-116">ICatalogServices Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 <span data-ttu-id="596af-117">提供用于编录服务的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-117">Provides methods for cataloging services.</span></span> <span data-ttu-id="596af-118">（此接口支持.NET Framework 基础结构，不宜在代码中直接使用。）</span><span class="sxs-lookup"><span data-stu-id="596af-118">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="596af-119">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="596af-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 <span data-ttu-id="596af-120">提供用于支持在主机和有关程序集 CLR 之间的通信方法。</span><span class="sxs-lookup"><span data-stu-id="596af-120">Provides methods that support communication between the host and the CLR about assemblies.</span></span>  
  
 [<span data-ttu-id="596af-121">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="596af-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 <span data-ttu-id="596af-122">管理由 CLR 而不是主机加载的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="596af-122">Manages a list of assemblies that are loaded by the CLR and not by the host.</span></span>  
  
 [<span data-ttu-id="596af-123">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="596af-123">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 <span data-ttu-id="596af-124">提供主机访问，并配置的 CLR 的各个方面的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-124">Provides methods for the host to gain access to, and configure various aspects of, the CLR.</span></span>  
  
 [<span data-ttu-id="596af-125">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="596af-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 <span data-ttu-id="596af-126">提供使主机能够将一组任务标识符和友好名称与相关联的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-126">Provides methods that enable a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
 [<span data-ttu-id="596af-127">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="596af-127">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 <span data-ttu-id="596af-128">提供使主机能够为错误报告配置自定义的堆转储的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-128">Provides methods that enable the host to configure custom heap dumps for error reporting.</span></span>  
  
 [<span data-ttu-id="596af-129">ICLRGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="596af-129">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 <span data-ttu-id="596af-130">提供使主机能够与 CLR 的垃圾回收系统进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-130">Provides methods that enable a host to interact with the CLR's garbage collection system.</span></span>  
  
 [<span data-ttu-id="596af-131">ICLRHostBindingPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="596af-131">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 <span data-ttu-id="596af-132">提供用于主机评估并将程序集的策略信息中的更改通知方法。</span><span class="sxs-lookup"><span data-stu-id="596af-132">Provides methods for the host to evaluate and communicate changes in policy information for assemblies.</span></span>  
  
 [<span data-ttu-id="596af-133">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="596af-133">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 <span data-ttu-id="596af-134">使主机可以阻止特定的托管的类、 方法、 属性和字段从部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="596af-134">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
 [<span data-ttu-id="596af-135">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="596af-135">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 <span data-ttu-id="596af-136">实现使宿主能够通知指定的输入/输出请求的状态的 CLR 的回调方法。</span><span class="sxs-lookup"><span data-stu-id="596af-136">Implements a callback method that enables the host to notify the CLR of the status of specified I/O requests.</span></span>  
  
 [<span data-ttu-id="596af-137">ICLRMemoryNotificationCallback 接口</span><span class="sxs-lookup"><span data-stu-id="596af-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 <span data-ttu-id="596af-138">允许宿主来报告内存压力情况使用类似于 Win32 方法`CreateMemoryResourceNotification`函数。</span><span class="sxs-lookup"><span data-stu-id="596af-138">Enables the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
 [<span data-ttu-id="596af-139">ICLROnEventManager 接口</span><span class="sxs-lookup"><span data-stu-id="596af-139">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 <span data-ttu-id="596af-140">提供使主机能够注册和注销 CLR 事件的回调的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-140">Provides methods that enable the host to register and unregister callbacks for CLR events.</span></span>  
  
 [<span data-ttu-id="596af-141">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="596af-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 <span data-ttu-id="596af-142">提供使主机能够指定要执行发生故障和超时策略操作的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-142">Provides methods that enable the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
 [<span data-ttu-id="596af-143">ICLRProbingAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="596af-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 <span data-ttu-id="596af-144">提供使主机能够通过使用是内部的 CLR，而无需了解该标识或创建的程序集的标识信息来获取程序集的探测标识的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-144">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the CLR, without needing to create or understand that identity.</span></span>  
  
 [<span data-ttu-id="596af-145">ICLRReferenceAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="596af-145">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 <span data-ttu-id="596af-146">提供使主机能够操作的文件或使用程序集是内部的 CLR，而无需创建或了解这些标识的标识数据的流由引用的程序集的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-146">Provides methods that enable the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the CLR, without needing to create or understand those identities.</span></span>  
  
 [<span data-ttu-id="596af-147">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="596af-147">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 <span data-ttu-id="596af-148">提供功能类似于[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)，与其他方法将主机控件接口设置。</span><span class="sxs-lookup"><span data-stu-id="596af-148">Provides capabilities similar to [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), with an additional method to set the host control interface.</span></span>  
  
 [<span data-ttu-id="596af-149">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="596af-149">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 <span data-ttu-id="596af-150">提供方法以获取有关请求的任务的信息并在其同步实现检测死锁的主机。</span><span class="sxs-lookup"><span data-stu-id="596af-150">Provides methods for the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
 [<span data-ttu-id="596af-151">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="596af-151">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 <span data-ttu-id="596af-152">提供一些方法，请启用主机发出请求的 CLR，或向 CLR 有关关联的任务提供通知。</span><span class="sxs-lookup"><span data-stu-id="596af-152">Provides methods that enable the host to make requests of the CLR, or to provide notification to the CLR about the associated task.</span></span>  
  
 [<span data-ttu-id="596af-153">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="596af-153">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 <span data-ttu-id="596af-154">提供使主机能够 CLR 创建新任务、 获取当前正在执行的任务，并设置地理语言和任务的区域性显式请求的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-154">Provides methods that enable the host to request explicitly that the CLR create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
 [<span data-ttu-id="596af-155">ICLRValidator 接口</span><span class="sxs-lookup"><span data-stu-id="596af-155">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 <span data-ttu-id="596af-156">提供用于验证可移植可执行 (PE) 映像和报告验证错误的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-156">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
 [<span data-ttu-id="596af-157">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="596af-157">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 <span data-ttu-id="596af-158">提供用于配置 CLR 方法。</span><span class="sxs-lookup"><span data-stu-id="596af-158">Provides methods for configuring the CLR.</span></span>  
  
 [<span data-ttu-id="596af-159">ICorThreadpool 接口</span><span class="sxs-lookup"><span data-stu-id="596af-159">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 <span data-ttu-id="596af-160">提供用于访问线程池的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-160">Provides methods for accessing the thread pool.</span></span>  
  
 [<span data-ttu-id="596af-161">IDebuggerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="596af-161">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 <span data-ttu-id="596af-162">提供用于获取有关调试服务的状态信息的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-162">Provides methods for obtaining information about the state of the debugging services.</span></span>  
  
 [<span data-ttu-id="596af-163">IDebuggerThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="596af-163">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 <span data-ttu-id="596af-164">提供用于通知主机有关阻止和取消阻止的线程调试服务的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-164">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
 [<span data-ttu-id="596af-165">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="596af-165">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 <span data-ttu-id="596af-166">提供用于获取有关垃圾回收系统的信息以及控制垃圾回收的某些方面的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-166">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
 [<span data-ttu-id="596af-167">IGCHost2 接口</span><span class="sxs-lookup"><span data-stu-id="596af-167">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 <span data-ttu-id="596af-168">提供[SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)方法，使主机设置为值的垃圾回收段的大小和垃圾回收系统生成零的最大大小大于`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="596af-168">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method that enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation zero to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="596af-169">IGCHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="596af-169">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 <span data-ttu-id="596af-170">提供一个方法，使垃圾回收器请求主机后，若要更改的虚拟内存限制。</span><span class="sxs-lookup"><span data-stu-id="596af-170">Provides a method that enables the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
 [<span data-ttu-id="596af-171">IGCThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="596af-171">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 <span data-ttu-id="596af-172">提供用于参与否则会阻止垃圾回收的线程调度的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-172">Provides methods for participating in the scheduling of threads that would otherwise be blocked for garbage collection.</span></span>  
  
 [<span data-ttu-id="596af-173">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="596af-173">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 <span data-ttu-id="596af-174">提供使主机能够指定的由 CLR 或主机应加载的程序集的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-174">Provides methods that enable a host to specify sets of assemblies that should be loaded by the CLR or by the host.</span></span>  
  
 [<span data-ttu-id="596af-175">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="596af-175">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 <span data-ttu-id="596af-176">提供使主机能够加载程序集和独立于 CLR 模块的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-176">Provides methods that enable a host to load assemblies and modules independently of the CLR.</span></span>  
  
 [<span data-ttu-id="596af-177">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="596af-177">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 <span data-ttu-id="596af-178">提供的表示形式由宿主实现的自动重置事件。</span><span class="sxs-lookup"><span data-stu-id="596af-178">Provides a representation of an auto-reset event implemented by the host.</span></span>  
  
 [<span data-ttu-id="596af-179">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="596af-179">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 <span data-ttu-id="596af-180">提供用于配置加载的程序集，以及用于确定主机支持哪些承载接口方法。</span><span class="sxs-lookup"><span data-stu-id="596af-180">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
 [<span data-ttu-id="596af-181">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="596af-181">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 <span data-ttu-id="596af-182">用作主机的表示形式的线程处理关键部分。</span><span class="sxs-lookup"><span data-stu-id="596af-182">Serves as the host's representation of a critical section for threading.</span></span>  
  
 [<span data-ttu-id="596af-183">IHostGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="596af-183">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 <span data-ttu-id="596af-184">提供通知宿主的垃圾回收机制由 CLR 实现中的事件的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-184">Provides methods that notify the host of events in the garbage collection mechanism implemented by the CLR.</span></span>  
  
 [<span data-ttu-id="596af-185">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="596af-185">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 <span data-ttu-id="596af-186">提供启用 CLR 与主机提供的 I/O 完成端口进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-186">Provides methods that enable the CLR to interact with I/O completion ports provided by the host.</span></span>  
  
 [<span data-ttu-id="596af-187">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="596af-187">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 <span data-ttu-id="596af-188">提供 CLR 从通过主机堆请求细粒度分配方法。</span><span class="sxs-lookup"><span data-stu-id="596af-188">Provides methods for the CLR to request fine-grained allocations from the heap through the host.</span></span>  
  
 [<span data-ttu-id="596af-189">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="596af-189">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 <span data-ttu-id="596af-190">提供的表示形式的手动重置事件主机的实现。</span><span class="sxs-lookup"><span data-stu-id="596af-190">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
 [<span data-ttu-id="596af-191">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="596af-191">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 <span data-ttu-id="596af-192">提供 CLR 发出通过主机，而不是使用标准 Win32 虚拟内存函数的虚拟内存请求的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-192">Provides methods for the CLR to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
 [<span data-ttu-id="596af-193">IHostPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="596af-193">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 <span data-ttu-id="596af-194">提供通知的 CLR 的情况下将执行的操作主机中止、 超时或失败的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-194">Provides methods that notify the host of the actions the CLR performs in case of aborts, timeouts, or failures.</span></span>  
  
 [<span data-ttu-id="596af-195">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="596af-195">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 <span data-ttu-id="596af-196">启用 CLR 能够维护由宿主实现的安全上下文信息。</span><span class="sxs-lookup"><span data-stu-id="596af-196">Enables the CLR to maintain security context information implemented by the host.</span></span>  
  
 [<span data-ttu-id="596af-197">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="596af-197">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 <span data-ttu-id="596af-198">提供启用访问，并控制当前正在执行的线程的安全上下文的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-198">Provides methods that enable access to, and control over, the security context of the currently executing thread.</span></span>  
  
 [<span data-ttu-id="596af-199">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="596af-199">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 <span data-ttu-id="596af-200">提供的表示形式由宿主实现的信号量。</span><span class="sxs-lookup"><span data-stu-id="596af-200">Provides a representation of a semaphore implemented by the host.</span></span>  
  
 [<span data-ttu-id="596af-201">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="596af-201">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 <span data-ttu-id="596af-202">提供 CLR 通过调用主机，而不是使用 Win32 同步函数创建同步基元的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-202">Provides methods for the CLR to create synchronization primitives by calling the host, instead of using the Win32 synchronization functions.</span></span>  
  
 [<span data-ttu-id="596af-203">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="596af-203">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 <span data-ttu-id="596af-204">提供启用 CLR 与要管理任务的主机进行通信的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-204">Provides methods that enable the CLR to communicate with the host to manage tasks.</span></span>  
  
 [<span data-ttu-id="596af-205">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="596af-205">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 <span data-ttu-id="596af-206">提供启用 CLR 能够来处理通过主机而不是使用标准操作系统线程处理或纤程函数的任务的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-206">Provides methods that enable the CLR to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
 [<span data-ttu-id="596af-207">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="596af-207">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 <span data-ttu-id="596af-208">提供 CLR 配置线程池以及排队到线程池工作项的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-208">Provides methods for the CLR to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
 [<span data-ttu-id="596af-209">IManagedObject 接口</span><span class="sxs-lookup"><span data-stu-id="596af-209">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 <span data-ttu-id="596af-210">提供用于控制托管的对象的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-210">Provides methods for controlling a managed object.</span></span>  
  
 <span data-ttu-id="596af-211">"IObjectHandle"</span><span class="sxs-lookup"><span data-stu-id="596af-211">"IObjectHandle"</span></span>  
 <span data-ttu-id="596af-212">提供用于从间接寻址的寻址封送按值对象的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-212">Provides a method for unwrapping marshal-by-value objects from indirection.</span></span>  
  
 [<span data-ttu-id="596af-213">ITypeName 接口</span><span class="sxs-lookup"><span data-stu-id="596af-213">ITypeName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 <span data-ttu-id="596af-214">提供用于获取类型名称信息的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-214">Provides methods for obtaining type name information.</span></span> <span data-ttu-id="596af-215">（此接口支持.NET Framework 基础结构，不宜在代码中直接使用。）</span><span class="sxs-lookup"><span data-stu-id="596af-215">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="596af-216">ITypeNameBuilder 接口</span><span class="sxs-lookup"><span data-stu-id="596af-216">ITypeNameBuilder Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 <span data-ttu-id="596af-217">提供用于生成的类型名称的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-217">Provides methods for building a type name.</span></span> <span data-ttu-id="596af-218">（此接口支持.NET Framework 基础结构，不宜在代码中直接使用。）</span><span class="sxs-lookup"><span data-stu-id="596af-218">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="596af-219">ITypeNameFactory 接口</span><span class="sxs-lookup"><span data-stu-id="596af-219">ITypeNameFactory Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 <span data-ttu-id="596af-220">提供用于解构类型名称的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-220">Provides methods for deconstructing a type name.</span></span> <span data-ttu-id="596af-221">（此接口支持.NET Framework 基础结构，不宜在代码中直接使用。）</span><span class="sxs-lookup"><span data-stu-id="596af-221">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 <span data-ttu-id="596af-222">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="596af-222">"IValidator"</span></span>  
 <span data-ttu-id="596af-223">提供用于验证可移植可执行 (PE) 映像和报告验证错误的方法。</span><span class="sxs-lookup"><span data-stu-id="596af-223">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="596af-224">相关章节</span><span class="sxs-lookup"><span data-stu-id="596af-224">Related Sections</span></span>  
 [<span data-ttu-id="596af-225">弃用的 CLR 承载接口和组件类</span><span class="sxs-lookup"><span data-stu-id="596af-225">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="596af-226">包含描述.NET Framework 1.0 和 1.1 版中提供的托管接口的主题。</span><span class="sxs-lookup"><span data-stu-id="596af-226">Contains topics that describe the hosting interfaces provided in the .NET Framework version 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="596af-227">CLR 承载接口添加在.NET Framework 4 和 4.5</span><span class="sxs-lookup"><span data-stu-id="596af-227">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="596af-228">包含描述中提供的托管接口的主题[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="596af-228">Contains topics that describe the hosting interfaces provided in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>
