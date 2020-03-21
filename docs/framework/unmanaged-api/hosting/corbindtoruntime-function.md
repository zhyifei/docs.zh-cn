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
ms.openlocfilehash: 2db9d26ef2dec150977c468b16334a7cb4b3d49c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176508"
---
# <a name="corbindtoruntime-function"></a><span data-ttu-id="e42d4-102">CorBindToRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="e42d4-102">CorBindToRuntime Function</span></span>
<span data-ttu-id="e42d4-103">使非托管主机能够将通用语言运行时 （CLR） 加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="e42d4-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="e42d4-104">此功能已在 .NET 框架 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="e42d4-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e42d4-105">语法</span><span class="sxs-lookup"><span data-stu-id="e42d4-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,
    [in]  LPCWSTR     pwszBuildFlavor,
    [in]  REFCLSID    rclsid,
    [in]  REFIID      riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e42d4-106">parameters</span><span class="sxs-lookup"><span data-stu-id="e42d4-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="e42d4-107">[在]描述要加载的 CLR 版本的字符串。</span><span class="sxs-lookup"><span data-stu-id="e42d4-107">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="e42d4-108">.NET 框架中的版本号由四个部分组成，由句点分隔：*主要.minor.build.revision*.</span><span class="sxs-lookup"><span data-stu-id="e42d4-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="e42d4-109">传递的`pwszVersion`字符串必须以字符"v"开头，后跟版本号的前三个部分（例如，"v1.0.1529"）。</span><span class="sxs-lookup"><span data-stu-id="e42d4-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="e42d4-110">CLR 的某些版本都安装了策略语句，该语句指定与 CLR 的早期版本的兼容性。</span><span class="sxs-lookup"><span data-stu-id="e42d4-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="e42d4-111">默认情况下，启动希姆`pwszVersion`根据策略语句进行评估，并加载与所请求版本兼容的最新版本的运行时。</span><span class="sxs-lookup"><span data-stu-id="e42d4-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="e42d4-112">主机可以强制 him 跳过策略评估，并通过传递`pwszVersion``STARTUP_LOADER_SAFEMODE``flags`参数的值来加载指定的确切版本，如下所述。</span><span class="sxs-lookup"><span data-stu-id="e42d4-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `flags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="e42d4-113">如果调用方为`pwszVersion`指定 null，则加载运行时的最新版本。</span><span class="sxs-lookup"><span data-stu-id="e42d4-113">If the caller specifies null for `pwszVersion`, the latest version of the runtime is loaded.</span></span> <span data-ttu-id="e42d4-114">传递 null 使主机无法控制加载的哪个版本的运行时。</span><span class="sxs-lookup"><span data-stu-id="e42d4-114">Passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="e42d4-115">尽管此方法在某些情况下可能适用，但强烈建议主机提供要加载的特定版本。</span><span class="sxs-lookup"><span data-stu-id="e42d4-115">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="e42d4-116">[在]指定是加载 CLR 的服务器还是工作站构建的字符串。</span><span class="sxs-lookup"><span data-stu-id="e42d4-116">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="e42d4-117">有效值为 `svr` 和 `wks`。</span><span class="sxs-lookup"><span data-stu-id="e42d4-117">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="e42d4-118">服务器生成经过优化，以利用多个处理器进行垃圾回收，工作站生成针对在单处理器计算机上运行的客户端应用程序进行了优化。</span><span class="sxs-lookup"><span data-stu-id="e42d4-118">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="e42d4-119">如果`pwszBuildFlavor`设置为 null，则加载工作站生成。</span><span class="sxs-lookup"><span data-stu-id="e42d4-119">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="e42d4-120">在单处理器计算机上运行时，工作站生成始终加载，即使`pwszBuildFlavor`设置为`svr`。</span><span class="sxs-lookup"><span data-stu-id="e42d4-120">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="e42d4-121">但是，如果`pwszBuildFlavor`设置为`svr`并指定了并发垃圾回收（请参阅`flags`参数的说明），则加载服务器生成。</span><span class="sxs-lookup"><span data-stu-id="e42d4-121">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `flags` parameter), the server build is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="e42d4-122">[在]`CLSID`实现[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口的共类。</span><span class="sxs-lookup"><span data-stu-id="e42d4-122">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="e42d4-123">支持的值CLSID_CorRuntimeHost或CLSID_CLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="e42d4-123">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="e42d4-124">[在]从`IID`的请求接口的`rclsid`的</span><span class="sxs-lookup"><span data-stu-id="e42d4-124">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="e42d4-125">支持的值IID_ICorRuntimeHost或IID_ICLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="e42d4-125">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="e42d4-126">[出]返回的接口指针到`riid`。</span><span class="sxs-lookup"><span data-stu-id="e42d4-126">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e42d4-127">备注</span><span class="sxs-lookup"><span data-stu-id="e42d4-127">Remarks</span></span>  
 <span data-ttu-id="e42d4-128">如果`pwszVersion`指定不存在的运行时版本，`CorBindToRuntimeEx`则返回 hRESULT 值CLR_E_SHIM_RUNTIMELOAD。</span><span class="sxs-lookup"><span data-stu-id="e42d4-128">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="e42d4-129">执行上下文和 Windows 标识的流</span><span class="sxs-lookup"><span data-stu-id="e42d4-129">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="e42d4-130">在 CLR 的版本 1<xref:System.Security.Principal.WindowsIdentity>中，对象不会跨异步点（如新线程、线程池或计时器回调）流动。</span><span class="sxs-lookup"><span data-stu-id="e42d4-130">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="e42d4-131">在 CLR 的版本 2.0<xref:System.Threading.ExecutionContext>中，对象会包装有关当前正在执行的线程的一些信息，并将其流过任何异步点，但不跨应用程序域边界。</span><span class="sxs-lookup"><span data-stu-id="e42d4-131">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="e42d4-132">同样，<xref:System.Security.Principal.WindowsIdentity>对象也流过任何异步点。</span><span class="sxs-lookup"><span data-stu-id="e42d4-132">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="e42d4-133">因此，线程上的当前模拟（如果有）也会流动。</span><span class="sxs-lookup"><span data-stu-id="e42d4-133">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="e42d4-134">您可以通过两种方式更改流：</span><span class="sxs-lookup"><span data-stu-id="e42d4-134">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="e42d4-135">通过修改<xref:System.Threading.ExecutionContext>设置以按线程禁止流（请参阅 、<xref:System.Threading.ExecutionContext.SuppressFlow%2A><xref:System.Security.SecurityContext.SuppressFlow%2A>和方法）。 <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A></span><span class="sxs-lookup"><span data-stu-id="e42d4-135">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="e42d4-136">通过将进程默认模式更改为版本 1 兼容性模式，其中<xref:System.Security.Principal.WindowsIdentity>对象不会流过任何异步点，而不考虑当前线程上的<xref:System.Threading.ExecutionContext>设置。</span><span class="sxs-lookup"><span data-stu-id="e42d4-136">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="e42d4-137">更改默认模式的方式取决于您是使用托管可执行文件还是非托管托管接口来加载 CLR：</span><span class="sxs-lookup"><span data-stu-id="e42d4-137">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1. <span data-ttu-id="e42d4-138">对于托管可执行文件，必须将`enabled`[\<旧模拟策略>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)元素的属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="e42d4-138">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2. <span data-ttu-id="e42d4-139">对于非托管托管接口，在`STARTUP_LEGACY_IMPERSONATION`调用`flags``CorBindToRuntimeEx`函数时在参数中设置标志。</span><span class="sxs-lookup"><span data-stu-id="e42d4-139">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `flags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="e42d4-140">版本 1 兼容性模式适用于整个过程和流程中的所有应用程序域。</span><span class="sxs-lookup"><span data-stu-id="e42d4-140">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e42d4-141">备注</span><span class="sxs-lookup"><span data-stu-id="e42d4-141">Remarks</span></span>  
 <span data-ttu-id="e42d4-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) `CorBindToRuntime`并执行相同的操作，`CorBindToRuntimeEx`但该函数允许您设置标志以指定 CLR 的行为。</span><span class="sxs-lookup"><span data-stu-id="e42d4-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and `CorBindToRuntime` perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e42d4-143">要求</span><span class="sxs-lookup"><span data-stu-id="e42d4-143">Requirements</span></span>  
 <span data-ttu-id="e42d4-144">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e42d4-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e42d4-145">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e42d4-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e42d4-146">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e42d4-146">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e42d4-147">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e42d4-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e42d4-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e42d4-148">See also</span></span>

- [<span data-ttu-id="e42d4-149">CorBindToCurrentRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="e42d4-149">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="e42d4-150">CorBindToRuntimeByCfg 函数</span><span class="sxs-lookup"><span data-stu-id="e42d4-150">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="e42d4-151">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="e42d4-151">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="e42d4-152">CorBindToRuntimeHost 函数</span><span class="sxs-lookup"><span data-stu-id="e42d4-152">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="e42d4-153">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="e42d4-153">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="e42d4-154">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="e42d4-154">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
