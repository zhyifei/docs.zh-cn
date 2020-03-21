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
ms.openlocfilehash: 3520af5f55f43183920dce7fbd24b70359c023a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176495"
---
# <a name="corbindtoruntimeex-function"></a><span data-ttu-id="55121-102">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="55121-102">CorBindToRuntimeEx Function</span></span>
<span data-ttu-id="55121-103">使非托管主机能够将通用语言运行时 （CLR） 加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="55121-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span> <span data-ttu-id="55121-104">[CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)和`CorBindToRuntimeEx`函数执行相同的操作，`CorBindToRuntimeEx`但该函数允许您设置标志以指定 CLR 的行为。</span><span class="sxs-lookup"><span data-stu-id="55121-104">The [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) and `CorBindToRuntimeEx` functions perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 <span data-ttu-id="55121-105">此功能已在 .NET 框架 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="55121-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="55121-106">此函数采用一组允许主机执行以下操作的参数：</span><span class="sxs-lookup"><span data-stu-id="55121-106">This function takes a set of parameters that allow a host to do the following:</span></span>  
  
- <span data-ttu-id="55121-107">指定将加载的运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="55121-107">Specify the version of the runtime that will be loaded.</span></span>  
  
- <span data-ttu-id="55121-108">指示是否应加载服务器或工作站生成。</span><span class="sxs-lookup"><span data-stu-id="55121-108">Indicate whether the server or workstation build should be loaded.</span></span>  
  
- <span data-ttu-id="55121-109">控制是否完成了并发垃圾回收或非并发垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="55121-109">Control whether concurrent garbage collection or non-concurrent garbage collection is done.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55121-110">在 64 位系统上运行 WOW64 x86 仿真器的应用程序不支持并发垃圾回收，这些系统实现了英特尔 Itanium 架构（以前称为 IA-64）。</span><span class="sxs-lookup"><span data-stu-id="55121-110">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="55121-111">有关在 64 位 Windows 系统上使用 WOW64 的详细信息，请参阅[运行 32 位应用程序](/windows/desktop/WinProg64/running-32-bit-applications)。</span><span class="sxs-lookup"><span data-stu-id="55121-111">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
- <span data-ttu-id="55121-112">控制程序集是否加载为域中立。</span><span class="sxs-lookup"><span data-stu-id="55121-112">Control whether assemblies are loaded as domain-neutral.</span></span>  
  
- <span data-ttu-id="55121-113">获取指向[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)的接口指针，该指针可用于在 CLR 启动之前设置用于配置 CLR 实例的其他选项。</span><span class="sxs-lookup"><span data-stu-id="55121-113">Obtain an interface pointer to an [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) that can be used to set additional options for configuring an instance of the CLR before it is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55121-114">语法</span><span class="sxs-lookup"><span data-stu-id="55121-114">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="55121-115">parameters</span><span class="sxs-lookup"><span data-stu-id="55121-115">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="55121-116">[在]描述要加载的 CLR 版本的字符串。</span><span class="sxs-lookup"><span data-stu-id="55121-116">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="55121-117">.NET 框架中的版本号由四个部分组成，由句点分隔：*主要.minor.build.revision*.</span><span class="sxs-lookup"><span data-stu-id="55121-117">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="55121-118">传递的`pwszVersion`字符串必须以字符"v"开头，后跟版本号的前三个部分（例如，"v1.0.1529"）。</span><span class="sxs-lookup"><span data-stu-id="55121-118">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="55121-119">CLR 的某些版本都安装了策略语句，该语句指定与 CLR 的早期版本的兼容性。</span><span class="sxs-lookup"><span data-stu-id="55121-119">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="55121-120">默认情况下，启动希姆`pwszVersion`根据策略语句进行评估，并加载与所请求版本兼容的最新版本的运行时。</span><span class="sxs-lookup"><span data-stu-id="55121-120">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="55121-121">主机可以强制 him 跳过策略评估，并通过传递`pwszVersion``STARTUP_LOADER_SAFEMODE``startupFlags`参数的值来加载指定的确切版本，如下所述。</span><span class="sxs-lookup"><span data-stu-id="55121-121">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `startupFlags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="55121-122">如果调用方为`pwszVersion`指定`CorBindToRuntimeEx`null，则标识其版本号低于 .NET Framework 4 运行时的已安装运行时集，并从该集加载最新版本的运行时。</span><span class="sxs-lookup"><span data-stu-id="55121-122">If the caller specifies null for `pwszVersion`, `CorBindToRuntimeEx` identifies the set of installed runtimes whose version numbers are lower than the .NET Framework 4 runtime, and loads the latest version of the runtime from that set.</span></span> <span data-ttu-id="55121-123">它不会加载 .NET 框架 4 或更高版本，如果没有安装早期版本，它将失败。</span><span class="sxs-lookup"><span data-stu-id="55121-123">It won't load the .NET Framework 4 or later, and fails if no earlier version is installed.</span></span> <span data-ttu-id="55121-124">请注意，传递 null 使主机无法控制加载的哪个版本的运行时。</span><span class="sxs-lookup"><span data-stu-id="55121-124">Note that passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="55121-125">尽管此方法在某些情况下可能适用，但强烈建议主机提供要加载的特定版本。</span><span class="sxs-lookup"><span data-stu-id="55121-125">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="55121-126">[在]指定是加载 CLR 的服务器还是工作站构建的字符串。</span><span class="sxs-lookup"><span data-stu-id="55121-126">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="55121-127">有效值为 `svr` 和 `wks`。</span><span class="sxs-lookup"><span data-stu-id="55121-127">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="55121-128">服务器生成经过优化，以利用多个处理器进行垃圾回收，工作站生成针对在单处理器计算机上运行的客户端应用程序进行了优化。</span><span class="sxs-lookup"><span data-stu-id="55121-128">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="55121-129">如果`pwszBuildFlavor`设置为 null，则加载工作站生成。</span><span class="sxs-lookup"><span data-stu-id="55121-129">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="55121-130">在单处理器计算机上运行时，工作站生成始终加载，即使`pwszBuildFlavor`设置为`svr`。</span><span class="sxs-lookup"><span data-stu-id="55121-130">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="55121-131">但是，如果`pwszBuildFlavor`设置为`svr`并指定了并发垃圾回收（请参阅`startupFlags`参数的说明），则加载服务器生成。</span><span class="sxs-lookup"><span data-stu-id="55121-131">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="55121-132">[在][STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)枚举的值的组合。</span><span class="sxs-lookup"><span data-stu-id="55121-132">[in] A combination of values of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration.</span></span> <span data-ttu-id="55121-133">这些标志控制并发垃圾回收、域中立代码和`pwszVersion`参数的行为。</span><span class="sxs-lookup"><span data-stu-id="55121-133">These flags control concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="55121-134">如果未设置标志，则默认值为单个域。</span><span class="sxs-lookup"><span data-stu-id="55121-134">The default is single domain if no flag is set.</span></span> <span data-ttu-id="55121-135">以下为有效值：</span><span class="sxs-lookup"><span data-stu-id="55121-135">The following values are valid:</span></span>  
  
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
  
 <span data-ttu-id="55121-136">有关这些标志的说明，请参阅[STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="55121-136">For descriptions of these flags, see the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="55121-137">[在]`CLSID`实现[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口的共类。</span><span class="sxs-lookup"><span data-stu-id="55121-137">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="55121-138">支持的值CLSID_CorRuntimeHost或CLSID_CLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="55121-138">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="55121-139">[在]从`IID`的请求接口的`rclsid`的</span><span class="sxs-lookup"><span data-stu-id="55121-139">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="55121-140">支持的值IID_ICorRuntimeHost或IID_ICLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="55121-140">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="55121-141">[出]返回的接口指针到`riid`。</span><span class="sxs-lookup"><span data-stu-id="55121-141">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55121-142">备注</span><span class="sxs-lookup"><span data-stu-id="55121-142">Remarks</span></span>  
 <span data-ttu-id="55121-143">如果`pwszVersion`指定不存在的运行时版本，`CorBindToRuntimeEx`则返回 hRESULT 值CLR_E_SHIM_RUNTIMELOAD。</span><span class="sxs-lookup"><span data-stu-id="55121-143">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="55121-144">执行上下文和 Windows 标识的流</span><span class="sxs-lookup"><span data-stu-id="55121-144">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="55121-145">在 CLR 的版本 1<xref:System.Security.Principal.WindowsIdentity>中，对象不会跨异步点（如新线程、线程池或计时器回调）流动。</span><span class="sxs-lookup"><span data-stu-id="55121-145">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="55121-146">在 CLR 的版本 2.0<xref:System.Threading.ExecutionContext>中，对象会包装有关当前正在执行的线程的一些信息，并将其流过任何异步点，但不跨应用程序域边界。</span><span class="sxs-lookup"><span data-stu-id="55121-146">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="55121-147">同样，<xref:System.Security.Principal.WindowsIdentity>对象也流过任何异步点。</span><span class="sxs-lookup"><span data-stu-id="55121-147">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="55121-148">因此，线程上的当前模拟（如果有）也会流动。</span><span class="sxs-lookup"><span data-stu-id="55121-148">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="55121-149">您可以通过两种方式更改流：</span><span class="sxs-lookup"><span data-stu-id="55121-149">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="55121-150">通过修改<xref:System.Threading.ExecutionContext>设置以按线程禁止流（请参阅 、<xref:System.Threading.ExecutionContext.SuppressFlow%2A><xref:System.Security.SecurityContext.SuppressFlow%2A>和方法）。 <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A></span><span class="sxs-lookup"><span data-stu-id="55121-150">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="55121-151">通过将进程默认模式更改为版本 1 兼容性模式，其中<xref:System.Security.Principal.WindowsIdentity>对象不会流过任何异步点，而不考虑当前线程上的<xref:System.Threading.ExecutionContext>设置。</span><span class="sxs-lookup"><span data-stu-id="55121-151">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="55121-152">更改默认模式的方式取决于您是使用托管可执行文件还是非托管托管接口来加载 CLR：</span><span class="sxs-lookup"><span data-stu-id="55121-152">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1. <span data-ttu-id="55121-153">对于托管可执行文件，必须将`enabled`[\<旧模拟策略>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)元素的属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="55121-153">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2. <span data-ttu-id="55121-154">对于非托管托管接口，在`STARTUP_LEGACY_IMPERSONATION`调用`startupFlags``CorBindToRuntimeEx`函数时在参数中设置标志。</span><span class="sxs-lookup"><span data-stu-id="55121-154">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `startupFlags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="55121-155">版本 1 兼容性模式适用于整个过程和流程中的所有应用程序域。</span><span class="sxs-lookup"><span data-stu-id="55121-155">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55121-156">要求</span><span class="sxs-lookup"><span data-stu-id="55121-156">Requirements</span></span>  
 <span data-ttu-id="55121-157">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="55121-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55121-158">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="55121-158">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55121-159">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="55121-159">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55121-160">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55121-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55121-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55121-161">See also</span></span>

- [<span data-ttu-id="55121-162">CorBindToCurrentRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="55121-162">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="55121-163">CorBindToRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="55121-163">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="55121-164">CorBindToRuntimeByCfg 函数</span><span class="sxs-lookup"><span data-stu-id="55121-164">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="55121-165">CorBindToRuntimeHost 函数</span><span class="sxs-lookup"><span data-stu-id="55121-165">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="55121-166">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="55121-166">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="55121-167">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="55121-167">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
