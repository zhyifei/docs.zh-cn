---
title: "ICLRDebuggingLibraryProvider::ProvideLibrary 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebuggingLibraryProvider.ProvideLibrary Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDebuggingLibraryProvider::ProvideLibrary
helpviewer_keywords:
- ProvideLibrary method [.NET Framework debugging]
- ICLRDebuggingLibraryProvider::ProvideLibrary method [.NET Framework debugging]
ms.assetid: 86f06245-9517-49be-8d8c-ca5deaf34c02
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d3a34579787e976022ffa8caf7c29d8a565a7c73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a><span data-ttu-id="91eae-102">ICLRDebuggingLibraryProvider::ProvideLibrary 方法</span><span class="sxs-lookup"><span data-stu-id="91eae-102">ICLRDebuggingLibraryProvider::ProvideLibrary Method</span></span>
<span data-ttu-id="91eae-103">获取一个库提供程序允许公共语言运行时 (CLR) 特定于版本的调试库需要定位和加载上的回调接口。</span><span class="sxs-lookup"><span data-stu-id="91eae-103">Gets a library provider callback interface that allows common language runtime (CLR) version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91eae-104">语法</span><span class="sxs-lookup"><span data-stu-id="91eae-104">Syntax</span></span>  
  
```  
HRESULT ProvideLibrary(  
     [in] const WCHAR* pwszFileName,  
     [in] DWORD dwTimestamp,  
     [in] DWORD dwSizeOfImage,  
     [out] HMODULE* hModule);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="91eae-105">参数</span><span class="sxs-lookup"><span data-stu-id="91eae-105">Parameters</span></span>  
 `pwszFilename`  
 <span data-ttu-id="91eae-106">[in]请求的模块的名称。</span><span class="sxs-lookup"><span data-stu-id="91eae-106">[in] The name of the module being requested .</span></span>  
  
 `dwTimestamp`  
 <span data-ttu-id="91eae-107">[in]COFF 文件头的 PE 文件中存储日期时间戳。</span><span class="sxs-lookup"><span data-stu-id="91eae-107">[in] The date time stamp stored in the COFF file header of PE files.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="91eae-108">[in]`SizeOfImage` COFF 可选文件头的 PE 文件中存储的字段。</span><span class="sxs-lookup"><span data-stu-id="91eae-108">[in] The `SizeOfImage` field stored in the COFF optional file header of PE files.</span></span>  
  
 `hModule`  
 <span data-ttu-id="91eae-109">[out]请求的模块句柄。</span><span class="sxs-lookup"><span data-stu-id="91eae-109">[out] The handle to the requested module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91eae-110">返回值</span><span class="sxs-lookup"><span data-stu-id="91eae-110">Return Value</span></span>  
 <span data-ttu-id="91eae-111">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="91eae-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="91eae-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="91eae-112">HRESULT</span></span>|<span data-ttu-id="91eae-113">描述</span><span class="sxs-lookup"><span data-stu-id="91eae-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="91eae-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="91eae-114">S_OK</span></span>|<span data-ttu-id="91eae-115">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="91eae-115">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="91eae-116">异常</span><span class="sxs-lookup"><span data-stu-id="91eae-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91eae-117">备注</span><span class="sxs-lookup"><span data-stu-id="91eae-117">Remarks</span></span>  
 <span data-ttu-id="91eae-118">`ProvideLibrary`使调试器能够提供所需的调试特定 CLR 文件，如 mscordbi.dll 和 mscordacwks.dll 的模块。</span><span class="sxs-lookup"><span data-stu-id="91eae-118">`ProvideLibrary` allows the debugger to provide modules that are needed for debugging specific CLR files such as mscordbi.dll and mscordacwks.dll.</span></span> <span data-ttu-id="91eae-119">模块句柄已保留，直到调用有效[iclrdebugging:: Canunloadnow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)方法指示它们可能会被释放，此时它是调用方负责释放句柄。</span><span class="sxs-lookup"><span data-stu-id="91eae-119">The module handles have to remain valid until a call to the [ICLRDebugging::CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) method indicates that they may be freed, at which point it is the caller’s responsibility to free the handles.</span></span>  
  
 <span data-ttu-id="91eae-120">调试器可以使用任何可用的方式来定位或获得调试模块。</span><span class="sxs-lookup"><span data-stu-id="91eae-120">The debugger may use any available means to locate or procure the debugging module.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="91eae-121">此功能允许 API 调用方提供包含可执行文件，并可能是恶意代码的模块。</span><span class="sxs-lookup"><span data-stu-id="91eae-121">This feature allows the API caller to provide modules that contain executable, and possibly malicious, code.</span></span> <span data-ttu-id="91eae-122">作为安全措施，调用方不应使用`ProvideLibrary`来分发不愿意本身执行任何代码。</span><span class="sxs-lookup"><span data-stu-id="91eae-122">As a security precaution, the caller should not use `ProvideLibrary` to distribute any code that it is not willing to execute itself.</span></span>  
>   
>  <span data-ttu-id="91eae-123">如果在已发布的库中，如 mscordbi.dll 或 mscordacwks.dll，发现了严重的安全问题填充程序可以进行修补，以识别错误版本的文件。</span><span class="sxs-lookup"><span data-stu-id="91eae-123">If a serious security issue is discovered in an already released library, such as mscordbi.dll or mscordacwks.dll, the shim can be patched to recognize the bad versions of the files.</span></span> <span data-ttu-id="91eae-124">然后，填充程序可以发出修补版本的文件的请求并拒绝不适用的版本，如果对任何请求响应中提供。</span><span class="sxs-lookup"><span data-stu-id="91eae-124">The shim can then issue requests for the patched versions of the files and reject the bad versions if they are provided in response to any request.</span></span> <span data-ttu-id="91eae-125">仅当用户具有修补到该填充程序的新版本时，才会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="91eae-125">This can occur only if the user has patched to a new version of the shim.</span></span> <span data-ttu-id="91eae-126">未安装修补程序的版本仍易受攻击。</span><span class="sxs-lookup"><span data-stu-id="91eae-126">Unpatched versions will remain vulnerable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91eae-127">要求</span><span class="sxs-lookup"><span data-stu-id="91eae-127">Requirements</span></span>  
 <span data-ttu-id="91eae-128">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="91eae-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91eae-129">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91eae-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91eae-130">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91eae-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91eae-131">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91eae-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91eae-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91eae-132">See Also</span></span>  
 [<span data-ttu-id="91eae-133">调试接口</span><span class="sxs-lookup"><span data-stu-id="91eae-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="91eae-134">调试</span><span class="sxs-lookup"><span data-stu-id="91eae-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
