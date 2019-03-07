---
title: CorBindToRuntimeHost 函数
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeHost
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeHost
helpviewer_keywords:
- CorBindToRuntimeHost function [.NET Framework hosting]
ms.assetid: 5c826ba3-8258-49bc-a417-78807915fcaf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4822a63bf2524582d2dc7677385d26b8914ca0a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488998"
---
# <a name="corbindtoruntimehost-function"></a><span data-ttu-id="e5d6f-102">CorBindToRuntimeHost 函数</span><span class="sxs-lookup"><span data-stu-id="e5d6f-102">CorBindToRuntimeHost Function</span></span>
<span data-ttu-id="e5d6f-103">使主机能够加载到进程的指定公共语言运行时 (CLR) 版本。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-103">Enables hosts to load a specified version of the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="e5d6f-104">此函数中不推荐[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5d6f-105">语法</span><span class="sxs-lookup"><span data-stu-id="e5d6f-105">Syntax</span></span>  
  
```  
HRESULT CorBindToRuntimeHost (  
    [in] LPCWSTR       pwszVersion,   
    [in] LPCWSTR       pwszBuildFlavor,   
    [in] LPCWSTR       pwszHostConfigFile,   
    [in] VOID*         pReserved,   
    [in] DWORD         startupFlags,   
    [in] REFCLSID      rclsid,   
    [in] REFIID        riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5d6f-106">参数</span><span class="sxs-lookup"><span data-stu-id="e5d6f-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="e5d6f-107">[in]一个字符串，描述要加载的 clr 版本。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-107">[in] A string that describes the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="e5d6f-108">.NET Framework 中的版本号用句点分隔的四个部分组成： *major.minor.build.revision*。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="e5d6f-109">将字符串作为传递`pwszVersion`必须以字符"v"跟版本号 (例如，"v1.0.1529") 的前三个部分开头。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="e5d6f-110">某些版本的 CLR 随指定与以前版本的 CLR 的兼容性的策略语句。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="e5d6f-111">默认情况下，启动填充程序的计算结果`pwszVersion`针对策略语句和加载运行时的最新版本的是与所请求的版本兼容。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="e5d6f-112">主机可以强制填充程序跳过策略评估和负载中指定的确切版本`pwszVersion`通过传递的值为 STARTUP_LOADER_SAFEMODE`startupFlags`参数。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of STARTUP_LOADER_SAFEMODE for the `startupFlags` parameter.</span></span>  
  
 <span data-ttu-id="e5d6f-113">如果`pwszVersion`是`null,`方法不会加载任何版本的 CLR。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-113">If `pwszVersion` is `null,` the method does not load any version of the CLR.</span></span> <span data-ttu-id="e5d6f-114">相反，它将返回 CLR_E_SHIM_RUNTIMELOAD，指示它未能加载运行时。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-114">Instead, it returns CLR_E_SHIM_RUNTIMELOAD, which indicates that it failed to load the runtime.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="e5d6f-115">[in]一个字符串，指定是否加载在服务器或工作站的 clr 版本。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-115">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="e5d6f-116">有效值为 `svr` 和 `wks`。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-116">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="e5d6f-117">服务器生成经过优化，可充分利用多个处理器，用于垃圾回收和工作站生成优化的单处理器计算机上运行的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-117">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="e5d6f-118">如果`pwszBuildFlavor`设置为 null，则将加载工作站版本。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-118">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="e5d6f-119">在单处理器计算机上运行时，工作站生成始终处于加载状态，即使`pwszBuildFlavor`设置为`svr`。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-119">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="e5d6f-120">但是，如果`pwszBuildFlavor`设置为`svr`，并且指定并发垃圾回收 (请参阅的说明`startupFlags`参数)，将加载服务器版本。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-120">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5d6f-121">在应用程序运行在 WOW64 中不支持并发垃圾回收 x86 仿真程序上实现 Intel Itanium 体系结构 （以前称为 IA-64） 的 64 位系统。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-121">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="e5d6f-122">有关在 64 位 Windows 系统上使用 WOW64 的详细信息，请参阅[运行 32 位应用程序](/windows/desktop/WinProg64/running-32-bit-applications)。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-122">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
 `pwszHostConfigFile`  
 <span data-ttu-id="e5d6f-123">[in]指定要加载的 CLR 版本的主机配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-123">[in] The name of a host configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="e5d6f-124">如果文件名称不包括完全限定的路径，则假定文件中进行调用的可执行文件所在的目录。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-124">If the file name does not include a fully qualified path, the file is assumed to be in the same directory as the executable that is making the call.</span></span>  
  
 `pReserved`  
 <span data-ttu-id="e5d6f-125">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-125">[in] Reserved for future extensibility.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="e5d6f-126">[in]一组标志，用于控制并发垃圾回收、 非特定于域的代码和行为的`pwszVersion`参数。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-126">[in] A set of flags that controls concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="e5d6f-127">如果未设置标志，则默认值为单一域。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-127">The default is single domain if no flag is set.</span></span> <span data-ttu-id="e5d6f-128">有关支持的值的列表，请参阅[STARTUP_FLAGS 枚举](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-128">For a list of supported values, see the [STARTUP_FLAGS enumeration](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).</span></span>  
  
 `rclsid`  
 <span data-ttu-id="e5d6f-129">[in]`CLSID`的实现的组件类[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-129">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="e5d6f-130">支持的值为 CLSID_CorRuntimeHost 或 CLSID_CLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-130">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="e5d6f-131">[in]`IID`您请求的接口。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-131">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="e5d6f-132">支持的值为 IID_ICorRuntimeHost 或 IID_ICLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-132">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="e5d6f-133">[out]指向已加载的运行时版本的接口指针。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-133">[out] An interface pointer to the version of the runtime that was loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5d6f-134">要求</span><span class="sxs-lookup"><span data-stu-id="e5d6f-134">Requirements</span></span>  
 <span data-ttu-id="e5d6f-135">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e5d6f-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5d6f-136">**标头：** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="e5d6f-136">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="e5d6f-137">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e5d6f-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5d6f-138">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5d6f-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5d6f-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5d6f-139">See also</span></span>
- [<span data-ttu-id="e5d6f-140">CorBindToCurrentRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="e5d6f-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="e5d6f-141">CorBindToRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="e5d6f-141">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="e5d6f-142">CorBindToRuntimeByCfg 函数</span><span class="sxs-lookup"><span data-stu-id="e5d6f-142">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="e5d6f-143">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="e5d6f-143">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="e5d6f-144">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="e5d6f-144">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="e5d6f-145">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="e5d6f-145">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
