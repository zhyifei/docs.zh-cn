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
ms.openlocfilehash: 6566adc442034763e0209869404b60b5afa63866
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176482"
---
# <a name="corbindtoruntimehost-function"></a><span data-ttu-id="2ac21-102">CorBindToRuntimeHost 函数</span><span class="sxs-lookup"><span data-stu-id="2ac21-102">CorBindToRuntimeHost Function</span></span>
<span data-ttu-id="2ac21-103">使主机能够将指定版本的通用语言运行时 （CLR） 加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="2ac21-103">Enables hosts to load a specified version of the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="2ac21-104">此功能已在 .NET 框架 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="2ac21-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ac21-105">语法</span><span class="sxs-lookup"><span data-stu-id="2ac21-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="2ac21-106">parameters</span><span class="sxs-lookup"><span data-stu-id="2ac21-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="2ac21-107">[在]描述要加载的 CLR 版本的字符串。</span><span class="sxs-lookup"><span data-stu-id="2ac21-107">[in] A string that describes the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="2ac21-108">.NET 框架中的版本号由四个部分组成，由句点分隔：*主要.minor.build.revision*.</span><span class="sxs-lookup"><span data-stu-id="2ac21-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="2ac21-109">传递的`pwszVersion`字符串必须以字符"v"开头，后跟版本号的前三个部分（例如，"v1.0.1529"）。</span><span class="sxs-lookup"><span data-stu-id="2ac21-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="2ac21-110">CLR 的某些版本都安装了策略语句，该语句指定与 CLR 的早期版本的兼容性。</span><span class="sxs-lookup"><span data-stu-id="2ac21-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="2ac21-111">默认情况下，启动希姆`pwszVersion`根据策略语句进行评估，并加载与所请求版本兼容的最新版本的运行时。</span><span class="sxs-lookup"><span data-stu-id="2ac21-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="2ac21-112">主机可以通过传递`startupFlags`参数的STARTUP_LOADER_SAFEMODE值来强制 him 跳过策略评估并加载指定`pwszVersion`的确切版本。</span><span class="sxs-lookup"><span data-stu-id="2ac21-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of STARTUP_LOADER_SAFEMODE for the `startupFlags` parameter.</span></span>  
  
 <span data-ttu-id="2ac21-113">如果`pwszVersion`是`null,`，该方法不会加载 CLR 的任何版本。</span><span class="sxs-lookup"><span data-stu-id="2ac21-113">If `pwszVersion` is `null,` the method does not load any version of the CLR.</span></span> <span data-ttu-id="2ac21-114">相反，它将返回CLR_E_SHIM_RUNTIMELOAD，这表明它无法加载运行时。</span><span class="sxs-lookup"><span data-stu-id="2ac21-114">Instead, it returns CLR_E_SHIM_RUNTIMELOAD, which indicates that it failed to load the runtime.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="2ac21-115">[在]指定是加载 CLR 的服务器还是工作站构建的字符串。</span><span class="sxs-lookup"><span data-stu-id="2ac21-115">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="2ac21-116">有效值为 `svr` 和 `wks`。</span><span class="sxs-lookup"><span data-stu-id="2ac21-116">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="2ac21-117">服务器生成经过优化，以利用多个处理器进行垃圾回收，工作站生成针对在单处理器计算机上运行的客户端应用程序进行了优化。</span><span class="sxs-lookup"><span data-stu-id="2ac21-117">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="2ac21-118">如果`pwszBuildFlavor`设置为 null，则加载工作站生成。</span><span class="sxs-lookup"><span data-stu-id="2ac21-118">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="2ac21-119">在单处理器计算机上运行时，工作站生成始终加载，即使`pwszBuildFlavor`设置为`svr`。</span><span class="sxs-lookup"><span data-stu-id="2ac21-119">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="2ac21-120">但是，如果`pwszBuildFlavor`设置为`svr`并指定了并发垃圾回收（请参阅`startupFlags`参数的说明），则加载服务器生成。</span><span class="sxs-lookup"><span data-stu-id="2ac21-120">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2ac21-121">在 64 位系统上运行 WOW64 x86 仿真器的应用程序不支持并发垃圾回收，这些系统实现了英特尔 Itanium 架构（以前称为 IA-64）。</span><span class="sxs-lookup"><span data-stu-id="2ac21-121">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="2ac21-122">有关在 64 位 Windows 系统上使用 WOW64 的详细信息，请参阅[运行 32 位应用程序](/windows/desktop/WinProg64/running-32-bit-applications)。</span><span class="sxs-lookup"><span data-stu-id="2ac21-122">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](/windows/desktop/WinProg64/running-32-bit-applications).</span></span>  
  
 `pwszHostConfigFile`  
 <span data-ttu-id="2ac21-123">[在]指定要加载的 CLR 版本的主机配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="2ac21-123">[in] The name of a host configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="2ac21-124">如果文件名不包含完全限定的路径，则假定该文件与进行调用的可执行文件位于同一目录中。</span><span class="sxs-lookup"><span data-stu-id="2ac21-124">If the file name does not include a fully qualified path, the file is assumed to be in the same directory as the executable that is making the call.</span></span>  
  
 `pReserved`  
 <span data-ttu-id="2ac21-125">[在]保留以供将来扩展。</span><span class="sxs-lookup"><span data-stu-id="2ac21-125">[in] Reserved for future extensibility.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="2ac21-126">[在]控制并发垃圾回收、域中立代码和`pwszVersion`参数行为的标志集。</span><span class="sxs-lookup"><span data-stu-id="2ac21-126">[in] A set of flags that controls concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="2ac21-127">如果未设置标志，则默认值为单个域。</span><span class="sxs-lookup"><span data-stu-id="2ac21-127">The default is single domain if no flag is set.</span></span> <span data-ttu-id="2ac21-128">有关受支持值的列表，请参阅[STARTUP_FLAGS枚举](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="2ac21-128">For a list of supported values, see the [STARTUP_FLAGS enumeration](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).</span></span>  
  
 `rclsid`  
 <span data-ttu-id="2ac21-129">[在]`CLSID`实现[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口的共类。</span><span class="sxs-lookup"><span data-stu-id="2ac21-129">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="2ac21-130">支持的值CLSID_CorRuntimeHost或CLSID_CLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="2ac21-130">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="2ac21-131">[在]您`IID`请求的接口的。</span><span class="sxs-lookup"><span data-stu-id="2ac21-131">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="2ac21-132">支持的值IID_ICorRuntimeHost或IID_ICLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="2ac21-132">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="2ac21-133">[出]指向加载的运行时版本的接口指针。</span><span class="sxs-lookup"><span data-stu-id="2ac21-133">[out] An interface pointer to the version of the runtime that was loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ac21-134">要求</span><span class="sxs-lookup"><span data-stu-id="2ac21-134">Requirements</span></span>  
 <span data-ttu-id="2ac21-135">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2ac21-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ac21-136">**标题：** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="2ac21-136">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="2ac21-137">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2ac21-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ac21-138">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ac21-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ac21-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ac21-139">See also</span></span>

- [<span data-ttu-id="2ac21-140">CorBindToCurrentRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="2ac21-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="2ac21-141">CorBindToRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="2ac21-141">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="2ac21-142">CorBindToRuntimeByCfg 函数</span><span class="sxs-lookup"><span data-stu-id="2ac21-142">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="2ac21-143">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="2ac21-143">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="2ac21-144">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="2ac21-144">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="2ac21-145">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="2ac21-145">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
