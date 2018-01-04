---
title: "CorBindToRuntimeEx 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorBindToRuntimeEx
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: CorBindToRuntimeEx
helpviewer_keywords: CorBindToRuntimeEx function [.NET Framework hosting]
ms.assetid: aae9fb17-5d01-41da-9773-1b5b5b642d81
topic_type: apiref
caps.latest.revision: "41"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c0080e5a01c8e856c2862182ba06096fdc9385c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corbindtoruntimeex-function"></a><span data-ttu-id="e55a7-102">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="e55a7-102">CorBindToRuntimeEx Function</span></span>
<span data-ttu-id="e55a7-103">使非托管的宿主能够将公共语言运行时 (CLR) 加载到过程中。</span><span class="sxs-lookup"><span data-stu-id="e55a7-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span> <span data-ttu-id="e55a7-104">[CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)和`CorBindToRuntimeEx`函数执行相同的操作，但`CorBindToRuntimeEx`函数使你可以设置标志以指定的 CLR 的行为。</span><span class="sxs-lookup"><span data-stu-id="e55a7-104">The [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) and `CorBindToRuntimeEx` functions perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 <span data-ttu-id="e55a7-105">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e55a7-105">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
 <span data-ttu-id="e55a7-106">此函数采用一组允许的主机来执行以下参数：</span><span class="sxs-lookup"><span data-stu-id="e55a7-106">This function takes a set of parameters that allow a host to do the following:</span></span>  
  
-   <span data-ttu-id="e55a7-107">指定将加载的运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="e55a7-107">Specify the version of the runtime that will be loaded.</span></span>  
  
-   <span data-ttu-id="e55a7-108">指示是否应加载服务器或工作站生成。</span><span class="sxs-lookup"><span data-stu-id="e55a7-108">Indicate whether the server or workstation build should be loaded.</span></span>  
  
-   <span data-ttu-id="e55a7-109">控制是否并发垃圾回收或非并发垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="e55a7-109">Control whether concurrent garbage collection or non-concurrent garbage collection is done.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e55a7-110">运行 WOW64 应用程序中不支持并发垃圾回收 x86 仿真程序上实现 （以前称为 ia-64） 的 Intel 的 Itanium 体系结构的 64 位系统。</span><span class="sxs-lookup"><span data-stu-id="e55a7-110">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="e55a7-111">有关使用 64 位 Windows 系统上的 WOW64 的详细信息，请参阅[运行 32 位应用程序](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e55a7-111">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx).</span></span>  
  
-   <span data-ttu-id="e55a7-112">控制是否非特定域方式加载程序集。</span><span class="sxs-lookup"><span data-stu-id="e55a7-112">Control whether assemblies are loaded as domain-neutral.</span></span>  
  
-   <span data-ttu-id="e55a7-113">获取到的接口指针[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)可用来设置配置的 CLR 实例之前启动的其他选项。</span><span class="sxs-lookup"><span data-stu-id="e55a7-113">Obtain an interface pointer to an [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) that can be used to set additional options for configuring an instance of the CLR before it is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e55a7-114">语法</span><span class="sxs-lookup"><span data-stu-id="e55a7-114">Syntax</span></span>  
  
```  
HRESULT CorBindToRuntimeEx (  
    [in]  LPCWSTR      pwszVersion,   
    [in]  LPCWSTR      pwszBuildFlavor,   
    [in]  DWORD        startupFlags,   
    [in]  REFCLSID     rclsid,   
    [in]  REFIID       riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e55a7-115">参数</span><span class="sxs-lookup"><span data-stu-id="e55a7-115">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="e55a7-116">[in]你想要加载描述的 CLR 版本的字符串。</span><span class="sxs-lookup"><span data-stu-id="e55a7-116">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="e55a7-117">.NET Framework 中的版本号用句点分隔的四个部分组成： *major.minor.build.revision*。</span><span class="sxs-lookup"><span data-stu-id="e55a7-117">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="e55a7-118">将字符串作为传递`pwszVersion`必须以字符"v"跟版本号 (例如，"v1.0.1529") 的前三个部分开头。</span><span class="sxs-lookup"><span data-stu-id="e55a7-118">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="e55a7-119">某些版本的 CLR 与指定与以前版本的 CLR 的兼容性的策略语句一起安装。</span><span class="sxs-lookup"><span data-stu-id="e55a7-119">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="e55a7-120">默认情况下，启动填充码将评估`pwszVersion`针对策略语句和加载运行时的最新版本的适用于所请求的版本。</span><span class="sxs-lookup"><span data-stu-id="e55a7-120">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="e55a7-121">主机可以强制填充码可跳过策略评估，负载中指定的确切版本`pwszVersion`通过将的值传递`STARTUP_LOADER_SAFEMODE`为`startupFlags`参数，如下所述。</span><span class="sxs-lookup"><span data-stu-id="e55a7-121">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `startupFlags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="e55a7-122">如果调用方指定为 null `pwszVersion`，`CorBindToRuntimeEx`标识的一套安装运行时，其版本号低于.NET Framework 4 运行时，并从该组中加载的运行时的最新版本。</span><span class="sxs-lookup"><span data-stu-id="e55a7-122">If the caller specifies null for `pwszVersion`, `CorBindToRuntimeEx` identifies the set of installed runtimes whose version numbers are lower than the .NET Framework 4 runtime, and loads the latest version of the runtime from that set.</span></span> <span data-ttu-id="e55a7-123">如果不安装任何早期版本，它不会加载.NET Framework 4 或更高版本，并且将失败。</span><span class="sxs-lookup"><span data-stu-id="e55a7-123">It won't load the .NET Framework 4 or later, and fails if no earlier version is installed.</span></span> <span data-ttu-id="e55a7-124">请注意，传递 null，则主机加载的运行时版本的任何控件。</span><span class="sxs-lookup"><span data-stu-id="e55a7-124">Note that passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="e55a7-125">虽然这种方法可能在某些情况下适用，但强烈建议主机提供一个要加载的特定版本。</span><span class="sxs-lookup"><span data-stu-id="e55a7-125">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="e55a7-126">[in]一个字符串，指定是否以加载服务器或工作站生成的 CLR。</span><span class="sxs-lookup"><span data-stu-id="e55a7-126">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="e55a7-127">有效值为 `svr` 和 `wks`。</span><span class="sxs-lookup"><span data-stu-id="e55a7-127">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="e55a7-128">服务器版本进行了优化以利用多个处理器进行垃圾回收和工作站生成优化的单处理器计算机上运行的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="e55a7-128">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="e55a7-129">如果`pwszBuildFlavor`设置为 null，则将加载工作站版本。</span><span class="sxs-lookup"><span data-stu-id="e55a7-129">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="e55a7-130">单处理器计算机上运行时，工作站生成始终处于加载状态，即使`pwszBuildFlavor`设置为`svr`。</span><span class="sxs-lookup"><span data-stu-id="e55a7-130">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="e55a7-131">但是，如果`pwszBuildFlavor`设置为`svr`和指定并发垃圾回收 (请参阅的说明`startupFlags`参数)，则服务器将加载版本。</span><span class="sxs-lookup"><span data-stu-id="e55a7-131">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="e55a7-132">[in]值的组合[STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="e55a7-132">[in] A combination of values of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration.</span></span> <span data-ttu-id="e55a7-133">这些标志控制并发垃圾回收、 非特定于域的代码和行为的`pwszVersion`参数。</span><span class="sxs-lookup"><span data-stu-id="e55a7-133">These flags control concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="e55a7-134">如果未设置标志，则默认值是单一域。</span><span class="sxs-lookup"><span data-stu-id="e55a7-134">The default is single domain if no flag is set.</span></span> <span data-ttu-id="e55a7-135">以下为有效值：</span><span class="sxs-lookup"><span data-stu-id="e55a7-135">The following values are valid:</span></span>  
  
-   `STARTUP_CONCURRENT_GC`  
  
-   `STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`  
  
-   `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`  
  
-   `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`  
  
-   `STARTUP_LOADER_SAFEMODE`  
  
-   `STARTUP_LEGACY_IMPERSONATION`  
  
-   `STARTUP_LOADER_SETPREFERENCE`  
  
-   `STARTUP_SERVER_GC`  
  
-   `STARTUP_HOARD_GC_VM`  
  
-   `STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`  
  
-   `STARTUP_LEGACY_IMPERSONATION`  
  
-   `STARTUP_DISABLE_COMMITTHREADSTACK`  
  
-   `STARTUP_ALWAYSFLOW_IMPERSONATION`  
  
 <span data-ttu-id="e55a7-136">有关这些标志的说明，请参阅[STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="e55a7-136">For descriptions of these flags, see the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="e55a7-137">[in]`CLSID`实现的组件类的[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="e55a7-137">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="e55a7-138">支持的值为 CLSID_CorRuntimeHost 或 CLSID_CLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="e55a7-138">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="e55a7-139">[in]`IID`从所请求的接口的`rclsid`。</span><span class="sxs-lookup"><span data-stu-id="e55a7-139">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="e55a7-140">支持的值为 IID_ICorRuntimeHost 或 IID_ICLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="e55a7-140">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="e55a7-141">[out]指向返回的接口指针`riid`。</span><span class="sxs-lookup"><span data-stu-id="e55a7-141">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e55a7-142">备注</span><span class="sxs-lookup"><span data-stu-id="e55a7-142">Remarks</span></span>  
 <span data-ttu-id="e55a7-143">如果`pwszVersion`指定不存在，运行时版本`CorBindToRuntimeEx`返回 CLR_E_SHIM_RUNTIMELOAD HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="e55a7-143">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="e55a7-144">执行上下文和的 Windows 标识的流</span><span class="sxs-lookup"><span data-stu-id="e55a7-144">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="e55a7-145">中的 clr 版本 1<xref:System.Security.Principal.WindowsIdentity>对象不流过异步点，例如新线程，线程池或计时器回调。</span><span class="sxs-lookup"><span data-stu-id="e55a7-145">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="e55a7-146">在 2.0 版中的 CLR，<xref:System.Threading.ExecutionContext>对象包装有关当前正在执行的线程的一些信息，并且流动它跨任何异步的点，但是不能跨应用程序域边界。</span><span class="sxs-lookup"><span data-stu-id="e55a7-146">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="e55a7-147">同样，<xref:System.Security.Principal.WindowsIdentity>对象也会流过任何异步的点。</span><span class="sxs-lookup"><span data-stu-id="e55a7-147">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="e55a7-148">因此，当前线程上的模拟如果有的话，也会流动。</span><span class="sxs-lookup"><span data-stu-id="e55a7-148">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="e55a7-149">您可以改变两种方式流：</span><span class="sxs-lookup"><span data-stu-id="e55a7-149">You can alter the flow in two ways:</span></span>  
  
1.  <span data-ttu-id="e55a7-150">通过修改<xref:System.Threading.ExecutionContext>设置以禁止显示的每个线程基础上的流 (请参阅<xref:System.Threading.ExecutionContext.SuppressFlow%2A>， <xref:System.Security.SecurityContext.SuppressFlow%2A>，和<xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A>方法)。</span><span class="sxs-lookup"><span data-stu-id="e55a7-150">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2.  <span data-ttu-id="e55a7-151">通过更改进程的默认模式为版本 1 兼容性模式，其中<xref:System.Security.Principal.WindowsIdentity>对象不流经任何异步的点，而不考虑<xref:System.Threading.ExecutionContext>当前线程上的设置。</span><span class="sxs-lookup"><span data-stu-id="e55a7-151">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="e55a7-152">如何更改默认模式取决于是否使用托管的可执行文件或使用非托管承载接口来加载 CLR:</span><span class="sxs-lookup"><span data-stu-id="e55a7-152">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1.  <span data-ttu-id="e55a7-153">用于托管可执行文件，必须设置`enabled`属性[ \<legacyImpersonationPolicy >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)元素`true`。</span><span class="sxs-lookup"><span data-stu-id="e55a7-153">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2.  <span data-ttu-id="e55a7-154">对于非托管承载接口、 将`STARTUP_LEGACY_IMPERSONATION`中标记出来`startupFlags`参数调用时`CorBindToRuntimeEx`函数。</span><span class="sxs-lookup"><span data-stu-id="e55a7-154">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `startupFlags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="e55a7-155">版本 1 兼容模式适用于进程中的所有应用程序域和的整个过程。</span><span class="sxs-lookup"><span data-stu-id="e55a7-155">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e55a7-156">惠?</span><span class="sxs-lookup"><span data-stu-id="e55a7-156">Requirements</span></span>  
 <span data-ttu-id="e55a7-157">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e55a7-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e55a7-158">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e55a7-158">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e55a7-159">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e55a7-159">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e55a7-160">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e55a7-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e55a7-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="e55a7-161">See Also</span></span>  
 [<span data-ttu-id="e55a7-162">CorBindToCurrentRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="e55a7-162">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [<span data-ttu-id="e55a7-163">CorBindToRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="e55a7-163">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [<span data-ttu-id="e55a7-164">CorBindToRuntimeByCfg 函数</span><span class="sxs-lookup"><span data-stu-id="e55a7-164">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [<span data-ttu-id="e55a7-165">CorBindToRuntimeHost 函数</span><span class="sxs-lookup"><span data-stu-id="e55a7-165">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [<span data-ttu-id="e55a7-166">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="e55a7-166">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="e55a7-167">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="e55a7-167">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
