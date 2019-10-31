---
title: ICorDebugHeapEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum::Next
helpviewer_keywords:
- ICorDebugHeapEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 2221fd06-9e27-4113-972e-2530db8c3594
topic_type:
- apiref
ms.openlocfilehash: 1beb69bfaad9acb9c269ad8becb81bea64edb6a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138459"
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="f3303-102">ICorDebugHeapEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="f3303-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="f3303-103">获取指定数量的[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)实例，这些实例包含有关托管堆上的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="f3303-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3303-104">语法</span><span class="sxs-lookup"><span data-stu-id="f3303-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3303-105">参数</span><span class="sxs-lookup"><span data-stu-id="f3303-105">Parameters</span></span>  
 <span data-ttu-id="f3303-106">celt</span><span class="sxs-lookup"><span data-stu-id="f3303-106">celt</span></span>  
 <span data-ttu-id="f3303-107">[in] 要检索的对象数。</span><span class="sxs-lookup"><span data-stu-id="f3303-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="f3303-108">对象</span><span class="sxs-lookup"><span data-stu-id="f3303-108">objects</span></span>  
 <span data-ttu-id="f3303-109">弄指针数组，其中每个都指向一个[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)对象，该对象提供有关托管堆上的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="f3303-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="f3303-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="f3303-110">pceltFetched</span></span>  
 <span data-ttu-id="f3303-111">弄一个指针，指向 `objects`中实际返回的[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)对象的数目。</span><span class="sxs-lookup"><span data-stu-id="f3303-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="f3303-112">如果 `celt` 为 1，此值可能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="f3303-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3303-113">备注</span><span class="sxs-lookup"><span data-stu-id="f3303-113">Remarks</span></span>  
 <span data-ttu-id="f3303-114">`COR_HEAPOBJECT.type` 字段是嵌套的引用计数 COM 接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="f3303-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="f3303-115">此引用必须由 `ICorDebugHeapEnum::Next` 的调用方释放。</span><span class="sxs-lookup"><span data-stu-id="f3303-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3303-116">要求</span><span class="sxs-lookup"><span data-stu-id="f3303-116">Requirements</span></span>  
 <span data-ttu-id="f3303-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f3303-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3303-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3303-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3303-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3303-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3303-120">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3303-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3303-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="f3303-121">See also</span></span>

- [<span data-ttu-id="f3303-122">ICorDebugHeapEnum 接口</span><span class="sxs-lookup"><span data-stu-id="f3303-122">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)
- [<span data-ttu-id="f3303-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="f3303-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
