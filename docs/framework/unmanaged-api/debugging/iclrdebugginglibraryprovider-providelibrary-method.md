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
ms.openlocfilehash: a1b02bb74a61e64a3ed9875fcf88e018de9f6317
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70041439"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a><span data-ttu-id="d6823-102">ICLRDebuggingLibraryProvider::ProvideLibrary 方法</span><span class="sxs-lookup"><span data-stu-id="d6823-102">ICLRDebuggingLibraryProvider::ProvideLibrary Method</span></span>

<span data-ttu-id="d6823-103">获取一个库提供程序回调接口, 该接口允许根据需要定位和加载特定于公共语言运行时 (CLR) 版本的调试库。</span><span class="sxs-lookup"><span data-stu-id="d6823-103">Gets a library provider callback interface that allows common language runtime (CLR) version-specific debugging libraries to be located and loaded on demand.</span></span>

## <a name="syntax"></a><span data-ttu-id="d6823-104">语法</span><span class="sxs-lookup"><span data-stu-id="d6823-104">Syntax</span></span>

```cpp
HRESULT ProvideLibrary(
     [in] const WCHAR* pwszFileName,
     [in] DWORD dwTimestamp,
     [in] DWORD dwSizeOfImage,
     [out] HMODULE* hModule);
```

## <a name="parameters"></a><span data-ttu-id="d6823-105">参数</span><span class="sxs-lookup"><span data-stu-id="d6823-105">Parameters</span></span>

`pwszFilename` \
<span data-ttu-id="d6823-106">中请求的模块的名称。</span><span class="sxs-lookup"><span data-stu-id="d6823-106">[in] The name of the module being requested.</span></span>

`dwTimestamp` \
<span data-ttu-id="d6823-107">中存储在 PE 文件的 COFF 文件头中的日期时间戳。</span><span class="sxs-lookup"><span data-stu-id="d6823-107">[in] The date time stamp stored in the COFF file header of PE files.</span></span>

`pLibraryProvider` \
<span data-ttu-id="d6823-108">中存储在 PE 文件的 COFF 可选文件头中的字段。`SizeOfImage`</span><span class="sxs-lookup"><span data-stu-id="d6823-108">[in] The `SizeOfImage` field stored in the COFF optional file header of PE files.</span></span>

`hModule` \
<span data-ttu-id="d6823-109">弄请求的模块的句柄。</span><span class="sxs-lookup"><span data-stu-id="d6823-109">[out] The handle to the requested module.</span></span>

## <a name="return-value"></a><span data-ttu-id="d6823-110">返回值</span><span class="sxs-lookup"><span data-stu-id="d6823-110">Return Value</span></span>

<span data-ttu-id="d6823-111">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="d6823-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>

|<span data-ttu-id="d6823-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d6823-112">HRESULT</span></span>|<span data-ttu-id="d6823-113">描述</span><span class="sxs-lookup"><span data-stu-id="d6823-113">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="d6823-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d6823-114">S_OK</span></span>|<span data-ttu-id="d6823-115">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="d6823-115">The method completed successfully.</span></span>|

## <a name="exceptions"></a><span data-ttu-id="d6823-116">Exceptions</span><span class="sxs-lookup"><span data-stu-id="d6823-116">Exceptions</span></span>

## <a name="remarks"></a><span data-ttu-id="d6823-117">备注</span><span class="sxs-lookup"><span data-stu-id="d6823-117">Remarks</span></span>

<span data-ttu-id="d6823-118">`ProvideLibrary`允许调试器提供调试特定 CLR 文件 (如 mscordbi.dll 和 mscordacwks) 所需的模块。</span><span class="sxs-lookup"><span data-stu-id="d6823-118">`ProvideLibrary` allows the debugger to provide modules that are needed for debugging specific CLR files such as mscordbi.dll and mscordacwks.dll.</span></span> <span data-ttu-id="d6823-119">模块句柄必须保持有效, 直到对[ICLRDebugging:: CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)方法的调用指示它们可能已被释放, 此时调用方负责释放句柄。</span><span class="sxs-lookup"><span data-stu-id="d6823-119">The module handles have to remain valid until a call to the [ICLRDebugging::CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) method indicates that they may be freed, at which point it is the caller’s responsibility to free the handles.</span></span>

<span data-ttu-id="d6823-120">调试器可以使用任何可用的方法来查找或获取调试模块。</span><span class="sxs-lookup"><span data-stu-id="d6823-120">The debugger may use any available means to locate or procure the debugging module.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d6823-121">此功能允许 API 调用方提供包含可执行文件的模块, 并提供可能的恶意代码。</span><span class="sxs-lookup"><span data-stu-id="d6823-121">This feature allows the API caller to provide modules that contain executable, and possibly malicious, code.</span></span> <span data-ttu-id="d6823-122">作为一种安全预防措施, 调用方不`ProvideLibrary`应使用分发任何不愿意自行执行的代码。</span><span class="sxs-lookup"><span data-stu-id="d6823-122">As a security precaution, the caller should not use `ProvideLibrary` to distribute any code that it is not willing to execute itself.</span></span>
>
> <span data-ttu-id="d6823-123">如果在已发布的库 (如 mscordbi.dll 或 mscordacwks) 中发现了严重的安全问题, 则可以对填充程序进行修补, 以识别文件的不正确版本。</span><span class="sxs-lookup"><span data-stu-id="d6823-123">If a serious security issue is discovered in an already released library, such as mscordbi.dll or mscordacwks.dll, the shim can be patched to recognize the bad versions of the files.</span></span> <span data-ttu-id="d6823-124">然后, 填充程序可以为文件的已修补版本发出请求, 并拒绝不正确的版本 (如果提供这些文件以响应任何请求)。</span><span class="sxs-lookup"><span data-stu-id="d6823-124">The shim can then issue requests for the patched versions of the files and reject the bad versions if they are provided in response to any request.</span></span> <span data-ttu-id="d6823-125">仅当用户已修补新的填充码版本时, 才会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="d6823-125">This can occur only if the user has patched to a new version of the shim.</span></span> <span data-ttu-id="d6823-126">未修补的版本将仍然容易受到攻击。</span><span class="sxs-lookup"><span data-stu-id="d6823-126">Unpatched versions will remain vulnerable.</span></span>

## <a name="requirements"></a><span data-ttu-id="d6823-127">要求</span><span class="sxs-lookup"><span data-stu-id="d6823-127">Requirements</span></span>

<span data-ttu-id="d6823-128">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d6823-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="d6823-129">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="d6823-129">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="d6823-130">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6823-130">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="d6823-131">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6823-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d6823-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6823-132">See also</span></span>

- [<span data-ttu-id="d6823-133">调试接口</span><span class="sxs-lookup"><span data-stu-id="d6823-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d6823-134">调试</span><span class="sxs-lookup"><span data-stu-id="d6823-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
