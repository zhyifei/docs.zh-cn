---
title: CLR 承载接口
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 2.0
- hosting interfaces [.NET Framework], version 2.0
- .NET Framework 2.0, hosting interfaces
ms.assetid: 703b8381-43db-4a4d-9faa-cca39302d922
ms.openlocfilehash: e6913e18a4ff6e616f357a4ef43fb8b892264943
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616835"
---
# <a name="clr-hosting-interfaces"></a><span data-ttu-id="534c8-102">CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="534c8-102">CLR Hosting Interfaces</span></span>
<span data-ttu-id="534c8-103">本节介绍非托管主机可用于将公共语言运行时（CLR）集成到其应用程序中的接口。</span><span class="sxs-lookup"><span data-stu-id="534c8-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span> <span data-ttu-id="534c8-104">此信息适用于2.0 版及更高版本的 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="534c8-104">The information pertains to the .NET Framework version 2.0 and later versions.</span></span> <span data-ttu-id="534c8-105">这些接口使宿主能够控制运行时的更多方面，而不是在版本1.0 和1.1 中提供的，并且在 CLR 与宿主的执行模型之间提供了更紧密的集成。</span><span class="sxs-lookup"><span data-stu-id="534c8-105">These interfaces enable the host to control many more aspects of the runtime than was possible in versions 1.0 and 1.1, and provide much tighter integration between the CLR and the host's execution model.</span></span>  
  
 <span data-ttu-id="534c8-106">在 .NET Framework 版本1.0 和1.1 中，托管模型启用了一个非托管主机，用于将 CLR 加载到进程中、配置特定设置以及接收事件通知。</span><span class="sxs-lookup"><span data-stu-id="534c8-106">In the .NET Framework version 1.0 and 1.1, the hosting model enabled an unmanaged host to load the CLR into a process, to configure certain settings, and to receive event notifications.</span></span> <span data-ttu-id="534c8-107">不过，通常情况下，主机和 CLR 在该进程中单独运行。</span><span class="sxs-lookup"><span data-stu-id="534c8-107">However, in general, the host and the CLR ran independently in that process.</span></span> <span data-ttu-id="534c8-108">在 .NET Framework 版本2.0 及更高版本中，新的抽象层允许宿主提供当前由 Win32 程序集中的类型提供的多个资源，并扩展主机可配置的功能集。</span><span class="sxs-lookup"><span data-stu-id="534c8-108">In the .NET Framework version 2.0 and later versions, new layers of abstraction let the host provide many of the resources currently provided by the types in the Win32 assembly, and extend the set of capabilities that the host can configure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="534c8-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="534c8-109">In This Section</span></span>  
 [<span data-ttu-id="534c8-110">IActionOnCLREvent 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-110">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)  
 <span data-ttu-id="534c8-111">提供一个方法，该方法对已注册的事件执行回调。</span><span class="sxs-lookup"><span data-stu-id="534c8-111">Provides a method that performs a callback for a registered event.</span></span>  
  
 [<span data-ttu-id="534c8-112">IApartmentCallback 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-112">IApartmentCallback Interface</span></span>](iapartmentcallback-interface.md)  
 <span data-ttu-id="534c8-113">提供用于在单元中进行回调的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-113">Provides methods for making callbacks within an apartment.</span></span>  
  
 [<span data-ttu-id="534c8-114">IAppDomainBinding 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-114">IAppDomainBinding Interface</span></span>](iappdomainbinding-interface.md)  
 <span data-ttu-id="534c8-115">提供设置运行时配置的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-115">Provides methods for setting run-time configuration.</span></span>  
  
 [<span data-ttu-id="534c8-116">ICatalogServices 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-116">ICatalogServices Interface</span></span>](icatalogservices-interface.md)  
 <span data-ttu-id="534c8-117">提供用于编录服务的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-117">Provides methods for cataloging services.</span></span> <span data-ttu-id="534c8-118">（此接口支持 .NET Framework 基础结构，不应在代码中直接使用。）</span><span class="sxs-lookup"><span data-stu-id="534c8-118">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="534c8-119">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-119">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)  
 <span data-ttu-id="534c8-120">提供一些方法，这些方法支持宿主与 CLR 之间的有关程序集的通信。</span><span class="sxs-lookup"><span data-stu-id="534c8-120">Provides methods that support communication between the host and the CLR about assemblies.</span></span>  
  
 [<span data-ttu-id="534c8-121">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-121">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)  
 <span data-ttu-id="534c8-122">管理由 CLR （而不是由主机）加载的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="534c8-122">Manages a list of assemblies that are loaded by the CLR and not by the host.</span></span>  
  
 [<span data-ttu-id="534c8-123">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-123">ICLRControl Interface</span></span>](iclrcontrol-interface.md)  
 <span data-ttu-id="534c8-124">为宿主提供方法，以获取和配置 CLR 的各个方面。</span><span class="sxs-lookup"><span data-stu-id="534c8-124">Provides methods for the host to gain access to, and configure various aspects of, the CLR.</span></span>  
  
 [<span data-ttu-id="534c8-125">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-125">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)  
 <span data-ttu-id="534c8-126">提供使宿主可以将一组任务与标识符和友好名称关联的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-126">Provides methods that enable a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
 [<span data-ttu-id="534c8-127">ICLRErrorReportingManager 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-127">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)  
 <span data-ttu-id="534c8-128">提供使宿主可以配置自定义堆转储以用于错误报告的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-128">Provides methods that enable the host to configure custom heap dumps for error reporting.</span></span>  
  
 [<span data-ttu-id="534c8-129">ICLRGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-129">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)  
 <span data-ttu-id="534c8-130">提供使宿主能够与 CLR 的垃圾回收系统交互的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-130">Provides methods that enable a host to interact with the CLR's garbage collection system.</span></span>  
  
 [<span data-ttu-id="534c8-131">ICLRHostBindingPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-131">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)  
 <span data-ttu-id="534c8-132">为宿主提供方法，用于计算和传达程序集策略信息中的更改。</span><span class="sxs-lookup"><span data-stu-id="534c8-132">Provides methods for the host to evaluate and communicate changes in policy information for assemblies.</span></span>  
  
 [<span data-ttu-id="534c8-133">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-133">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)  
 <span data-ttu-id="534c8-134">允许宿主阻止在部分受信任的代码中运行特定的托管类、方法、属性和字段。</span><span class="sxs-lookup"><span data-stu-id="534c8-134">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
 [<span data-ttu-id="534c8-135">ICLRIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-135">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)  
 <span data-ttu-id="534c8-136">实现一个回调方法，该方法使宿主能够向 CLR 通知指定 i/o 请求的状态。</span><span class="sxs-lookup"><span data-stu-id="534c8-136">Implements a callback method that enables the host to notify the CLR of the status of specified I/O requests.</span></span>  
  
 [<span data-ttu-id="534c8-137">ICLRMemoryNotificationCallback 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-137">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)  
 <span data-ttu-id="534c8-138">允许主机使用类似于 Win32 函数的方法来报告内存压力情况 `CreateMemoryResourceNotification` 。</span><span class="sxs-lookup"><span data-stu-id="534c8-138">Enables the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
 [<span data-ttu-id="534c8-139">ICLROnEventManager 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-139">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)  
 <span data-ttu-id="534c8-140">提供使宿主能够注册和注销 CLR 事件的回调的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-140">Provides methods that enable the host to register and unregister callbacks for CLR events.</span></span>  
  
 [<span data-ttu-id="534c8-141">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-141">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)  
 <span data-ttu-id="534c8-142">提供使宿主可以指定在发生故障和超时时要执行的策略操作的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-142">Provides methods that enable the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
 [<span data-ttu-id="534c8-143">ICLRProbingAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-143">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)  
 <span data-ttu-id="534c8-144">提供使宿主可以通过使用 CLR 内部的程序集的标识信息来获取程序集的探测标识的方法，无需创建或了解该标识。</span><span class="sxs-lookup"><span data-stu-id="534c8-144">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the CLR, without needing to create or understand that identity.</span></span>  
  
 [<span data-ttu-id="534c8-145">ICLRReferenceAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-145">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)  
 <span data-ttu-id="534c8-146">提供一些方法，这些方法使宿主可以使用 CLR 内部的程序集标识数据来操作由文件或流引用的程序集集，而无需创建或了解这些标识。</span><span class="sxs-lookup"><span data-stu-id="534c8-146">Provides methods that enable the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the CLR, without needing to create or understand those identities.</span></span>  
  
 [<span data-ttu-id="534c8-147">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-147">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)  
 <span data-ttu-id="534c8-148">提供类似于[ICorRuntimeHost](icorruntimehost-interface.md)的功能，另外还提供了一个用于设置宿主控件接口的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-148">Provides capabilities similar to [ICorRuntimeHost](icorruntimehost-interface.md), with an additional method to set the host control interface.</span></span>  
  
 [<span data-ttu-id="534c8-149">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-149">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)  
 <span data-ttu-id="534c8-150">为宿主提供方法，以获取有关请求任务的信息，并在其同步实现中检测死锁。</span><span class="sxs-lookup"><span data-stu-id="534c8-150">Provides methods for the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
 [<span data-ttu-id="534c8-151">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-151">ICLRTask Interface</span></span>](iclrtask-interface.md)  
 <span data-ttu-id="534c8-152">提供一些方法，这些方法使宿主可以发出 CLR 请求，或向 CLR 提供有关关联任务的通知。</span><span class="sxs-lookup"><span data-stu-id="534c8-152">Provides methods that enable the host to make requests of the CLR, or to provide notification to the CLR about the associated task.</span></span>  
  
 [<span data-ttu-id="534c8-153">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-153">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)  
 <span data-ttu-id="534c8-154">提供使宿主能够显式请求 CLR 创建新任务、获取当前正在执行的任务以及设置任务的地理语言和区域性的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-154">Provides methods that enable the host to request explicitly that the CLR create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
 [<span data-ttu-id="534c8-155">ICLRValidator 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-155">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)  
 <span data-ttu-id="534c8-156">提供用于验证可移植可执行（PE）映像和报告验证错误的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-156">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
 [<span data-ttu-id="534c8-157">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-157">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)  
 <span data-ttu-id="534c8-158">提供配置 CLR 的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-158">Provides methods for configuring the CLR.</span></span>  
  
 [<span data-ttu-id="534c8-159">ICorThreadpool 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-159">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)  
 <span data-ttu-id="534c8-160">提供用于访问线程池的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-160">Provides methods for accessing the thread pool.</span></span>  
  
 [<span data-ttu-id="534c8-161">IDebuggerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-161">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)  
 <span data-ttu-id="534c8-162">提供用于获取有关调试服务状态的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-162">Provides methods for obtaining information about the state of the debugging services.</span></span>  
  
 [<span data-ttu-id="534c8-163">IDebuggerThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-163">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)  
 <span data-ttu-id="534c8-164">提供一些方法，用于通知宿主调试服务阻止和取消阻止线程。</span><span class="sxs-lookup"><span data-stu-id="534c8-164">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
 [<span data-ttu-id="534c8-165">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-165">IGCHost Interface</span></span>](igchost-interface.md)  
 <span data-ttu-id="534c8-166">提供一些方法，用于获取有关垃圾回收系统的信息并控制垃圾回收的某些方面。</span><span class="sxs-lookup"><span data-stu-id="534c8-166">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
 [<span data-ttu-id="534c8-167">IGCHost2 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-167">IGCHost2 Interface</span></span>](igchost2-interface.md)  
 <span data-ttu-id="534c8-168">提供[SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md)方法，该方法使宿主可以将垃圾回收段的大小和垃圾回收系统的代零的最大大小设置为大于的值 `DWORD` 。</span><span class="sxs-lookup"><span data-stu-id="534c8-168">Provides the [SetGCStartupLimitsEx](igchost2-setgcstartuplimitsex-method.md) method that enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation zero to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="534c8-169">IGCHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-169">IGCHostControl Interface</span></span>](igchostcontrol-interface.md)  
 <span data-ttu-id="534c8-170">提供一个方法，该方法使垃圾回收器能够请求宿主更改虚拟内存的限制。</span><span class="sxs-lookup"><span data-stu-id="534c8-170">Provides a method that enables the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
 [<span data-ttu-id="534c8-171">IGCThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-171">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)  
 <span data-ttu-id="534c8-172">提供一些方法，这些方法用于参与要阻止垃圾回收的线程的计划。</span><span class="sxs-lookup"><span data-stu-id="534c8-172">Provides methods for participating in the scheduling of threads that would otherwise be blocked for garbage collection.</span></span>  
  
 [<span data-ttu-id="534c8-173">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-173">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)  
 <span data-ttu-id="534c8-174">提供使宿主可以指定应由 CLR 或由主机加载的程序集的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-174">Provides methods that enable a host to specify sets of assemblies that should be loaded by the CLR or by the host.</span></span>  
  
 [<span data-ttu-id="534c8-175">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-175">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)  
 <span data-ttu-id="534c8-176">提供使宿主可以独立于 CLR 加载程序集和模块的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-176">Provides methods that enable a host to load assemblies and modules independently of the CLR.</span></span>  
  
 [<span data-ttu-id="534c8-177">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-177">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)  
 <span data-ttu-id="534c8-178">提供宿主实现的自动重置事件的表示形式。</span><span class="sxs-lookup"><span data-stu-id="534c8-178">Provides a representation of an auto-reset event implemented by the host.</span></span>  
  
 [<span data-ttu-id="534c8-179">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-179">IHostControl Interface</span></span>](ihostcontrol-interface.md)  
 <span data-ttu-id="534c8-180">提供用于配置程序集加载和确定宿主支持哪些宿主接口的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-180">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
 [<span data-ttu-id="534c8-181">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-181">IHostCrst Interface</span></span>](ihostcrst-interface.md)  
 <span data-ttu-id="534c8-182">用作线程的关键部分的宿主表示形式。</span><span class="sxs-lookup"><span data-stu-id="534c8-182">Serves as the host's representation of a critical section for threading.</span></span>  
  
 [<span data-ttu-id="534c8-183">IHostGCManager 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-183">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)  
 <span data-ttu-id="534c8-184">提供一些方法，这些方法可向宿主通知 CLR 实现的垃圾回收机制中的事件。</span><span class="sxs-lookup"><span data-stu-id="534c8-184">Provides methods that notify the host of events in the garbage collection mechanism implemented by the CLR.</span></span>  
  
 [<span data-ttu-id="534c8-185">IHostIoCompletionManager 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-185">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)  
 <span data-ttu-id="534c8-186">提供使 CLR 能够与主机提供的 i/o 完成端口进行交互的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-186">Provides methods that enable the CLR to interact with I/O completion ports provided by the host.</span></span>  
  
 [<span data-ttu-id="534c8-187">IHostMalloc 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-187">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)  
 <span data-ttu-id="534c8-188">为 CLR 提供一些方法，用于通过宿主请求从堆中进行细粒度分配。</span><span class="sxs-lookup"><span data-stu-id="534c8-188">Provides methods for the CLR to request fine-grained allocations from the heap through the host.</span></span>  
  
 [<span data-ttu-id="534c8-189">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-189">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)  
 <span data-ttu-id="534c8-190">提供宿主手动重置事件表示形式的实现。</span><span class="sxs-lookup"><span data-stu-id="534c8-190">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
 [<span data-ttu-id="534c8-191">IHostMemoryManager 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-191">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)  
 <span data-ttu-id="534c8-192">为 CLR 提供一些方法，用于通过主机进行虚拟内存请求，而不是使用标准 Win32 虚拟内存函数。</span><span class="sxs-lookup"><span data-stu-id="534c8-192">Provides methods for the CLR to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
 [<span data-ttu-id="534c8-193">IHostPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-193">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)  
 <span data-ttu-id="534c8-194">提供一些方法，这些方法在发生中止、超时或失败时通知 CLR 执行的操作。</span><span class="sxs-lookup"><span data-stu-id="534c8-194">Provides methods that notify the host of the actions the CLR performs in case of aborts, timeouts, or failures.</span></span>  
  
 [<span data-ttu-id="534c8-195">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-195">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)  
 <span data-ttu-id="534c8-196">使 CLR 能够维护宿主实现的安全上下文信息。</span><span class="sxs-lookup"><span data-stu-id="534c8-196">Enables the CLR to maintain security context information implemented by the host.</span></span>  
  
 [<span data-ttu-id="534c8-197">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-197">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)  
 <span data-ttu-id="534c8-198">提供允许访问和控制当前正在执行的线程的安全上下文的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-198">Provides methods that enable access to, and control over, the security context of the currently executing thread.</span></span>  
  
 [<span data-ttu-id="534c8-199">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-199">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)  
 <span data-ttu-id="534c8-200">提供由主机实现的信号量的表示形式。</span><span class="sxs-lookup"><span data-stu-id="534c8-200">Provides a representation of a semaphore implemented by the host.</span></span>  
  
 [<span data-ttu-id="534c8-201">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-201">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)  
 <span data-ttu-id="534c8-202">为 CLR 提供方法，以通过调用主机而不是使用 Win32 同步函数来创建同步基元。</span><span class="sxs-lookup"><span data-stu-id="534c8-202">Provides methods for the CLR to create synchronization primitives by calling the host, instead of using the Win32 synchronization functions.</span></span>  
  
 [<span data-ttu-id="534c8-203">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-203">IHostTask Interface</span></span>](ihosttask-interface.md)  
 <span data-ttu-id="534c8-204">提供使 CLR 能够与宿主通信以管理任务的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-204">Provides methods that enable the CLR to communicate with the host to manage tasks.</span></span>  
  
 [<span data-ttu-id="534c8-205">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-205">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)  
 <span data-ttu-id="534c8-206">提供一些方法，使 CLR 可以通过主机使用任务，而不是使用标准的操作系统线程或纤程函数。</span><span class="sxs-lookup"><span data-stu-id="534c8-206">Provides methods that enable the CLR to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
 [<span data-ttu-id="534c8-207">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-207">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)  
 <span data-ttu-id="534c8-208">为 CLR 提供方法来配置线程池并将工作项排队到线程池。</span><span class="sxs-lookup"><span data-stu-id="534c8-208">Provides methods for the CLR to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
 [<span data-ttu-id="534c8-209">IManagedObject 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-209">IManagedObject Interface</span></span>](imanagedobject-interface.md)  
 <span data-ttu-id="534c8-210">提供用于控制托管对象的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-210">Provides methods for controlling a managed object.</span></span>  
  
 <span data-ttu-id="534c8-211">IObjectHandle</span><span class="sxs-lookup"><span data-stu-id="534c8-211">"IObjectHandle"</span></span>  
 <span data-ttu-id="534c8-212">提供了一种方法，用于从间接寻址解包按值封送对象。</span><span class="sxs-lookup"><span data-stu-id="534c8-212">Provides a method for unwrapping marshal-by-value objects from indirection.</span></span>  
  
 [<span data-ttu-id="534c8-213">ITypeName 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-213">ITypeName Interface</span></span>](itypename-interface.md)  
 <span data-ttu-id="534c8-214">提供用于获取类型名称信息的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-214">Provides methods for obtaining type name information.</span></span> <span data-ttu-id="534c8-215">（此接口支持 .NET Framework 基础结构，不应在代码中直接使用。）</span><span class="sxs-lookup"><span data-stu-id="534c8-215">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="534c8-216">ITypeNameBuilder 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-216">ITypeNameBuilder Interface</span></span>](itypenamebuilder-interface.md)  
 <span data-ttu-id="534c8-217">提供用于生成类型名称的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-217">Provides methods for building a type name.</span></span> <span data-ttu-id="534c8-218">（此接口支持 .NET Framework 基础结构，不应在代码中直接使用。）</span><span class="sxs-lookup"><span data-stu-id="534c8-218">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="534c8-219">ITypeNameFactory 接口</span><span class="sxs-lookup"><span data-stu-id="534c8-219">ITypeNameFactory Interface</span></span>](itypenamefactory-interface.md)  
 <span data-ttu-id="534c8-220">提供用于析构类型名称的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-220">Provides methods for deconstructing a type name.</span></span> <span data-ttu-id="534c8-221">（此接口支持 .NET Framework 基础结构，不应在代码中直接使用。）</span><span class="sxs-lookup"><span data-stu-id="534c8-221">(This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 <span data-ttu-id="534c8-222">IValidator</span><span class="sxs-lookup"><span data-stu-id="534c8-222">"IValidator"</span></span>  
 <span data-ttu-id="534c8-223">提供用于验证可移植可执行（PE）映像和报告验证错误的方法。</span><span class="sxs-lookup"><span data-stu-id="534c8-223">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="534c8-224">相关章节</span><span class="sxs-lookup"><span data-stu-id="534c8-224">Related Sections</span></span>  
 [<span data-ttu-id="534c8-225">弃用的 CLR 承载接口和 Coclass</span><span class="sxs-lookup"><span data-stu-id="534c8-225">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="534c8-226">包含描述 .NET Framework 版本1.0 和1.1 中提供的托管接口的主题。</span><span class="sxs-lookup"><span data-stu-id="534c8-226">Contains topics that describe the hosting interfaces provided in the .NET Framework version 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="534c8-227">.NET Framework 4 和 4.5 中添加的 CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="534c8-227">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="534c8-228">包含描述 .NET Framework 4 中提供的宿主接口的主题。</span><span class="sxs-lookup"><span data-stu-id="534c8-228">Contains topics that describe the hosting interfaces provided in the .NET Framework 4.</span></span>
