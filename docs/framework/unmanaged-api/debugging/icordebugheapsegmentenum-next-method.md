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
ms.openlocfilehash: 8a267ec7123edb73ad51f0781a78344119ec6f21
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178896"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="b2fc0-102">ICorDebugHeapSegmentEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="b2fc0-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="b2fc0-103">获取包含有关托管堆内存区域[信息的指定](cor-heapobject-structure.md)COR_HEAPOBJECT实例数。</span><span class="sxs-lookup"><span data-stu-id="b2fc0-103">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2fc0-104">语法</span><span class="sxs-lookup"><span data-stu-id="b2fc0-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2fc0-105">parameters</span><span class="sxs-lookup"><span data-stu-id="b2fc0-105">Parameters</span></span>  
 <span data-ttu-id="b2fc0-106">celt</span><span class="sxs-lookup"><span data-stu-id="b2fc0-106">celt</span></span>  
 <span data-ttu-id="b2fc0-107">[在]要检索的段数。</span><span class="sxs-lookup"><span data-stu-id="b2fc0-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="b2fc0-108">段</span><span class="sxs-lookup"><span data-stu-id="b2fc0-108">segments</span></span>  
 <span data-ttu-id="b2fc0-109">[出]指针数组，每个指针都[指向COR_HEAPOBJECT对象](cor-heapobject-structure.md)，该对象提供有关托管堆中内存区域的信息。</span><span class="sxs-lookup"><span data-stu-id="b2fc0-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="b2fc0-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="b2fc0-110">pceltFetched</span></span>  
 <span data-ttu-id="b2fc0-111">[出]指向 中实际[返回COR_HEAPOBJECT对象的](cor-heapobject-structure.md)数量的指针`segments`。</span><span class="sxs-lookup"><span data-stu-id="b2fc0-111">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="b2fc0-112">如果 `celt` 为 1，此值可能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="b2fc0-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2fc0-113">备注</span><span class="sxs-lookup"><span data-stu-id="b2fc0-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2fc0-114">要求</span><span class="sxs-lookup"><span data-stu-id="b2fc0-114">Requirements</span></span>  
 <span data-ttu-id="b2fc0-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b2fc0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2fc0-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2fc0-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2fc0-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2fc0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2fc0-118">**.NET 框架版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2fc0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2fc0-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2fc0-119">See also</span></span>

- [<span data-ttu-id="b2fc0-120">ICorDebugHeapSegmentEnum 接口</span><span class="sxs-lookup"><span data-stu-id="b2fc0-120">ICorDebugHeapSegmentEnum Interface</span></span>](icordebugheapsegmentenum-interface.md)
- [<span data-ttu-id="b2fc0-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="b2fc0-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
