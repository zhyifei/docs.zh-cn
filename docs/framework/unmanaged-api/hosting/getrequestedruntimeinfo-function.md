---
title: GetRequestedRuntimeInfo 函数
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeInfo
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeInfo
helpviewer_keywords:
- GetRequestedRuntimeInfo function [.NET Framework hosting]
ms.assetid: 0dfd7cdc-c116-4e25-b56a-ac7b0378c942
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1290aa864a3f65e549bc26173dcd23648b8dee90
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074880"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="2fc63-102">GetRequestedRuntimeInfo 函数</span><span class="sxs-lookup"><span data-stu-id="2fc63-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="2fc63-103">获取有关公共语言运行时 (CLR) 应用程序请求的版本和目录信息。</span><span class="sxs-lookup"><span data-stu-id="2fc63-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="2fc63-104">此函数中不推荐[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2fc63-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fc63-105">语法</span><span class="sxs-lookup"><span data-stu-id="2fc63-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="2fc63-106">参数</span><span class="sxs-lookup"><span data-stu-id="2fc63-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="2fc63-107">[in]应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="2fc63-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="2fc63-108">[in]指定运行时的版本号的字符串。</span><span class="sxs-lookup"><span data-stu-id="2fc63-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="2fc63-109">[in]与之关联的配置文件的名称`pExe`。</span><span class="sxs-lookup"><span data-stu-id="2fc63-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="2fc63-110">[in]一个或多个[STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)枚举值。</span><span class="sxs-lookup"><span data-stu-id="2fc63-110">[in] One or more of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="2fc63-111">[in]一个或多个[RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)枚举值。</span><span class="sxs-lookup"><span data-stu-id="2fc63-111">[in] One or more of the [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="2fc63-112">[out]包含成功完成后运行时的目录路径的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2fc63-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="2fc63-113">[in]目录缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="2fc63-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="2fc63-114">[out]指向的目录路径字符串长度的指针。</span><span class="sxs-lookup"><span data-stu-id="2fc63-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="2fc63-115">[out]包含成功完成后运行时的版本号的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2fc63-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="2fc63-116">[in]版本字符串缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="2fc63-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="2fc63-117">[out]指向版本字符串的长度的指针。</span><span class="sxs-lookup"><span data-stu-id="2fc63-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2fc63-118">返回值</span><span class="sxs-lookup"><span data-stu-id="2fc63-118">Return Value</span></span>  
 <span data-ttu-id="2fc63-119">此方法返回标准的组件对象模型 (COM) 错误代码，定义在 WinError.h，除了以下值。</span><span class="sxs-lookup"><span data-stu-id="2fc63-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="2fc63-120">返回代码</span><span class="sxs-lookup"><span data-stu-id="2fc63-120">Return code</span></span>|<span data-ttu-id="2fc63-121">描述</span><span class="sxs-lookup"><span data-stu-id="2fc63-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="2fc63-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="2fc63-122">S_OK</span></span>|<span data-ttu-id="2fc63-123">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="2fc63-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="2fc63-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="2fc63-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="2fc63-125">目录缓冲区不足够空间来存储的目录路径。</span><span class="sxs-lookup"><span data-stu-id="2fc63-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="2fc63-126">- 或 -</span><span class="sxs-lookup"><span data-stu-id="2fc63-126">- or -</span></span><br /><br /> <span data-ttu-id="2fc63-127">版本缓冲区不足够空间来存储的版本字符串。</span><span class="sxs-lookup"><span data-stu-id="2fc63-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fc63-128">备注</span><span class="sxs-lookup"><span data-stu-id="2fc63-128">Remarks</span></span>  
 <span data-ttu-id="2fc63-129">`GetRequestedRuntimeInfo`方法返回运行时加载到进程，不一定是最新版本的计算机上安装的版本信息。</span><span class="sxs-lookup"><span data-stu-id="2fc63-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="2fc63-130">在.NET Framework 2.0 版中，可以获取有关最新安装的版本信息，通过使用`GetRequestedRuntimeInfo`方法，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2fc63-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
-   <span data-ttu-id="2fc63-131">指定`pExe`， `pwszVersion`，和`pConfigurationFile`参数为 null。</span><span class="sxs-lookup"><span data-stu-id="2fc63-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
-   <span data-ttu-id="2fc63-132">指定在 RUNTIME_INFO_UPGRADE_VERSION 标志`RUNTIME_INFO_FLAGS`枚举`runtimeInfoFlags`参数。</span><span class="sxs-lookup"><span data-stu-id="2fc63-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="2fc63-133">`GetRequestedRuntimeInfo`方法不在以下情况下返回的最新的 CLR 版本：</span><span class="sxs-lookup"><span data-stu-id="2fc63-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
-   <span data-ttu-id="2fc63-134">指定正在加载特定的 CLR 版本应用程序配置文件存在。</span><span class="sxs-lookup"><span data-stu-id="2fc63-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="2fc63-135">请注意，.NET Framework 将使用配置文件，即使您指定为 null`pConfigurationFile`参数。</span><span class="sxs-lookup"><span data-stu-id="2fc63-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
-   <span data-ttu-id="2fc63-136">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)指定较早的 CLR 版本调用方法。</span><span class="sxs-lookup"><span data-stu-id="2fc63-136">The [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
-   <span data-ttu-id="2fc63-137">为较早的 CLR 版本编译的应用程序当前正在运行。</span><span class="sxs-lookup"><span data-stu-id="2fc63-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="2fc63-138">有关`runtimeInfoFlags`参数，可以指定的体系结构常量之一`RUNTIME_INFO_FLAGS`枚举一次：</span><span class="sxs-lookup"><span data-stu-id="2fc63-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
-   <span data-ttu-id="2fc63-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="2fc63-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
-   <span data-ttu-id="2fc63-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="2fc63-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
-   <span data-ttu-id="2fc63-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="2fc63-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fc63-142">要求</span><span class="sxs-lookup"><span data-stu-id="2fc63-142">Requirements</span></span>  
 <span data-ttu-id="2fc63-143">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2fc63-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fc63-144">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2fc63-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2fc63-145">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2fc63-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2fc63-146">**.NET Framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fc63-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fc63-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="2fc63-147">See also</span></span>

- [<span data-ttu-id="2fc63-148">GetRequestedRuntimeVersion 函数</span><span class="sxs-lookup"><span data-stu-id="2fc63-148">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="2fc63-149">GetVersionFromProcess 函数</span><span class="sxs-lookup"><span data-stu-id="2fc63-149">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="2fc63-150">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="2fc63-150">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
