---
title: ICorDebugModule3::CreateReaderForInMemorySymbols 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule3.CreateReaderForInMemorySymbols
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3::CreateReaderForInMemorySymbols
helpviewer_keywords:
- CreateReaderForInMemorySymbols method, ICorDebugModule3 interface [.NET Framework debugging]
- ICorDebugModule3::CreateReaderForInMemorySymbols method [.NET Framework debugging]
ms.assetid: af317171-d66d-4114-89eb-063554c74940
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 76f7b53f800bc8c5c23f49a0781287a38bf8c959
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421511"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="6efbb-102">ICorDebugModule3::CreateReaderForInMemorySymbols 方法</span><span class="sxs-lookup"><span data-stu-id="6efbb-102">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>
<span data-ttu-id="6efbb-103">创建动态模块的调试符号读取器。</span><span class="sxs-lookup"><span data-stu-id="6efbb-103">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6efbb-104">语法</span><span class="sxs-lookup"><span data-stu-id="6efbb-104">Syntax</span></span>  
  
```  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6efbb-105">参数</span><span class="sxs-lookup"><span data-stu-id="6efbb-105">Parameters</span></span>  
 <span data-ttu-id="6efbb-106">riid</span><span class="sxs-lookup"><span data-stu-id="6efbb-106">riid</span></span>  
 <span data-ttu-id="6efbb-107">[in]若要返回 COM 接口的 IID。</span><span class="sxs-lookup"><span data-stu-id="6efbb-107">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="6efbb-108">通常，这是[ISymUnmanagedReader 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="6efbb-108">Typically, this is an [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="6efbb-109">ppObj</span><span class="sxs-lookup"><span data-stu-id="6efbb-109">ppObj</span></span>  
 <span data-ttu-id="6efbb-110">[out]指向返回的接口指针。</span><span class="sxs-lookup"><span data-stu-id="6efbb-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6efbb-111">返回值</span><span class="sxs-lookup"><span data-stu-id="6efbb-111">Return Value</span></span>  
 <span data-ttu-id="6efbb-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6efbb-112">S_OK</span></span>  
 <span data-ttu-id="6efbb-113">已成功创建读取器。</span><span class="sxs-lookup"><span data-stu-id="6efbb-113">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="6efbb-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="6efbb-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="6efbb-115">该模块不在内存或动态模块。</span><span class="sxs-lookup"><span data-stu-id="6efbb-115">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="6efbb-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6efbb-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="6efbb-117">符号尚未提供应用程序或尚不可用。</span><span class="sxs-lookup"><span data-stu-id="6efbb-117">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="6efbb-118">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="6efbb-118">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="6efbb-119">无法创建读取器。</span><span class="sxs-lookup"><span data-stu-id="6efbb-119">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6efbb-120">备注</span><span class="sxs-lookup"><span data-stu-id="6efbb-120">Remarks</span></span>  
 <span data-ttu-id="6efbb-121">此方法还可以用于创建符号读取器对象的内存中 （非动态） 模块，但仅限于后第一次的可用符号 (由[UpdateModuleSymbols 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md)回调)。</span><span class="sxs-lookup"><span data-stu-id="6efbb-121">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="6efbb-122">此方法返回一个新的读取器实例，每次调用 (如[CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6))。</span><span class="sxs-lookup"><span data-stu-id="6efbb-122">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)).</span></span> <span data-ttu-id="6efbb-123">因此，调试器应缓存结果，并且请求的新实例，仅在基础数据可能已更改时 (即，当[LoadClass 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)收到回调)。</span><span class="sxs-lookup"><span data-stu-id="6efbb-123">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="6efbb-124">动态模块没有可用的任何符号，直到已加载的第一个类型 (如所示[LoadClass 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)回调)。</span><span class="sxs-lookup"><span data-stu-id="6efbb-124">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6efbb-125">要求</span><span class="sxs-lookup"><span data-stu-id="6efbb-125">Requirements</span></span>  
 <span data-ttu-id="6efbb-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6efbb-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6efbb-127">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6efbb-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6efbb-128">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6efbb-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6efbb-129">**.NET framework 版本：** 4.5、 4、 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="6efbb-129">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6efbb-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="6efbb-130">See Also</span></span>  
 [<span data-ttu-id="6efbb-131">ICorDebugRemoteTarget 接口</span><span class="sxs-lookup"><span data-stu-id="6efbb-131">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="6efbb-132">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="6efbb-132">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="6efbb-133">调试接口</span><span class="sxs-lookup"><span data-stu-id="6efbb-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
