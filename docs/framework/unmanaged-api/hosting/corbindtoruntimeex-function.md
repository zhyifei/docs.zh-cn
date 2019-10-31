---
title: CorBindToRuntimeEx 函数
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeEx
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeEx
helpviewer_keywords:
- CorBindToRuntimeEx function [.NET Framework hosting]
ms.assetid: aae9fb17-5d01-41da-9773-1b5b5b642d81
topic_type:
- apiref
ms.openlocfilehash: 794a39f1e2c4a93a34ae39641519c79fd4c4e79e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131231"
---
# <a name="corbindtoruntimeex-function"></a><span data-ttu-id="f60ee-102">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="f60ee-102">CorBindToRuntimeEx Function</span></span>
<span data-ttu-id="f60ee-103">使非托管宿主能够将公共语言运行时（CLR）加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="f60ee-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span> <span data-ttu-id="f60ee-104">[CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)和 `CorBindToRuntimeEx` 函数执行相同的操作，但 `CorBindToRuntimeEx` 函数允许您设置标志来指定 CLR 的行为。</span><span class="sxs-lookup"><span data-stu-id="f60ee-104">The [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) and `CorBindToRuntimeEx` functions perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 <span data-ttu-id="f60ee-105">此函数已在 .NET Framework 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="f60ee-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="f60ee-106">此函数使用一组参数，这些参数允许主机执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f60ee-106">This function takes a set of parameters that allow a host to do the following:</span></span>  
  
- <span data-ttu-id="f60ee-107">指定要加载的运行时版本。</span><span class="sxs-lookup"><span data-stu-id="f60ee-107">Specify the version of the runtime that will be loaded.</span></span>  
  
- <span data-ttu-id="f60ee-108">指示是否应加载服务器或工作站生成。</span><span class="sxs-lookup"><span data-stu-id="f60ee-108">Indicate whether the server or workstation build should be loaded.</span></span>  
  
- <span data-ttu-id="f60ee-109">控制并发垃圾回收或非并发垃圾回收是否已完成。</span><span class="sxs-lookup"><span data-stu-id="f60ee-109">Control whether concurrent garbage collection or non-concurrent garbage collection is done.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f60ee-110">在实现 Intel Itanium 体系结构（以前称为 IA-64）的64位系统上运行 WOW64 x86 模拟器的应用程序中不支持并发垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="f60ee-110">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="f60ee-111">有关在64位 Windows 系统上使用 WOW64 的详细信息，请参阅[运行32位应用程序](/windows/desktop/WinProg64/running-32-bit-applications)。</span><span class="sxs-lookup"><span data-stu-id="f60ee-111">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
- <span data-ttu-id="f60ee-112">控制是否以非特定于域的形式加载程序集。</span><span class="sxs-lookup"><span data-stu-id="f60ee-112">Control whether assemblies are loaded as domain-neutral.</span></span>  
  
- <span data-ttu-id="f60ee-113">获取一个指向[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)的接口指针，该指针可用于设置附加选项，以便在启动 CLR 实例之前对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="f60ee-113">Obtain an interface pointer to an [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) that can be used to set additional options for configuring an instance of the CLR before it is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f60ee-114">语法</span><span class="sxs-lookup"><span data-stu-id="f60ee-114">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeEx (  
    [in]  LPCWSTR      pwszVersion,   
    [in]  LPCWSTR      pwszBuildFlavor,   
    [in]  DWORD        startupFlags,   
    [in]  REFCLSID     rclsid,   
    [in]  REFIID       riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f60ee-115">参数</span><span class="sxs-lookup"><span data-stu-id="f60ee-115">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="f60ee-116">中一个字符串，描述要加载的 CLR 的版本。</span><span class="sxs-lookup"><span data-stu-id="f60ee-116">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="f60ee-117">.NET Framework 中的版本号由以句点分隔的四个部分组成：*主*版本. 次要版本. 内部版本号. 修订号。</span><span class="sxs-lookup"><span data-stu-id="f60ee-117">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="f60ee-118">作为 `pwszVersion` 传递的字符串必须以字符 "v" 开头，后跟版本号的前三个部分（例如，"1.0.1529"）。</span><span class="sxs-lookup"><span data-stu-id="f60ee-118">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="f60ee-119">某些版本的 CLR 随策略声明一起安装，后者指定与以前版本的 CLR 的兼容性。</span><span class="sxs-lookup"><span data-stu-id="f60ee-119">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="f60ee-120">默认情况下，启动填充程序根据策略语句计算 `pwszVersion`，并加载与请求的版本兼容的运行时的最新版本。</span><span class="sxs-lookup"><span data-stu-id="f60ee-120">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="f60ee-121">主机可以通过为 `startupFlags` 参数传递值 `STARTUP_LOADER_SAFEMODE` 来强制填充程序跳过策略评估并加载 `pwszVersion` 中指定的确切版本，如下所述。</span><span class="sxs-lookup"><span data-stu-id="f60ee-121">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `startupFlags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="f60ee-122">如果调用方为 `pwszVersion`指定 null，则 `CorBindToRuntimeEx` 会标识已安装的运行时集，其版本号低于 .NET Framework 4 运行时，并从该集中加载最新版本的运行时。</span><span class="sxs-lookup"><span data-stu-id="f60ee-122">If the caller specifies null for `pwszVersion`, `CorBindToRuntimeEx` identifies the set of installed runtimes whose version numbers are lower than the .NET Framework 4 runtime, and loads the latest version of the runtime from that set.</span></span> <span data-ttu-id="f60ee-123">它不会加载 .NET Framework 4 或更高版本，如果未安装任何早期版本，则会失败。</span><span class="sxs-lookup"><span data-stu-id="f60ee-123">It won't load the .NET Framework 4 or later, and fails if no earlier version is installed.</span></span> <span data-ttu-id="f60ee-124">请注意，传递 null 会使宿主无法控制加载的运行时版本。</span><span class="sxs-lookup"><span data-stu-id="f60ee-124">Note that passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="f60ee-125">虽然这种方法可能适用于某些情况，但强烈建议主机提供要加载的特定版本。</span><span class="sxs-lookup"><span data-stu-id="f60ee-125">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="f60ee-126">中一个字符串，指定是加载 CLR 的服务器还是工作站版本。</span><span class="sxs-lookup"><span data-stu-id="f60ee-126">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="f60ee-127">有效值为 `svr` 和 `wks`。</span><span class="sxs-lookup"><span data-stu-id="f60ee-127">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="f60ee-128">服务器版本经过优化，可利用多个处理器进行垃圾回收，工作站构建针对单处理器计算机上运行的客户端应用程序进行了优化。</span><span class="sxs-lookup"><span data-stu-id="f60ee-128">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="f60ee-129">如果 `pwszBuildFlavor` 设置为 null，则会加载工作站构建。</span><span class="sxs-lookup"><span data-stu-id="f60ee-129">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="f60ee-130">在单处理器计算机上运行时，始终会加载工作站构建，即使 `pwszBuildFlavor` 设置为 `svr`。</span><span class="sxs-lookup"><span data-stu-id="f60ee-130">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="f60ee-131">但是，如果 `pwszBuildFlavor` 设置为 `svr` 并指定了并发垃圾回收（请参阅 `startupFlags` 参数的说明），则将加载服务器生成。</span><span class="sxs-lookup"><span data-stu-id="f60ee-131">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="f60ee-132">中[STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)枚举值的组合。</span><span class="sxs-lookup"><span data-stu-id="f60ee-132">[in] A combination of values of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration.</span></span> <span data-ttu-id="f60ee-133">这些标志控制并发垃圾回收、非特定于域的代码和 `pwszVersion` 参数的行为。</span><span class="sxs-lookup"><span data-stu-id="f60ee-133">These flags control concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="f60ee-134">如果未设置任何标志，则默认值为单一域。</span><span class="sxs-lookup"><span data-stu-id="f60ee-134">The default is single domain if no flag is set.</span></span> <span data-ttu-id="f60ee-135">以下为有效值：</span><span class="sxs-lookup"><span data-stu-id="f60ee-135">The following values are valid:</span></span>  
  
- `STARTUP_CONCURRENT_GC`  
  
- `STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`  
  
- `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`  
  
- `STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`  
  
- `STARTUP_LOADER_SAFEMODE`  
  
- `STARTUP_LEGACY_IMPERSONATION`  
  
- `STARTUP_LOADER_SETPREFERENCE`  
  
- `STARTUP_SERVER_GC`  
  
- `STARTUP_HOARD_GC_VM`  
  
- `STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`  
  
- `STARTUP_LEGACY_IMPERSONATION`  
  
- `STARTUP_DISABLE_COMMITTHREADSTACK`  
  
- `STARTUP_ALWAYSFLOW_IMPERSONATION`  
  
 <span data-ttu-id="f60ee-136">有关这些标志的说明，请参阅[STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="f60ee-136">For descriptions of these flags, see the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="f60ee-137">中用于实现[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口的 coclass 的 `CLSID`。</span><span class="sxs-lookup"><span data-stu-id="f60ee-137">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="f60ee-138">支持的值为 CLSID_CorRuntimeHost 或 CLSID_CLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="f60ee-138">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="f60ee-139">中从 `rclsid`请求的接口的 `IID`。</span><span class="sxs-lookup"><span data-stu-id="f60ee-139">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="f60ee-140">支持的值为 IID_ICorRuntimeHost 或 IID_ICLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="f60ee-140">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="f60ee-141">弄返回 `riid`的接口指针。</span><span class="sxs-lookup"><span data-stu-id="f60ee-141">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f60ee-142">备注</span><span class="sxs-lookup"><span data-stu-id="f60ee-142">Remarks</span></span>  
 <span data-ttu-id="f60ee-143">如果 `pwszVersion` 指定不存在的运行时版本，则 `CorBindToRuntimeEx` 返回 HRESULT 值 CLR_E_SHIM_RUNTIMELOAD。</span><span class="sxs-lookup"><span data-stu-id="f60ee-143">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="f60ee-144">执行上下文和 Windows 标识流</span><span class="sxs-lookup"><span data-stu-id="f60ee-144">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="f60ee-145">在 CLR 版本1中，<xref:System.Security.Principal.WindowsIdentity> 对象不流经异步点，如新线程、线程池或计时器回调。</span><span class="sxs-lookup"><span data-stu-id="f60ee-145">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="f60ee-146">在 CLR 版本2.0 中，<xref:System.Threading.ExecutionContext> 对象包装了有关当前正在执行的线程的一些信息，并在所有异步点（而不是跨应用程序域边界）传递它。</span><span class="sxs-lookup"><span data-stu-id="f60ee-146">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="f60ee-147">同样，<xref:System.Security.Principal.WindowsIdentity> 对象还会流经任何异步点。</span><span class="sxs-lookup"><span data-stu-id="f60ee-147">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="f60ee-148">因此，线程上的当前模拟（如果有）也会流动。</span><span class="sxs-lookup"><span data-stu-id="f60ee-148">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="f60ee-149">可以通过两种方式更改流：</span><span class="sxs-lookup"><span data-stu-id="f60ee-149">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="f60ee-150">通过修改 <xref:System.Threading.ExecutionContext> 设置以按线程抑制流（请参阅 <xref:System.Threading.ExecutionContext.SuppressFlow%2A>、<xref:System.Security.SecurityContext.SuppressFlow%2A>和 <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> 方法）。</span><span class="sxs-lookup"><span data-stu-id="f60ee-150">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="f60ee-151">将进程默认模式更改为版本1兼容模式，其中 <xref:System.Security.Principal.WindowsIdentity> 对象不在任何异步点上流动，无论当前线程上的 <xref:System.Threading.ExecutionContext> 设置如何。</span><span class="sxs-lookup"><span data-stu-id="f60ee-151">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="f60ee-152">更改默认模式的方式取决于您使用的是托管可执行文件还是非托管承载接口来加载 CLR：</span><span class="sxs-lookup"><span data-stu-id="f60ee-152">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1. <span data-ttu-id="f60ee-153">对于托管的可执行文件，必须将[\<legacyImpersonationPolicy >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)元素的 `enabled` 属性设置为 "`true`"。</span><span class="sxs-lookup"><span data-stu-id="f60ee-153">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2. <span data-ttu-id="f60ee-154">对于非托管承载接口，请在调用 `CorBindToRuntimeEx` 函数时设置 `startupFlags` 参数中的 `STARTUP_LEGACY_IMPERSONATION` 标志。</span><span class="sxs-lookup"><span data-stu-id="f60ee-154">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `startupFlags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="f60ee-155">版本1兼容性模式适用于整个进程和进程中的所有应用程序域。</span><span class="sxs-lookup"><span data-stu-id="f60ee-155">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f60ee-156">要求</span><span class="sxs-lookup"><span data-stu-id="f60ee-156">Requirements</span></span>  
 <span data-ttu-id="f60ee-157">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f60ee-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f60ee-158">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f60ee-158">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f60ee-159">**库：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f60ee-159">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f60ee-160">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f60ee-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f60ee-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="f60ee-161">See also</span></span>

- [<span data-ttu-id="f60ee-162">CorBindToCurrentRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="f60ee-162">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="f60ee-163">CorBindToRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="f60ee-163">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="f60ee-164">CorBindToRuntimeByCfg 函数</span><span class="sxs-lookup"><span data-stu-id="f60ee-164">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="f60ee-165">CorBindToRuntimeHost 函数</span><span class="sxs-lookup"><span data-stu-id="f60ee-165">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="f60ee-166">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="f60ee-166">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="f60ee-167">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="f60ee-167">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
