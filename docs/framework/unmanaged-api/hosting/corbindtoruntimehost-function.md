---
title: "CorBindToRuntimeHost 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e6d69f39aa74665843b0bf91407e764ea67f41d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corbindtoruntimehost-function"></a><span data-ttu-id="ebf6b-102">CorBindToRuntimeHost 函数</span><span class="sxs-lookup"><span data-stu-id="ebf6b-102">CorBindToRuntimeHost Function</span></span>
<span data-ttu-id="ebf6b-103">使主机可以加载到进程的指定公共语言运行时 (CLR) 版本。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-103">Enables hosts to load a specified version of the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="ebf6b-104">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebf6b-105">语法</span><span class="sxs-lookup"><span data-stu-id="ebf6b-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="ebf6b-106">参数</span><span class="sxs-lookup"><span data-stu-id="ebf6b-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="ebf6b-107">[in]一个字符串，描述要加载的 clr 的版本。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-107">[in] A string that describes the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="ebf6b-108">.NET Framework 中的版本号用句点分隔的四个部分组成： *major.minor.build.revision*。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="ebf6b-109">将字符串作为传递`pwszVersion`必须以字符"v"跟版本号 (例如，"v1.0.1529") 的前三个部分开头。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="ebf6b-110">某些版本的 CLR 与指定与以前版本的 CLR 的兼容性的策略语句一起安装。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="ebf6b-111">默认情况下，启动填充码将评估`pwszVersion`针对策略语句和加载运行时的最新版本的适用于所请求的版本。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="ebf6b-112">主机可以强制填充码可跳过策略评估，负载中指定的确切版本`pwszVersion`通过传递一个值为 STARTUP_LOADER_SAFEMODE`startupFlags`参数。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of STARTUP_LOADER_SAFEMODE for the `startupFlags` parameter.</span></span>  
  
 <span data-ttu-id="ebf6b-113">如果`pwszVersion`是`null,`方法不会加载任何版本的 CLR。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-113">If `pwszVersion` is `null,` the method does not load any version of the CLR.</span></span> <span data-ttu-id="ebf6b-114">相反，它将返回 CLR_E_SHIM_RUNTIMELOAD，指示它未能将运行时加载。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-114">Instead, it returns CLR_E_SHIM_RUNTIMELOAD, which indicates that it failed to load the runtime.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="ebf6b-115">[in]一个字符串，指定是否以加载服务器或工作站生成的 CLR。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-115">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="ebf6b-116">有效值为 `svr` 和 `wks`。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-116">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="ebf6b-117">服务器版本进行了优化以利用多个处理器进行垃圾回收和工作站生成优化的单处理器计算机上运行的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-117">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="ebf6b-118">如果`pwszBuildFlavor`设置为 null，则将加载工作站版本。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-118">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="ebf6b-119">单处理器计算机上运行时，工作站生成始终处于加载状态，即使`pwszBuildFlavor`设置为`svr`。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-119">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="ebf6b-120">但是，如果`pwszBuildFlavor`设置为`svr`和指定并发垃圾回收 (请参阅的说明`startupFlags`参数)，则服务器将加载版本。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-120">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ebf6b-121">运行 WOW64 应用程序中不支持并发垃圾回收 x86 仿真程序上实现 （以前称为 ia-64） 的 Intel 的 Itanium 体系结构的 64 位系统。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-121">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="ebf6b-122">有关使用 64 位 Windows 系统上的 WOW64 的详细信息，请参阅[运行 32 位应用程序](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-122">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx).</span></span>  
  
 `pwszHostConfigFile`  
 <span data-ttu-id="ebf6b-123">[in]指定要加载的 clr 版本的主机配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-123">[in] The name of a host configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="ebf6b-124">如果文件名称不包含完全限定的路径，则假定文件进行调用的可执行文件所在相同目录中。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-124">If the file name does not include a fully qualified path, the file is assumed to be in the same directory as the executable that is making the call.</span></span>  
  
 `pReserved`  
 <span data-ttu-id="ebf6b-125">[in]留待将来扩展。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-125">[in] Reserved for future extensibility.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="ebf6b-126">[in]一组控制并发垃圾回收、 非特定于域的代码和的行为的标志`pwszVersion`参数。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-126">[in] A set of flags that controls concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="ebf6b-127">如果未设置标志，则默认值是单一域。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-127">The default is single domain if no flag is set.</span></span> <span data-ttu-id="ebf6b-128">有关支持的值的列表，请参阅[STARTUP_FLAGS 枚举](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-128">For a list of supported values, see the [STARTUP_FLAGS enumeration](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).</span></span>  
  
 `rclsid`  
 <span data-ttu-id="ebf6b-129">[in]`CLSID`实现的组件类的[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-129">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="ebf6b-130">支持的值为 CLSID_CorRuntimeHost 或 CLSID_CLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-130">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="ebf6b-131">[in]`IID`您请求的接口。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-131">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="ebf6b-132">支持的值为 IID_ICorRuntimeHost 或 IID_ICLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-132">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="ebf6b-133">[out]指向已加载的运行时版本的接口指针。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-133">[out] An interface pointer to the version of the runtime that was loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebf6b-134">惠?</span><span class="sxs-lookup"><span data-stu-id="ebf6b-134">Requirements</span></span>  
 <span data-ttu-id="ebf6b-135">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ebf6b-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebf6b-136">**标头：** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="ebf6b-136">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="ebf6b-137">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ebf6b-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ebf6b-138">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebf6b-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebf6b-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="ebf6b-139">See Also</span></span>  
 [<span data-ttu-id="ebf6b-140">CorBindToCurrentRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="ebf6b-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [<span data-ttu-id="ebf6b-141">CorBindToRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="ebf6b-141">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [<span data-ttu-id="ebf6b-142">CorBindToRuntimeByCfg 函数</span><span class="sxs-lookup"><span data-stu-id="ebf6b-142">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [<span data-ttu-id="ebf6b-143">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="ebf6b-143">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="ebf6b-144">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="ebf6b-144">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="ebf6b-145">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="ebf6b-145">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
