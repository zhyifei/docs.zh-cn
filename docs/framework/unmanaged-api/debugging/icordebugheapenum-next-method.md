---
title: "ICorDebugHeapEnum::Next 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapEnum::Next
helpviewer_keywords:
- ICorDebugHeapEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 2221fd06-9e27-4113-972e-2530db8c3594
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a15637f925401f23f9da34e33583c9bc5c014dd3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="043f3-102">ICorDebugHeapEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="043f3-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="043f3-103">获取指定的数目的[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)包含托管堆上对象的信息的实例。</span><span class="sxs-lookup"><span data-stu-id="043f3-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="043f3-104">语法</span><span class="sxs-lookup"><span data-stu-id="043f3-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],   
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="043f3-105">参数</span><span class="sxs-lookup"><span data-stu-id="043f3-105">Parameters</span></span>  
 <span data-ttu-id="043f3-106">celt</span><span class="sxs-lookup"><span data-stu-id="043f3-106">celt</span></span>  
 <span data-ttu-id="043f3-107">[in] 要检索的对象数。</span><span class="sxs-lookup"><span data-stu-id="043f3-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="043f3-108">对象</span><span class="sxs-lookup"><span data-stu-id="043f3-108">objects</span></span>  
 <span data-ttu-id="043f3-109">[out]一个指针，其中每个指向数组[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)提供托管堆的对象有关的信息的对象。</span><span class="sxs-lookup"><span data-stu-id="043f3-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="043f3-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="043f3-110">pceltFetched</span></span>  
 <span data-ttu-id="043f3-111">[out]指向数[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)中实际返回的对象`objects`。</span><span class="sxs-lookup"><span data-stu-id="043f3-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="043f3-112">如果 `celt` 为 1，此值可能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="043f3-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="043f3-113">备注</span><span class="sxs-lookup"><span data-stu-id="043f3-113">Remarks</span></span>  
 <span data-ttu-id="043f3-114">`COR_HEAPOBJECT.type` 字段是嵌套的引用计数 COM 接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="043f3-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="043f3-115">此引用必须由 `ICorDebugHeapEnum::Next` 的调用方释放。</span><span class="sxs-lookup"><span data-stu-id="043f3-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="043f3-116">要求</span><span class="sxs-lookup"><span data-stu-id="043f3-116">Requirements</span></span>  
 <span data-ttu-id="043f3-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="043f3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="043f3-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="043f3-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="043f3-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="043f3-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="043f3-120">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="043f3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="043f3-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="043f3-121">See Also</span></span>  
 [<span data-ttu-id="043f3-122">ICorDebugHeapEnum 接口</span><span class="sxs-lookup"><span data-stu-id="043f3-122">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
 [<span data-ttu-id="043f3-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="043f3-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
