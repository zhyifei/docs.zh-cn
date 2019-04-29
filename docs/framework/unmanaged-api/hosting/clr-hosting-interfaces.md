---
title: CLR 承载接口
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03839a2c6e52f9d2dcdd2e0941ff4fdbeb8a3a17
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789657"
---
# <a name="clr-hosting-interfaces"></a><span data-ttu-id="60234-102">CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="60234-102">CLR Hosting Interfaces</span></span>
<span data-ttu-id="60234-103">本部分中描述的接口以及非托管主机可用于将公共语言运行时 (CLR) 集成到其应用程序。</span><span class="sxs-lookup"><span data-stu-id="60234-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span> <span data-ttu-id="60234-104">信息与.NET Framework 2.0 版和更高版本。</span><span class="sxs-lookup"><span data-stu-id="60234-104">The information pertains to the .NET Framework version 2.0 and later versions.</span></span> <span data-ttu-id="60234-105">这些接口使宿主能够控制运行时比在版本 1.0 和 1.1 中，可能的更多方面，并提供 CLR 和主机的执行模型之间更紧密地集成。</span><span class="sxs-lookup"><span data-stu-id="60234-105">These interfaces enable the host to control many more aspects of the runtime than was possible in versions 1.0 and 1.1, and provide much tighter integration between the CLR and the host's execution model.</span></span>  
  
 <span data-ttu-id="60234-106">在.NET Framework 1.0 和 1.1 版中，启用非托管的宿主能够将 CLR 加载到进程中，若要配置某些设置，并接收事件通知宿主模型。</span><span class="sxs-lookup"><span data-stu-id="60234-106">In the .NET Framework version 1.0 and 1.1, the hosting model enabled an unmanaged host to load the CLR into a process, to configure certain settings, and to receive event notifications.</span></span> <span data-ttu-id="60234-107">但是，一般情况下，在主机和 CLR 独立进程中运行的。</span><span class="sxs-lookup"><span data-stu-id="60234-107">However, in general, the host and the CLR ran independently in that process.</span></span> <span data-ttu-id="60234-108">在.NET Framework 2.0 版和更高版本中，新的抽象层允许主机提供了多种 Win32 集中的类型当前提供的资源和扩展的主机可以配置的功能集。</span><span class="sxs-lookup"><span data-stu-id="60234-108">In the .NET Framework version 2.0 and later versions, new layers of abstraction let the host provide many of the resources currently provided by the types in the Win32 assembly, and extend the set of capabilities that the host can configure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="60234-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="60234-109">In This Section</span></span>  
 [<span data-ttu-id="60234-110">IActionOnCLREvent 接口</span><span class="sxs-lookup"><span data-stu-id="60234-110">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 <span data-ttu-id="60234-111">提供为已注册的事件执行回调的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-111">Provides a method that performs a callback for a registered event.</span></span>  
  
 [<span data-ttu-id="60234-112">IApartmentCallback 接口</span><span class="sxs-lookup"><span data-stu-id="60234-112">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)  
 <span data-ttu-id="60234-113">提供用于在单元内使回调方法。</span><span class="sxs-lookup"><span data-stu-id="60234-113">Provides methods for making callbacks within an apartment.</span></span>  
  
 [<span data-ttu-id="60234-114">IAppDomainBinding 接口</span><span class="sxs-lookup"><span data-stu-id="60234-114">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)  
 <span data-ttu-id="60234-115">提供用于设置运行时配置方法。</span><span class="sxs-lookup"><span data-stu-id="60234-115">Provides methods for setting run-time configuration.</span></span>  
  
 [<span data-ttu-id="60234-116">ICatalogServices 接口</span><span class="sxs-lookup"><span data-stu-id="60234-116">ICatalogServices Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icatalogservices-interface.md)  
 <span data-ttu-id="60234-117">提供目录服务的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-117">Provides methods for cataloging services.</span></span> <span data-ttu-id="60234-118">（此接口支持.NET Framework 基础结构，不应在代码中直接使用。）</span><span class="sxs-lookup"><span data-stu-id="60234-118">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="60234-119">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="60234-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 <span data-ttu-id="60234-120">提供支持在主机和有关程序集 CLR 之间的通信的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-120">Provides methods that support communication between the host and the CLR about assemblies.</span></span>  
  
 [<span data-ttu-id="60234-121">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="60234-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 <span data-ttu-id="60234-122">管理由 CLR，而不是由主机加载的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="60234-122">Manages a list of assemblies that are loaded by the CLR and not by the host.</span></span>  
  
 [<span data-ttu-id="60234-123">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="60234-123">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 <span data-ttu-id="60234-124">提供方法来获得访问权限，并配置各个方面的 CLR 的主机。</span><span class="sxs-lookup"><span data-stu-id="60234-124">Provides methods for the host to gain access to, and configure various aspects of, the CLR.</span></span>  
  
 [<span data-ttu-id="60234-125">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="60234-125">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 <span data-ttu-id="60234-126">提供了使宿主能够将一组任务标识符和友好名称与相关联的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-126">Provides methods that enable a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
 [<span data-ttu-id="60234-127">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="60234-127">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 <span data-ttu-id="60234-128">提供了使宿主能够配置自定义堆转储的错误报告的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-128">Provides methods that enable the host to configure custom heap dumps for error reporting.</span></span>  
  
 [<span data-ttu-id="60234-129">ICLRGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="60234-129">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 <span data-ttu-id="60234-130">提供了使宿主能够与 CLR 的垃圾回收系统进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-130">Provides methods that enable a host to interact with the CLR's garbage collection system.</span></span>  
  
 [<span data-ttu-id="60234-131">ICLRHostBindingPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="60234-131">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 <span data-ttu-id="60234-132">提供用于评估，并将程序集的策略信息中的更改通知的主机的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-132">Provides methods for the host to evaluate and communicate changes in policy information for assemblies.</span></span>  
  
 [<span data-ttu-id="60234-133">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="60234-133">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 <span data-ttu-id="60234-134">使宿主能够阻止特定的托管的类、 方法、 属性和字段从部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="60234-134">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
 [<span data-ttu-id="60234-135">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="60234-135">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 <span data-ttu-id="60234-136">实现一个回调方法，使主机来通知 CLR 的指定的 I/O 请求的状态。</span><span class="sxs-lookup"><span data-stu-id="60234-136">Implements a callback method that enables the host to notify the CLR of the status of specified I/O requests.</span></span>  
  
 [<span data-ttu-id="60234-137">ICLRMemoryNotificationCallback 接口</span><span class="sxs-lookup"><span data-stu-id="60234-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 <span data-ttu-id="60234-138">允许宿主来报告内存压力情况使用类似于 Win32 方法`CreateMemoryResourceNotification`函数。</span><span class="sxs-lookup"><span data-stu-id="60234-138">Enables the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
 [<span data-ttu-id="60234-139">ICLROnEventManager 接口</span><span class="sxs-lookup"><span data-stu-id="60234-139">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 <span data-ttu-id="60234-140">提供了使宿主能够注册和注销 CLR 事件的回调的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-140">Provides methods that enable the host to register and unregister callbacks for CLR events.</span></span>  
  
 [<span data-ttu-id="60234-141">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="60234-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 <span data-ttu-id="60234-142">提供了使宿主能够指定发生错误和超时时所采取的策略操作的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-142">Provides methods that enable the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
 [<span data-ttu-id="60234-143">ICLRProbingAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="60234-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)  
 <span data-ttu-id="60234-144">提供启用要使用的是内部的 CLR，而无需创建或了解该标识的程序集的标识信息获取程序集的探测标识的主机的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-144">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the CLR, without needing to create or understand that identity.</span></span>  
  
 [<span data-ttu-id="60234-145">ICLRReferenceAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="60234-145">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)  
 <span data-ttu-id="60234-146">提供了使宿主可以操作的程序集引用的文件或流使用的是内部的 CLR，而无需创建或了解这些标识程序集标识数据集的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-146">Provides methods that enable the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the CLR, without needing to create or understand those identities.</span></span>  
  
 [<span data-ttu-id="60234-147">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="60234-147">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 <span data-ttu-id="60234-148">提供了功能类似于[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)，采用其他方法来设置主机控制界面。</span><span class="sxs-lookup"><span data-stu-id="60234-148">Provides capabilities similar to [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md), with an additional method to set the host control interface.</span></span>  
  
 [<span data-ttu-id="60234-149">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="60234-149">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 <span data-ttu-id="60234-150">提供方法以获取有关请求的任务的信息，或若要在其同步实现中检测到死锁的主机。</span><span class="sxs-lookup"><span data-stu-id="60234-150">Provides methods for the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
 [<span data-ttu-id="60234-151">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="60234-151">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 <span data-ttu-id="60234-152">提供方法，使主机发出请求的 CLR，或向 CLR 有关关联的任务提供通知。</span><span class="sxs-lookup"><span data-stu-id="60234-152">Provides methods that enable the host to make requests of the CLR, or to provide notification to the CLR about the associated task.</span></span>  
  
 [<span data-ttu-id="60234-153">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="60234-153">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 <span data-ttu-id="60234-154">提供了使宿主可以显式请求 CLR 创建新的任务，获取当前正在执行的任务，并设置地理语言和区域性的任务的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-154">Provides methods that enable the host to request explicitly that the CLR create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
 [<span data-ttu-id="60234-155">ICLRValidator 接口</span><span class="sxs-lookup"><span data-stu-id="60234-155">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)  
 <span data-ttu-id="60234-156">提供用于验证可移植可执行 (PE) 映像和报告验证错误的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-156">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
 [<span data-ttu-id="60234-157">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="60234-157">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)  
 <span data-ttu-id="60234-158">提供用于配置 CLR 方法。</span><span class="sxs-lookup"><span data-stu-id="60234-158">Provides methods for configuring the CLR.</span></span>  
  
 [<span data-ttu-id="60234-159">ICorThreadpool 接口</span><span class="sxs-lookup"><span data-stu-id="60234-159">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)  
 <span data-ttu-id="60234-160">提供用于访问该线程池的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-160">Provides methods for accessing the thread pool.</span></span>  
  
 [<span data-ttu-id="60234-161">IDebuggerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="60234-161">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)  
 <span data-ttu-id="60234-162">提供用于获取有关调试的服务的状态信息的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-162">Provides methods for obtaining information about the state of the debugging services.</span></span>  
  
 [<span data-ttu-id="60234-163">IDebuggerThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="60234-163">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)  
 <span data-ttu-id="60234-164">提供用于通知主机有关阻止和取消阻止的线程的调试服务的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-164">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
 [<span data-ttu-id="60234-165">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="60234-165">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)  
 <span data-ttu-id="60234-166">提供方法用于获取有关垃圾回收系统的信息以及用于控制垃圾回收的某些方面。</span><span class="sxs-lookup"><span data-stu-id="60234-166">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
 [<span data-ttu-id="60234-167">IGCHost2 接口</span><span class="sxs-lookup"><span data-stu-id="60234-167">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)  
 <span data-ttu-id="60234-168">提供了[SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)方法，使主机可以设置为值的垃圾回收段的大小和垃圾回收系统生成零的最大大小大于`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="60234-168">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method that enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation zero to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="60234-169">IGCHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="60234-169">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)  
 <span data-ttu-id="60234-170">提供了一个方法，使垃圾回收器请求的主机，若要更改虚拟内存的限制。</span><span class="sxs-lookup"><span data-stu-id="60234-170">Provides a method that enables the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
 [<span data-ttu-id="60234-171">IGCThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="60234-171">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)  
 <span data-ttu-id="60234-172">提供用于参与防止因阻塞而进行垃圾回收的线程的调度方法。</span><span class="sxs-lookup"><span data-stu-id="60234-172">Provides methods for participating in the scheduling of threads that would otherwise be blocked for garbage collection.</span></span>  
  
 [<span data-ttu-id="60234-173">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="60234-173">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 <span data-ttu-id="60234-174">提供了使宿主能够指定的由 CLR 或由主机应加载的程序集的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-174">Provides methods that enable a host to specify sets of assemblies that should be loaded by the CLR or by the host.</span></span>  
  
 [<span data-ttu-id="60234-175">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="60234-175">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 <span data-ttu-id="60234-176">提供了使宿主能够加载程序集和独立于 CLR 模块的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-176">Provides methods that enable a host to load assemblies and modules independently of the CLR.</span></span>  
  
 [<span data-ttu-id="60234-177">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="60234-177">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 <span data-ttu-id="60234-178">提供的表示形式由宿主实现的自动重置事件。</span><span class="sxs-lookup"><span data-stu-id="60234-178">Provides a representation of an auto-reset event implemented by the host.</span></span>  
  
 [<span data-ttu-id="60234-179">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="60234-179">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 <span data-ttu-id="60234-180">提供用于配置加载的程序集，以及用于确定主机支持的托管接口的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-180">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
 [<span data-ttu-id="60234-181">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="60234-181">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 <span data-ttu-id="60234-182">用作主机的临界区对线程处理的表示形式。</span><span class="sxs-lookup"><span data-stu-id="60234-182">Serves as the host's representation of a critical section for threading.</span></span>  
  
 [<span data-ttu-id="60234-183">IHostGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="60234-183">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
 <span data-ttu-id="60234-184">提供通知宿主实现的 CLR 的垃圾回收机制中的事件的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-184">Provides methods that notify the host of events in the garbage collection mechanism implemented by the CLR.</span></span>  
  
 [<span data-ttu-id="60234-185">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="60234-185">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 <span data-ttu-id="60234-186">提供启用 CLR 与 I/O 完成端口提供的主机进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-186">Provides methods that enable the CLR to interact with I/O completion ports provided by the host.</span></span>  
  
 [<span data-ttu-id="60234-187">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="60234-187">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 <span data-ttu-id="60234-188">提供用于从通过主机堆请求细粒度分配的 CLR 方法。</span><span class="sxs-lookup"><span data-stu-id="60234-188">Provides methods for the CLR to request fine-grained allocations from the heap through the host.</span></span>  
  
 [<span data-ttu-id="60234-189">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="60234-189">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 <span data-ttu-id="60234-190">提供的手动重置事件的表示形式的主机的实现。</span><span class="sxs-lookup"><span data-stu-id="60234-190">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
 [<span data-ttu-id="60234-191">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="60234-191">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 <span data-ttu-id="60234-192">提供方法，以便 CLR 可通过主机，而不是使用标准 Win32 虚拟内存函数的虚拟内存请求。</span><span class="sxs-lookup"><span data-stu-id="60234-192">Provides methods for the CLR to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
 [<span data-ttu-id="60234-193">IHostPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="60234-193">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 <span data-ttu-id="60234-194">提供通知的主机的 CLR 的情况下将执行的操作中止、 超时或失败的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-194">Provides methods that notify the host of the actions the CLR performs in case of aborts, timeouts, or failures.</span></span>  
  
 [<span data-ttu-id="60234-195">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="60234-195">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 <span data-ttu-id="60234-196">使 CLR 能够维护由宿主实现的安全上下文信息。</span><span class="sxs-lookup"><span data-stu-id="60234-196">Enables the CLR to maintain security context information implemented by the host.</span></span>  
  
 [<span data-ttu-id="60234-197">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="60234-197">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 <span data-ttu-id="60234-198">提供启用访问权限，并控制当前正在执行的线程的安全上下文的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-198">Provides methods that enable access to, and control over, the security context of the currently executing thread.</span></span>  
  
 [<span data-ttu-id="60234-199">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="60234-199">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 <span data-ttu-id="60234-200">提供的表示形式由宿主实现的信号量。</span><span class="sxs-lookup"><span data-stu-id="60234-200">Provides a representation of a semaphore implemented by the host.</span></span>  
  
 [<span data-ttu-id="60234-201">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="60234-201">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 <span data-ttu-id="60234-202">提供用于通过调用宿主，而不是使用 Win32 同步函数创建同步基元的 CLR 方法。</span><span class="sxs-lookup"><span data-stu-id="60234-202">Provides methods for the CLR to create synchronization primitives by calling the host, instead of using the Win32 synchronization functions.</span></span>  
  
 [<span data-ttu-id="60234-203">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="60234-203">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 <span data-ttu-id="60234-204">提供使 CLR 能够与要管理任务的主机进行通信的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-204">Provides methods that enable the CLR to communicate with the host to manage tasks.</span></span>  
  
 [<span data-ttu-id="60234-205">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="60234-205">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 <span data-ttu-id="60234-206">提供使 CLR 能够使用通过而不是使用标准操作系统线程或纤程函数主机的任务的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-206">Provides methods that enable the CLR to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
 [<span data-ttu-id="60234-207">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="60234-207">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 <span data-ttu-id="60234-208">提供 CLR 线程池配置以及排队到线程池的工作项的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-208">Provides methods for the CLR to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
 [<span data-ttu-id="60234-209">IManagedObject 接口</span><span class="sxs-lookup"><span data-stu-id="60234-209">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)  
 <span data-ttu-id="60234-210">提供用于控制托管的对象的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-210">Provides methods for controlling a managed object.</span></span>  
  
 <span data-ttu-id="60234-211">"IObjectHandle"</span><span class="sxs-lookup"><span data-stu-id="60234-211">"IObjectHandle"</span></span>  
 <span data-ttu-id="60234-212">提供用于寻址从间接寻址打开按值封送的对象的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-212">Provides a method for unwrapping marshal-by-value objects from indirection.</span></span>  
  
 [<span data-ttu-id="60234-213">ITypeName 接口</span><span class="sxs-lookup"><span data-stu-id="60234-213">ITypeName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypename-interface.md)  
 <span data-ttu-id="60234-214">提供用于获取类型名称信息的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-214">Provides methods for obtaining type name information.</span></span> <span data-ttu-id="60234-215">（此接口支持.NET Framework 基础结构，不应在代码中直接使用。）</span><span class="sxs-lookup"><span data-stu-id="60234-215">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="60234-216">ITypeNameBuilder 接口</span><span class="sxs-lookup"><span data-stu-id="60234-216">ITypeNameBuilder Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamebuilder-interface.md)  
 <span data-ttu-id="60234-217">提供用于生成类型名称的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-217">Provides methods for building a type name.</span></span> <span data-ttu-id="60234-218">（此接口支持.NET Framework 基础结构，不应在代码中直接使用。）</span><span class="sxs-lookup"><span data-stu-id="60234-218">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="60234-219">ITypeNameFactory 接口</span><span class="sxs-lookup"><span data-stu-id="60234-219">ITypeNameFactory Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)  
 <span data-ttu-id="60234-220">提供用于析构类型名称的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-220">Provides methods for deconstructing a type name.</span></span> <span data-ttu-id="60234-221">（此接口支持.NET Framework 基础结构，不应在代码中直接使用。）</span><span class="sxs-lookup"><span data-stu-id="60234-221">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 <span data-ttu-id="60234-222">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="60234-222">"IValidator"</span></span>  
 <span data-ttu-id="60234-223">提供用于验证可移植可执行 (PE) 映像和报告验证错误的方法。</span><span class="sxs-lookup"><span data-stu-id="60234-223">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="60234-224">相关章节</span><span class="sxs-lookup"><span data-stu-id="60234-224">Related Sections</span></span>  
 [<span data-ttu-id="60234-225">弃用的 CLR 承接接口和组件类</span><span class="sxs-lookup"><span data-stu-id="60234-225">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="60234-226">包含描述.NET Framework 1.0 和 1.1 版中提供的托管接口的主题。</span><span class="sxs-lookup"><span data-stu-id="60234-226">Contains topics that describe the hosting interfaces provided in the .NET Framework version 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="60234-227">.NET Framework 4 和 4.5 中添加的 CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="60234-227">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="60234-228">包含的主题描述中提供的托管接口[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="60234-228">Contains topics that describe the hosting interfaces provided in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>
