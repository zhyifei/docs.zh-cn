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
ms.openlocfilehash: db721e1ef774c87de0fa7da178463d832a3da756
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178150"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="cca2e-102">GetRequestedRuntimeInfo 函数</span><span class="sxs-lookup"><span data-stu-id="cca2e-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="cca2e-103">获取有关应用程序请求的通用语言运行时 （CLR） 的版本和目录信息。</span><span class="sxs-lookup"><span data-stu-id="cca2e-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="cca2e-104">此功能已在 .NET 框架 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="cca2e-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cca2e-105">语法</span><span class="sxs-lookup"><span data-stu-id="cca2e-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="cca2e-106">parameters</span><span class="sxs-lookup"><span data-stu-id="cca2e-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="cca2e-107">[在]应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="cca2e-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="cca2e-108">[在]指定运行时的版本号的字符串。</span><span class="sxs-lookup"><span data-stu-id="cca2e-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="cca2e-109">[在]与`pExe`关联的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="cca2e-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="cca2e-110">[在]一个或多个[STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)枚举值。</span><span class="sxs-lookup"><span data-stu-id="cca2e-110">[in] One or more of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="cca2e-111">[在]一个或多个[RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md)枚举值。</span><span class="sxs-lookup"><span data-stu-id="cca2e-111">[in] One or more of the [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="cca2e-112">[出]一个缓冲区，在成功完成时包含到运行时的目录路径。</span><span class="sxs-lookup"><span data-stu-id="cca2e-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="cca2e-113">[在]目录缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="cca2e-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="cca2e-114">[出]指向目录路径字符串长度的指针。</span><span class="sxs-lookup"><span data-stu-id="cca2e-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="cca2e-115">[出]一个缓冲区，在成功完成时包含运行时的版本号。</span><span class="sxs-lookup"><span data-stu-id="cca2e-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="cca2e-116">[在]版本字符串缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="cca2e-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="cca2e-117">[出]指向版本字符串长度的指针。</span><span class="sxs-lookup"><span data-stu-id="cca2e-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cca2e-118">返回值</span><span class="sxs-lookup"><span data-stu-id="cca2e-118">Return Value</span></span>  
 <span data-ttu-id="cca2e-119">此方法返回 WinError.h 中定义的标准组件对象模型 （COM） 错误代码，以及以下值。</span><span class="sxs-lookup"><span data-stu-id="cca2e-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="cca2e-120">返回代码</span><span class="sxs-lookup"><span data-stu-id="cca2e-120">Return code</span></span>|<span data-ttu-id="cca2e-121">说明</span><span class="sxs-lookup"><span data-stu-id="cca2e-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="cca2e-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="cca2e-122">S_OK</span></span>|<span data-ttu-id="cca2e-123">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="cca2e-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="cca2e-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="cca2e-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="cca2e-125">目录缓冲区不够大，无法存储目录路径。</span><span class="sxs-lookup"><span data-stu-id="cca2e-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="cca2e-126">- 或 -</span><span class="sxs-lookup"><span data-stu-id="cca2e-126">- or -</span></span><br /><br /> <span data-ttu-id="cca2e-127">版本缓冲区不够大，无法存储版本字符串。</span><span class="sxs-lookup"><span data-stu-id="cca2e-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cca2e-128">备注</span><span class="sxs-lookup"><span data-stu-id="cca2e-128">Remarks</span></span>  
 <span data-ttu-id="cca2e-129">该方法`GetRequestedRuntimeInfo`返回有关加载到进程中的版本的运行时信息，这不一定是计算机上安装的最新版本。</span><span class="sxs-lookup"><span data-stu-id="cca2e-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="cca2e-130">在 .NET 框架版本 2.0 中，可以使用如下`GetRequestedRuntimeInfo`方法获取有关最新安装版本的信息：</span><span class="sxs-lookup"><span data-stu-id="cca2e-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
- <span data-ttu-id="cca2e-131">将`pExe`和`pwszVersion`参数`pConfigurationFile`指定为 null。</span><span class="sxs-lookup"><span data-stu-id="cca2e-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
- <span data-ttu-id="cca2e-132">在`runtimeInfoFlags`参数的枚举中`RUNTIME_INFO_FLAGS`指定RUNTIME_INFO_UPGRADE_VERSION标志。</span><span class="sxs-lookup"><span data-stu-id="cca2e-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="cca2e-133">在`GetRequestedRuntimeInfo`以下情况下，该方法不会返回最新的 CLR 版本：</span><span class="sxs-lookup"><span data-stu-id="cca2e-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
- <span data-ttu-id="cca2e-134">存在指定加载特定 CLR 版本的应用程序配置文件。</span><span class="sxs-lookup"><span data-stu-id="cca2e-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="cca2e-135">请注意，即使为`pConfigurationFile`参数指定 null，.NET 框架也会使用配置文件。</span><span class="sxs-lookup"><span data-stu-id="cca2e-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
- <span data-ttu-id="cca2e-136">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)方法称为指定较早的 CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="cca2e-136">The [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
- <span data-ttu-id="cca2e-137">为早期 CLR 版本编译的应用程序当前正在运行。</span><span class="sxs-lookup"><span data-stu-id="cca2e-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="cca2e-138">对于参数`runtimeInfoFlags`，一次只能指定枚举的`RUNTIME_INFO_FLAGS`一个体系结构常量：</span><span class="sxs-lookup"><span data-stu-id="cca2e-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
- <span data-ttu-id="cca2e-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="cca2e-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="cca2e-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="cca2e-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="cca2e-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="cca2e-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cca2e-142">要求</span><span class="sxs-lookup"><span data-stu-id="cca2e-142">Requirements</span></span>  
 <span data-ttu-id="cca2e-143">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cca2e-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cca2e-144">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cca2e-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cca2e-145">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cca2e-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cca2e-146">**.NET 框架版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cca2e-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cca2e-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cca2e-147">See also</span></span>

- [<span data-ttu-id="cca2e-148">GetRequestedRuntimeVersion 函数</span><span class="sxs-lookup"><span data-stu-id="cca2e-148">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="cca2e-149">GetVersionFromProcess 函数</span><span class="sxs-lookup"><span data-stu-id="cca2e-149">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="cca2e-150">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="cca2e-150">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
