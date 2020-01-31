---
title: ICorDebugHeapSegmentEnum::Next 方法
ms.date: 03/30/2017
api_name:
- Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum::Next
helpviewer_keywords:
- ICorDebugHeapSegmentEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 51625fd0-7399-49c7-b22b-5dfb05451fe6
topic_type:
- apiref
ms.openlocfilehash: 89ce4eafa46be3e9ba7cdb06884034a521e43bca
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777539"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="44877-102">ICorDebugHeapSegmentEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="44877-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="44877-103">获取指定数量的[COR_HEAPOBJECT](cor-heapobject-structure.md)实例，这些实例包含有关托管堆的内存区域的信息。</span><span class="sxs-lookup"><span data-stu-id="44877-103">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44877-104">语法</span><span class="sxs-lookup"><span data-stu-id="44877-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44877-105">参数</span><span class="sxs-lookup"><span data-stu-id="44877-105">Parameters</span></span>  
 <span data-ttu-id="44877-106">celt</span><span class="sxs-lookup"><span data-stu-id="44877-106">celt</span></span>  
 <span data-ttu-id="44877-107">中要检索的段数。</span><span class="sxs-lookup"><span data-stu-id="44877-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="44877-108">段</span><span class="sxs-lookup"><span data-stu-id="44877-108">segments</span></span>  
 <span data-ttu-id="44877-109">弄指针数组，其中每个都指向一个[COR_HEAPOBJECT](cor-heapobject-structure.md)对象，该对象提供有关托管堆中的内存区域的信息。</span><span class="sxs-lookup"><span data-stu-id="44877-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="44877-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="44877-110">pceltFetched</span></span>  
 <span data-ttu-id="44877-111">弄一个指针，指向 `segments`中实际返回的[COR_HEAPOBJECT](cor-heapobject-structure.md)对象的数量。</span><span class="sxs-lookup"><span data-stu-id="44877-111">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="44877-112">如果 `celt` 为 1，此值可能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="44877-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44877-113">备注</span><span class="sxs-lookup"><span data-stu-id="44877-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44877-114">需求</span><span class="sxs-lookup"><span data-stu-id="44877-114">Requirements</span></span>  
 <span data-ttu-id="44877-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="44877-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44877-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44877-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44877-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44877-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44877-118">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44877-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44877-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44877-119">See also</span></span>

- [<span data-ttu-id="44877-120">ICorDebugHeapSegmentEnum 接口</span><span class="sxs-lookup"><span data-stu-id="44877-120">ICorDebugHeapSegmentEnum Interface</span></span>](icordebugheapsegmentenum-interface.md)
- [<span data-ttu-id="44877-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="44877-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
