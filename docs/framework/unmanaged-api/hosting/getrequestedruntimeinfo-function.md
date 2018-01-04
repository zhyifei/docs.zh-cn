---
title: "GetRequestedRuntimeInfo 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetRequestedRuntimeInfo
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: GetRequestedRuntimeInfo
helpviewer_keywords: GetRequestedRuntimeInfo function [.NET Framework hosting]
ms.assetid: 0dfd7cdc-c116-4e25-b56a-ac7b0378c942
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 49459001d3764988eff7b7a4381a843c44e596cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="30f68-102">GetRequestedRuntimeInfo 函数</span><span class="sxs-lookup"><span data-stu-id="30f68-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="30f68-103">获取有关公共语言运行时 (CLR) 请求的应用程序版本和目录信息。</span><span class="sxs-lookup"><span data-stu-id="30f68-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="30f68-104">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="30f68-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30f68-105">语法</span><span class="sxs-lookup"><span data-stu-id="30f68-105">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeInfo (  
    [in]  LPCWSTR  pExe,   
    [in]  LPCWSTR  pwszVersion,   
    [in]  LPCWSTR  pConfigurationFile,   
    [in]  DWORD    startupFlags,   
    [in]  DWORD    runtimeInfoFlags,   
    [out] LPWSTR   pDirectory,   
    [in]  DWORD    dwDirectory,   
    [out] DWORD   *dwDirectoryLength,   
    [out] LPWSTR   pVersion,   
    [in]  DWORD    cchBuffer,   
    [out] DWORD   *dwlength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30f68-106">参数</span><span class="sxs-lookup"><span data-stu-id="30f68-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="30f68-107">[in]应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="30f68-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="30f68-108">[in]指定运行时的版本号的字符串。</span><span class="sxs-lookup"><span data-stu-id="30f68-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="30f68-109">[in]与关联的配置文件的名称`pExe`。</span><span class="sxs-lookup"><span data-stu-id="30f68-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="30f68-110">[in]一个或多个[STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)枚举值。</span><span class="sxs-lookup"><span data-stu-id="30f68-110">[in] One or more of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="30f68-111">[in]一个或多个[RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)枚举值。</span><span class="sxs-lookup"><span data-stu-id="30f68-111">[in] One or more of the [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="30f68-112">[out]包含成功完成后运行时的目录路径的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="30f68-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="30f68-113">[in]目录缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="30f68-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="30f68-114">[out]指向目录的路径字符串的长度的指针。</span><span class="sxs-lookup"><span data-stu-id="30f68-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="30f68-115">[out]包含成功完成后运行时的版本号的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="30f68-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="30f68-116">[in]版本字符串缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="30f68-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="30f68-117">[out]指向版本字符串的长度的指针。</span><span class="sxs-lookup"><span data-stu-id="30f68-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30f68-118">返回值</span><span class="sxs-lookup"><span data-stu-id="30f68-118">Return Value</span></span>  
 <span data-ttu-id="30f68-119">此方法返回标准的组件对象模型 (COM) 错误代码，除了以下值中 WinError.h，定义。</span><span class="sxs-lookup"><span data-stu-id="30f68-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="30f68-120">返回代码</span><span class="sxs-lookup"><span data-stu-id="30f68-120">Return code</span></span>|<span data-ttu-id="30f68-121">描述</span><span class="sxs-lookup"><span data-stu-id="30f68-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="30f68-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="30f68-122">S_OK</span></span>|<span data-ttu-id="30f68-123">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="30f68-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="30f68-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="30f68-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="30f68-125">在目录缓冲区未足以存储的目录路径。</span><span class="sxs-lookup"><span data-stu-id="30f68-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="30f68-126">- 或 -</span><span class="sxs-lookup"><span data-stu-id="30f68-126">- or -</span></span><br /><br /> <span data-ttu-id="30f68-127">在版本缓冲区未足以存储的版本字符串。</span><span class="sxs-lookup"><span data-stu-id="30f68-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30f68-128">备注</span><span class="sxs-lookup"><span data-stu-id="30f68-128">Remarks</span></span>  
 <span data-ttu-id="30f68-129">`GetRequestedRuntimeInfo`方法返回运行时加载到进程，这不一定是最新版本的计算机上安装的版本信息。</span><span class="sxs-lookup"><span data-stu-id="30f68-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="30f68-130">在.NET Framework 2.0 版中，你可以通过获取有关最新安装的版本信息`GetRequestedRuntimeInfo`方法，如下所示：</span><span class="sxs-lookup"><span data-stu-id="30f68-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
-   <span data-ttu-id="30f68-131">指定`pExe`， `pwszVersion`，和`pConfigurationFile`参数为 null。</span><span class="sxs-lookup"><span data-stu-id="30f68-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
-   <span data-ttu-id="30f68-132">指定在 RUNTIME_INFO_UPGRADE_VERSION 标志`RUNTIME_INFO_FLAGS`枚举的`runtimeInfoFlags`参数。</span><span class="sxs-lookup"><span data-stu-id="30f68-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="30f68-133">`GetRequestedRuntimeInfo`方法不在以下情况下返回的最新的 CLR 版本：</span><span class="sxs-lookup"><span data-stu-id="30f68-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
-   <span data-ttu-id="30f68-134">指定正在加载特定的 CLR 版本的应用程序配置文件存在。</span><span class="sxs-lookup"><span data-stu-id="30f68-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="30f68-135">请注意，.NET Framework 将使用配置文件，即使你指定为空`pConfigurationFile`参数。</span><span class="sxs-lookup"><span data-stu-id="30f68-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
-   <span data-ttu-id="30f68-136">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)方法调用指定的早期的 CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="30f68-136">The [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
-   <span data-ttu-id="30f68-137">当前正在运行的应用程序编译为较早的 CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="30f68-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="30f68-138">有关`runtimeInfoFlags`参数，你可以指定的体系结构常量之一`RUNTIME_INFO_FLAGS`一次的枚举：</span><span class="sxs-lookup"><span data-stu-id="30f68-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
-   <span data-ttu-id="30f68-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="30f68-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
-   <span data-ttu-id="30f68-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="30f68-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
-   <span data-ttu-id="30f68-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="30f68-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30f68-142">惠?</span><span class="sxs-lookup"><span data-stu-id="30f68-142">Requirements</span></span>  
 <span data-ttu-id="30f68-143">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="30f68-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30f68-144">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="30f68-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30f68-145">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="30f68-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30f68-146">**.NET framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30f68-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30f68-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="30f68-147">See Also</span></span>  
 [<span data-ttu-id="30f68-148">GetRequestedRuntimeVersion 函数</span><span class="sxs-lookup"><span data-stu-id="30f68-148">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 [<span data-ttu-id="30f68-149">GetVersionFromProcess 函数</span><span class="sxs-lookup"><span data-stu-id="30f68-149">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 [<span data-ttu-id="30f68-150">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="30f68-150">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
