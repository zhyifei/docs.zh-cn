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
ms.openlocfilehash: 2655151d34275b1b0fdc5d0903dd57fcea646014
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137306"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="efa65-102">ICorDebugModule3::CreateReaderForInMemorySymbols 方法</span><span class="sxs-lookup"><span data-stu-id="efa65-102">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>
<span data-ttu-id="efa65-103">为动态模块创建调试符号读取器。</span><span class="sxs-lookup"><span data-stu-id="efa65-103">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efa65-104">语法</span><span class="sxs-lookup"><span data-stu-id="efa65-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
## <a name="parameters"></a><span data-ttu-id="efa65-105">参数</span><span class="sxs-lookup"><span data-stu-id="efa65-105">Parameters</span></span>  
 <span data-ttu-id="efa65-106">riid</span><span class="sxs-lookup"><span data-stu-id="efa65-106">riid</span></span>  
 <span data-ttu-id="efa65-107">中要返回的 COM 接口的 IID。</span><span class="sxs-lookup"><span data-stu-id="efa65-107">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="efa65-108">通常，这是一个[ISymUnmanagedReader 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="efa65-108">Typically, this is an [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="efa65-109">ppObj</span><span class="sxs-lookup"><span data-stu-id="efa65-109">ppObj</span></span>  
 <span data-ttu-id="efa65-110">弄指向返回接口的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="efa65-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="efa65-111">返回值</span><span class="sxs-lookup"><span data-stu-id="efa65-111">Return Value</span></span>  
 <span data-ttu-id="efa65-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="efa65-112">S_OK</span></span>  
 <span data-ttu-id="efa65-113">已成功创建读取器。</span><span class="sxs-lookup"><span data-stu-id="efa65-113">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="efa65-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="efa65-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="efa65-115">该模块不是内存中或动态模块。</span><span class="sxs-lookup"><span data-stu-id="efa65-115">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="efa65-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="efa65-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="efa65-117">符号尚未由应用程序提供或尚未提供。</span><span class="sxs-lookup"><span data-stu-id="efa65-117">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="efa65-118">E_FAIL（或其他 E_ 返回代码）</span><span class="sxs-lookup"><span data-stu-id="efa65-118">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="efa65-119">无法创建读取器。</span><span class="sxs-lookup"><span data-stu-id="efa65-119">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efa65-120">备注</span><span class="sxs-lookup"><span data-stu-id="efa65-120">Remarks</span></span>  
 <span data-ttu-id="efa65-121">此方法还可用于为内存中（非动态）模块创建符号读取器对象，但仅在符号首次可用之后（由[UpdateModuleSymbols 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md)回调指示）。</span><span class="sxs-lookup"><span data-stu-id="efa65-121">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="efa65-122">此方法将在每次调用时返回一个新的读取器实例（例如[CComPtrBase：： CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)）。</span><span class="sxs-lookup"><span data-stu-id="efa65-122">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span></span> <span data-ttu-id="efa65-123">因此，调试器应缓存结果，并仅在基础数据可能已更改时（即，接收到[LoadClass 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)回调时）请求新的实例。</span><span class="sxs-lookup"><span data-stu-id="efa65-123">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="efa65-124">在加载第一个类型之前，动态模块没有可用的符号（如[LoadClass 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)回调所指示）。</span><span class="sxs-lookup"><span data-stu-id="efa65-124">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efa65-125">要求</span><span class="sxs-lookup"><span data-stu-id="efa65-125">Requirements</span></span>  
 <span data-ttu-id="efa65-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="efa65-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efa65-127">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="efa65-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="efa65-128">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efa65-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efa65-129">**.NET Framework 版本：** 4.5、4、3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="efa65-129">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efa65-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="efa65-130">See also</span></span>

- [<span data-ttu-id="efa65-131">ICorDebugRemoteTarget 接口</span><span class="sxs-lookup"><span data-stu-id="efa65-131">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="efa65-132">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="efa65-132">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="efa65-133">调试接口</span><span class="sxs-lookup"><span data-stu-id="efa65-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
