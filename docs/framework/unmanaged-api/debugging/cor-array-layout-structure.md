---
title: COR_ARRAY_LAYOUT 结构
ms.date: 03/30/2017
api_name:
- COR_ARRAY_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ARRAY_LAYOUT
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: aa20ac3d-6f60-4aa2-91c5-f3a86f82eba8
topic_type:
- apiref
ms.openlocfilehash: ca2d00611a7530dfb0d1c2a27123947bdf69820d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179341"
---
# <a name="cor_array_layout-structure"></a><span data-ttu-id="e7930-102">COR_ARRAY_LAYOUT 结构</span><span class="sxs-lookup"><span data-stu-id="e7930-102">COR_ARRAY_LAYOUT Structure</span></span>
<span data-ttu-id="e7930-103">提供有关内存中数组对象的布局的信息。</span><span class="sxs-lookup"><span data-stu-id="e7930-103">Provides information about the layout of an array object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7930-104">语法</span><span class="sxs-lookup"><span data-stu-id="e7930-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_ARRAY_LAYOUT {  
    COR_TYPEID componentID;  
    CorElementType componentType;  
    ULONG32 firstElementOffset;  
    ULONG32 elementSize;  
    ULONG32 countOffset;
    ULONG32 rankSize;
    ULONG32 numRanks;
    ULONG32 rankOffset;
} COR_ARRAY_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="e7930-105">成员</span><span class="sxs-lookup"><span data-stu-id="e7930-105">Members</span></span>  
  
|<span data-ttu-id="e7930-106">成员</span><span class="sxs-lookup"><span data-stu-id="e7930-106">Member</span></span>|<span data-ttu-id="e7930-107">说明</span><span class="sxs-lookup"><span data-stu-id="e7930-107">Description</span></span>|  
|------------|-----------------|  
|`componentID`|<span data-ttu-id="e7930-108">数组包含的对象类型的标识符。</span><span class="sxs-lookup"><span data-stu-id="e7930-108">The identifier of the type of objects that the array contains.</span></span>|  
|`componentType`|<span data-ttu-id="e7930-109">CorElementType 枚举值，用于指示组件是垃圾回收引用、值类还是基元。</span><span class="sxs-lookup"><span data-stu-id="e7930-109">A CorElementType enumeration value that indicates whether the component is a garbage collection reference, a value class, or a primitive.</span></span>|  
|`firstElementOffset`|<span data-ttu-id="e7930-110">数组中第一个元素的偏移量。</span><span class="sxs-lookup"><span data-stu-id="e7930-110">The offset to the first element in the array.</span></span>|  
|`elementSize`|<span data-ttu-id="e7930-111">每个元素的大小。</span><span class="sxs-lookup"><span data-stu-id="e7930-111">The size of each element.</span></span>|  
|`countOffset`|<span data-ttu-id="e7930-112">数组中元素数的偏移量。</span><span class="sxs-lookup"><span data-stu-id="e7930-112">The offset to the number of elements in the array.</span></span>|  
|`rankSize`|<span data-ttu-id="e7930-113">排名的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="e7930-113">The size of the rank, in bytes.</span></span>|  
|`numRanks`|<span data-ttu-id="e7930-114">数组中的排名数。</span><span class="sxs-lookup"><span data-stu-id="e7930-114">The number of ranks in the array.</span></span>|  
|`rankOffset`|<span data-ttu-id="e7930-115">排名开始的偏移量。</span><span class="sxs-lookup"><span data-stu-id="e7930-115">The offset at which the ranks start.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7930-116">备注</span><span class="sxs-lookup"><span data-stu-id="e7930-116">Remarks</span></span>  
 <span data-ttu-id="e7930-117">该`rankSize`字段指定多维数组中排名的大小。</span><span class="sxs-lookup"><span data-stu-id="e7930-117">The `rankSize` field specifies the size of a rank in a multi-dimensional array.</span></span> <span data-ttu-id="e7930-118">对于单维数组来说，它也是准确的。</span><span class="sxs-lookup"><span data-stu-id="e7930-118">It is accurate for single-dimensional arrays as well.</span></span>  
  
 <span data-ttu-id="e7930-119">对于单维`numRanks`数组和`N`多维`N`维度数组，值为 1。</span><span class="sxs-lookup"><span data-stu-id="e7930-119">The value of `numRanks` is 1 for a single-dimensional array and `N` for a multi-dimensional array of `N` dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7930-120">要求</span><span class="sxs-lookup"><span data-stu-id="e7930-120">Requirements</span></span>  
 <span data-ttu-id="e7930-121">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e7930-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7930-122">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7930-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7930-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7930-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7930-124">**.NET 框架版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7930-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7930-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7930-125">See also</span></span>

- [<span data-ttu-id="e7930-126">调试结构</span><span class="sxs-lookup"><span data-stu-id="e7930-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="e7930-127">调试</span><span class="sxs-lookup"><span data-stu-id="e7930-127">Debugging</span></span>](index.md)
