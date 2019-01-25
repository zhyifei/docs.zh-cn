---
title: ICLRDebuggingLibraryProvider::ProvideLibrary 方法
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider.ProvideLibrary Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider::ProvideLibrary
helpviewer_keywords:
- ProvideLibrary method [.NET Framework debugging]
- ICLRDebuggingLibraryProvider::ProvideLibrary method [.NET Framework debugging]
ms.assetid: 86f06245-9517-49be-8d8c-ca5deaf34c02
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9cac9e00c8cb6a13e2acc62b5f314b7bc0cf9e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629109"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a><span data-ttu-id="2d66e-102">ICLRDebuggingLibraryProvider::ProvideLibrary 方法</span><span class="sxs-lookup"><span data-stu-id="2d66e-102">ICLRDebuggingLibraryProvider::ProvideLibrary Method</span></span>
<span data-ttu-id="2d66e-103">获取一个库提供程序允许公共语言运行时 (CLR) 特定于版本的调试库定位和加载根据需要的回调接口。</span><span class="sxs-lookup"><span data-stu-id="2d66e-103">Gets a library provider callback interface that allows common language runtime (CLR) version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d66e-104">语法</span><span class="sxs-lookup"><span data-stu-id="2d66e-104">Syntax</span></span>  
  
```  
HRESULT ProvideLibrary(  
     [in] const WCHAR* pwszFileName,  
     [in] DWORD dwTimestamp,  
     [in] DWORD dwSizeOfImage,  
     [out] HMODULE* hModule);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2d66e-105">参数</span><span class="sxs-lookup"><span data-stu-id="2d66e-105">Parameters</span></span>  
 `pwszFilename`  
 <span data-ttu-id="2d66e-106">[in]请求的模块的名称。</span><span class="sxs-lookup"><span data-stu-id="2d66e-106">[in] The name of the module being requested .</span></span>  
  
 `dwTimestamp`  
 <span data-ttu-id="2d66e-107">[in]日期时间戳存储在 PE 文件的 COFF 文件标头中。</span><span class="sxs-lookup"><span data-stu-id="2d66e-107">[in] The date time stamp stored in the COFF file header of PE files.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="2d66e-108">[in]`SizeOfImage` COFF 可选文件标头的 PE 文件中存储的字段。</span><span class="sxs-lookup"><span data-stu-id="2d66e-108">[in] The `SizeOfImage` field stored in the COFF optional file header of PE files.</span></span>  
  
 `hModule`  
 <span data-ttu-id="2d66e-109">[out]请求的模块句柄。</span><span class="sxs-lookup"><span data-stu-id="2d66e-109">[out] The handle to the requested module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d66e-110">返回值</span><span class="sxs-lookup"><span data-stu-id="2d66e-110">Return Value</span></span>  
 <span data-ttu-id="2d66e-111">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="2d66e-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2d66e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2d66e-112">HRESULT</span></span>|<span data-ttu-id="2d66e-113">描述</span><span class="sxs-lookup"><span data-stu-id="2d66e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2d66e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="2d66e-114">S_OK</span></span>|<span data-ttu-id="2d66e-115">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="2d66e-115">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="2d66e-116">Exceptions</span><span class="sxs-lookup"><span data-stu-id="2d66e-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d66e-117">备注</span><span class="sxs-lookup"><span data-stu-id="2d66e-117">Remarks</span></span>  
 <span data-ttu-id="2d66e-118">`ProvideLibrary` 使调试器能够提供所需的调试特定 CLR 文件，如 mscordbi.dll 和 mscordacwks.dll 的模块。</span><span class="sxs-lookup"><span data-stu-id="2d66e-118">`ProvideLibrary` allows the debugger to provide modules that are needed for debugging specific CLR files such as mscordbi.dll and mscordacwks.dll.</span></span> <span data-ttu-id="2d66e-119">模块句柄必须在调用之前保持有效[iclrdebugging:: Canunloadnow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)方法指示，它们可能会被释放，此时它是调用方负责释放句柄。</span><span class="sxs-lookup"><span data-stu-id="2d66e-119">The module handles have to remain valid until a call to the [ICLRDebugging::CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) method indicates that they may be freed, at which point it is the caller’s responsibility to free the handles.</span></span>  
  
 <span data-ttu-id="2d66e-120">调试器可能会使用任何可用的方式来定位或获得调试模块。</span><span class="sxs-lookup"><span data-stu-id="2d66e-120">The debugger may use any available means to locate or procure the debugging module.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2d66e-121">此功能允许 API 调用方提供的包含可执行文件，并可能是恶意的代码模块。</span><span class="sxs-lookup"><span data-stu-id="2d66e-121">This feature allows the API caller to provide modules that contain executable, and possibly malicious, code.</span></span> <span data-ttu-id="2d66e-122">作为安全预防措施，调用方不应使用`ProvideLibrary`分发不愿意执行本身的任何代码。</span><span class="sxs-lookup"><span data-stu-id="2d66e-122">As a security precaution, the caller should not use `ProvideLibrary` to distribute any code that it is not willing to execute itself.</span></span>  
>   
>  <span data-ttu-id="2d66e-123">如果在已发布的库中，如 mscordbi.dll 或 mscordacwks.dll，发现了严重的安全问题可以修补该填充程序来识别错误版本的文件。</span><span class="sxs-lookup"><span data-stu-id="2d66e-123">If a serious security issue is discovered in an already released library, such as mscordbi.dll or mscordacwks.dll, the shim can be patched to recognize the bad versions of the files.</span></span> <span data-ttu-id="2d66e-124">填充程序可以然后修补版本的文件中的发出请求并拒绝不适用的版本，如果响应任何请求中提供了它们。</span><span class="sxs-lookup"><span data-stu-id="2d66e-124">The shim can then issue requests for the patched versions of the files and reject the bad versions if they are provided in response to any request.</span></span> <span data-ttu-id="2d66e-125">这可能仅当用户已修补到填充程序的新版本。</span><span class="sxs-lookup"><span data-stu-id="2d66e-125">This can occur only if the user has patched to a new version of the shim.</span></span> <span data-ttu-id="2d66e-126">未安装修补程序的版本仍易受攻击。</span><span class="sxs-lookup"><span data-stu-id="2d66e-126">Unpatched versions will remain vulnerable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d66e-127">要求</span><span class="sxs-lookup"><span data-stu-id="2d66e-127">Requirements</span></span>  
 <span data-ttu-id="2d66e-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2d66e-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d66e-129">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d66e-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d66e-130">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d66e-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d66e-131">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d66e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d66e-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d66e-132">See also</span></span>
- [<span data-ttu-id="2d66e-133">调试接口</span><span class="sxs-lookup"><span data-stu-id="2d66e-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2d66e-134">调试</span><span class="sxs-lookup"><span data-stu-id="2d66e-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
