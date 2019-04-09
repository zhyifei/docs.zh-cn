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
ms.openlocfilehash: ccfe83707b6354c42a4c3c81e911918b2ea79ec4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108909"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="22ada-102">ICorDebugModule3::CreateReaderForInMemorySymbols 方法</span><span class="sxs-lookup"><span data-stu-id="22ada-102">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>
<span data-ttu-id="22ada-103">创建动态模块的调试符号读取器。</span><span class="sxs-lookup"><span data-stu-id="22ada-103">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22ada-104">语法</span><span class="sxs-lookup"><span data-stu-id="22ada-104">Syntax</span></span>  
  
```  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
## <a name="parameters"></a><span data-ttu-id="22ada-105">参数</span><span class="sxs-lookup"><span data-stu-id="22ada-105">Parameters</span></span>  
 <span data-ttu-id="22ada-106">riid</span><span class="sxs-lookup"><span data-stu-id="22ada-106">riid</span></span>  
 <span data-ttu-id="22ada-107">[in]若要返回的 COM 接口的 IID。</span><span class="sxs-lookup"><span data-stu-id="22ada-107">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="22ada-108">通常情况下，这是[ISymUnmanagedReader 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="22ada-108">Typically, this is an [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="22ada-109">ppObj</span><span class="sxs-lookup"><span data-stu-id="22ada-109">ppObj</span></span>  
 <span data-ttu-id="22ada-110">[out]指针到指向返回的接口。</span><span class="sxs-lookup"><span data-stu-id="22ada-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22ada-111">返回值</span><span class="sxs-lookup"><span data-stu-id="22ada-111">Return Value</span></span>  
 <span data-ttu-id="22ada-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="22ada-112">S_OK</span></span>  
 <span data-ttu-id="22ada-113">已成功创建读取器。</span><span class="sxs-lookup"><span data-stu-id="22ada-113">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="22ada-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="22ada-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="22ada-115">该模块不是一个内存中或动态模块。</span><span class="sxs-lookup"><span data-stu-id="22ada-115">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="22ada-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="22ada-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="22ada-117">符号未由应用程序提供或尚不可用。</span><span class="sxs-lookup"><span data-stu-id="22ada-117">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="22ada-118">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="22ada-118">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="22ada-119">无法创建读取器。</span><span class="sxs-lookup"><span data-stu-id="22ada-119">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22ada-120">备注</span><span class="sxs-lookup"><span data-stu-id="22ada-120">Remarks</span></span>  
 <span data-ttu-id="22ada-121">此方法也可以是用于创建符号读取器对象的内存中 （非动态） 模块，但只有后首次了可用的符号 (由[UpdateModuleSymbols 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md)回调)。</span><span class="sxs-lookup"><span data-stu-id="22ada-121">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="22ada-122">此方法返回的新实例，每次调用时 (如[CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance))。</span><span class="sxs-lookup"><span data-stu-id="22ada-122">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span></span> <span data-ttu-id="22ada-123">因此，调试器应缓存的结果，并请求一个新实例，仅当基础数据可能已更改时 (即，当[LoadClass 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)收到回调)。</span><span class="sxs-lookup"><span data-stu-id="22ada-123">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="22ada-124">动态模块之前已加载的第一个类型不具有任何可用的符号 (如所示[LoadClass 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)回调)。</span><span class="sxs-lookup"><span data-stu-id="22ada-124">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22ada-125">要求</span><span class="sxs-lookup"><span data-stu-id="22ada-125">Requirements</span></span>  
 <span data-ttu-id="22ada-126">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="22ada-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22ada-127">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22ada-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22ada-128">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22ada-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22ada-129">**.NET framework 版本：** 4.5，4，3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="22ada-129">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22ada-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="22ada-130">See also</span></span>

- [<span data-ttu-id="22ada-131">ICorDebugRemoteTarget 接口</span><span class="sxs-lookup"><span data-stu-id="22ada-131">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="22ada-132">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="22ada-132">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="22ada-133">调试接口</span><span class="sxs-lookup"><span data-stu-id="22ada-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
