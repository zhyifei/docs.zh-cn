---
title: CorBindToRuntime 函数
ms.date: 03/30/2017
api_name:
- CorBindToRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntime
helpviewer_keywords:
- CorBindToRuntime function [.NET Framework hosting]
ms.assetid: 799740aa-46ec-4532-95da-6444565b4971
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb5c05a88c12b5124c77b0d0a7f834b405dd289f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59304618"
---
# <a name="corbindtoruntime-function"></a><span data-ttu-id="be6a3-102">CorBindToRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="be6a3-102">CorBindToRuntime Function</span></span>
<span data-ttu-id="be6a3-103">使非托管的宿主能够将公共语言运行时 (CLR) 加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="be6a3-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="be6a3-104">此函数中不推荐[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="be6a3-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be6a3-105">语法</span><span class="sxs-lookup"><span data-stu-id="be6a3-105">Syntax</span></span>  
  
```  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,   
    [in]  LPCWSTR     pwszBuildFlavor,   
    [in]  REFCLSID    rclsid,   
    [in]  REFIID      riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be6a3-106">参数</span><span class="sxs-lookup"><span data-stu-id="be6a3-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="be6a3-107">[in]想要加载的 CLR 版本描述的字符串。</span><span class="sxs-lookup"><span data-stu-id="be6a3-107">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="be6a3-108">.NET Framework 中的版本号用句点分隔的四个部分组成： *major.minor.build.revision*。</span><span class="sxs-lookup"><span data-stu-id="be6a3-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="be6a3-109">将字符串作为传递`pwszVersion`必须以字符"v"跟版本号 (例如，"v1.0.1529") 的前三个部分开头。</span><span class="sxs-lookup"><span data-stu-id="be6a3-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="be6a3-110">某些版本的 CLR 随指定与以前版本的 CLR 的兼容性的策略语句。</span><span class="sxs-lookup"><span data-stu-id="be6a3-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="be6a3-111">默认情况下，启动填充程序的计算结果`pwszVersion`针对策略语句和加载运行时的最新版本的是与所请求的版本兼容。</span><span class="sxs-lookup"><span data-stu-id="be6a3-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="be6a3-112">主机可以强制填充程序跳过策略评估和负载中指定的确切版本`pwszVersion`通过将的值传递`STARTUP_LOADER_SAFEMODE`为`flags`参数，如下所述。</span><span class="sxs-lookup"><span data-stu-id="be6a3-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `flags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="be6a3-113">如果调用方指定为 null `pwszVersion`，加载的运行时的最新版本。</span><span class="sxs-lookup"><span data-stu-id="be6a3-113">If the caller specifies null for `pwszVersion`, the latest version of the runtime is loaded.</span></span> <span data-ttu-id="be6a3-114">传递 null 不，则主机加载的运行时版本的任何控制。</span><span class="sxs-lookup"><span data-stu-id="be6a3-114">Passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="be6a3-115">虽然这种方法可能在某些情况下适用，但强烈建议主机提供一个要加载特定版本。</span><span class="sxs-lookup"><span data-stu-id="be6a3-115">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="be6a3-116">[in]一个字符串，指定是否加载在服务器或工作站的 clr 版本。</span><span class="sxs-lookup"><span data-stu-id="be6a3-116">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="be6a3-117">有效值为 `svr` 和 `wks`。</span><span class="sxs-lookup"><span data-stu-id="be6a3-117">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="be6a3-118">服务器生成经过优化，可充分利用多个处理器，用于垃圾回收和工作站生成优化的单处理器计算机上运行的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="be6a3-118">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="be6a3-119">如果`pwszBuildFlavor`设置为 null，则将加载工作站版本。</span><span class="sxs-lookup"><span data-stu-id="be6a3-119">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="be6a3-120">在单处理器计算机上运行时，工作站生成始终处于加载状态，即使`pwszBuildFlavor`设置为`svr`。</span><span class="sxs-lookup"><span data-stu-id="be6a3-120">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="be6a3-121">但是，如果`pwszBuildFlavor`设置为`svr`，并且指定并发垃圾回收 (请参阅的说明`flags`参数)，将加载服务器版本。</span><span class="sxs-lookup"><span data-stu-id="be6a3-121">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `flags` parameter), the server build is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="be6a3-122">[in]`CLSID`的实现的组件类[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="be6a3-122">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="be6a3-123">支持的值为 CLSID_CorRuntimeHost 或 CLSID_CLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="be6a3-123">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="be6a3-124">[in]`IID`从所请求的接口的`rclsid`。</span><span class="sxs-lookup"><span data-stu-id="be6a3-124">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="be6a3-125">支持的值为 IID_ICorRuntimeHost 或 IID_ICLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="be6a3-125">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="be6a3-126">[out]指向返回的接口指针`riid`。</span><span class="sxs-lookup"><span data-stu-id="be6a3-126">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be6a3-127">备注</span><span class="sxs-lookup"><span data-stu-id="be6a3-127">Remarks</span></span>  
 <span data-ttu-id="be6a3-128">如果`pwszVersion`指定不存在，运行时版本`CorBindToRuntimeEx`返回 CLR_E_SHIM_RUNTIMELOAD 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="be6a3-128">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="be6a3-129">执行上下文和流的 Windows 标识</span><span class="sxs-lookup"><span data-stu-id="be6a3-129">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="be6a3-130">在 CLR 版本 1<xref:System.Security.Principal.WindowsIdentity>对象不流经异步点，如新的线程，线程池或计时器回调。</span><span class="sxs-lookup"><span data-stu-id="be6a3-130">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="be6a3-131">在 2.0 版中的 clr<xref:System.Threading.ExecutionContext>对象封装有关当前正在执行的线程的一些信息，然后在任何异步点，但不是会跨应用程序域边界。</span><span class="sxs-lookup"><span data-stu-id="be6a3-131">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="be6a3-132">同样，<xref:System.Security.Principal.WindowsIdentity>对象还上任何异步点流动。</span><span class="sxs-lookup"><span data-stu-id="be6a3-132">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="be6a3-133">因此，在线程上的当前模拟如果有的话，也会流动。</span><span class="sxs-lookup"><span data-stu-id="be6a3-133">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="be6a3-134">您可以更改以下两种方式流：</span><span class="sxs-lookup"><span data-stu-id="be6a3-134">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="be6a3-135">通过修改<xref:System.Threading.ExecutionContext>设置，以禁止显示上每个线程进行的流 (请参阅<xref:System.Threading.ExecutionContext.SuppressFlow%2A>， <xref:System.Security.SecurityContext.SuppressFlow%2A>，和<xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A>方法)。</span><span class="sxs-lookup"><span data-stu-id="be6a3-135">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="be6a3-136">通过更改进程的默认模式为第 1 版兼容性模式，其中<xref:System.Security.Principal.WindowsIdentity>对象不流经异步的任何时刻，而不考虑<xref:System.Threading.ExecutionContext>当前线程上的设置。</span><span class="sxs-lookup"><span data-stu-id="be6a3-136">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="be6a3-137">如何更改默认模式取决于是否使用托管可执行文件或使用非托管承载接口能够将 CLR 加载：</span><span class="sxs-lookup"><span data-stu-id="be6a3-137">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1.  <span data-ttu-id="be6a3-138">用于托管可执行文件，必须设置`enabled`的属性[ \<legacyImpersonationPolicy >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)元素`true`。</span><span class="sxs-lookup"><span data-stu-id="be6a3-138">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2.  <span data-ttu-id="be6a3-139">对于非托管承载接口，将`STARTUP_LEGACY_IMPERSONATION`中的标志`flags`参数调用时`CorBindToRuntimeEx`函数。</span><span class="sxs-lookup"><span data-stu-id="be6a3-139">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `flags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="be6a3-140">第 1 版兼容性模式适用于整个过程和进程中的所有应用程序域。</span><span class="sxs-lookup"><span data-stu-id="be6a3-140">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be6a3-141">备注</span><span class="sxs-lookup"><span data-stu-id="be6a3-141">Remarks</span></span>  
 <span data-ttu-id="be6a3-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)并`CorBindToRuntime`执行相同的操作，但`CorBindToRuntimeEx`函数允许您设置标志以指定 CLR 的行为。</span><span class="sxs-lookup"><span data-stu-id="be6a3-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and `CorBindToRuntime` perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be6a3-143">要求</span><span class="sxs-lookup"><span data-stu-id="be6a3-143">Requirements</span></span>  
 <span data-ttu-id="be6a3-144">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="be6a3-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be6a3-145">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="be6a3-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="be6a3-146">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="be6a3-146">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="be6a3-147">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="be6a3-147">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="be6a3-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="be6a3-148">See also</span></span>

- [<span data-ttu-id="be6a3-149">CorBindToCurrentRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="be6a3-149">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="be6a3-150">CorBindToRuntimeByCfg 函数</span><span class="sxs-lookup"><span data-stu-id="be6a3-150">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="be6a3-151">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="be6a3-151">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="be6a3-152">CorBindToRuntimeHost 函数</span><span class="sxs-lookup"><span data-stu-id="be6a3-152">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="be6a3-153">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="be6a3-153">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="be6a3-154">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="be6a3-154">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
