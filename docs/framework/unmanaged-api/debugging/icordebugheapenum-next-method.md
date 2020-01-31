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
ms.openlocfilehash: 2c84112984e9cb7dec2a492ac16af00e14770806
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782484"
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="db252-102">ICorDebugHeapEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="db252-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="db252-103">获取指定数量的[COR_HEAPOBJECT](cor-heapobject-structure.md)实例，这些实例包含有关托管堆上的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="db252-103">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db252-104">语法</span><span class="sxs-lookup"><span data-stu-id="db252-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db252-105">参数</span><span class="sxs-lookup"><span data-stu-id="db252-105">Parameters</span></span>  
 <span data-ttu-id="db252-106">celt</span><span class="sxs-lookup"><span data-stu-id="db252-106">celt</span></span>  
 <span data-ttu-id="db252-107">[in] 要检索的对象数。</span><span class="sxs-lookup"><span data-stu-id="db252-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="db252-108">对象执行）</span><span class="sxs-lookup"><span data-stu-id="db252-108">objects</span></span>  
 <span data-ttu-id="db252-109">弄指针数组，其中每个都指向一个[COR_HEAPOBJECT](cor-heapobject-structure.md)对象，该对象提供有关托管堆上的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="db252-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="db252-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="db252-110">pceltFetched</span></span>  
 <span data-ttu-id="db252-111">弄一个指针，指向 `objects`中实际返回的[COR_HEAPOBJECT](cor-heapobject-structure.md)对象的数量。</span><span class="sxs-lookup"><span data-stu-id="db252-111">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="db252-112">如果 `celt` 为 1，此值可能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="db252-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db252-113">备注</span><span class="sxs-lookup"><span data-stu-id="db252-113">Remarks</span></span>  
 <span data-ttu-id="db252-114">`COR_HEAPOBJECT.type` 字段是嵌套的引用计数 COM 接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="db252-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="db252-115">此引用必须由 `ICorDebugHeapEnum::Next` 的调用方释放。</span><span class="sxs-lookup"><span data-stu-id="db252-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db252-116">需求</span><span class="sxs-lookup"><span data-stu-id="db252-116">Requirements</span></span>  
 <span data-ttu-id="db252-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="db252-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db252-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db252-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db252-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db252-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db252-120">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db252-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db252-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db252-121">See also</span></span>

- [<span data-ttu-id="db252-122">ICorDebugHeapEnum 接口</span><span class="sxs-lookup"><span data-stu-id="db252-122">ICorDebugHeapEnum Interface</span></span>](icordebugheapenum-interface.md)
- [<span data-ttu-id="db252-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="db252-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
