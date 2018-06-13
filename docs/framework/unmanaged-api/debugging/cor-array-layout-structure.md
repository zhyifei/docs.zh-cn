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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a96542ab5113311bba79cc552afd7f29e6eafa2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406391"
---
# <a name="corarraylayout-structure"></a><span data-ttu-id="e22cf-102">COR_ARRAY_LAYOUT 结构</span><span class="sxs-lookup"><span data-stu-id="e22cf-102">COR_ARRAY_LAYOUT Structure</span></span>
<span data-ttu-id="e22cf-103">提供有关内存中数组对象的布局的信息。</span><span class="sxs-lookup"><span data-stu-id="e22cf-103">Provides information about the layout of an array object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e22cf-104">语法</span><span class="sxs-lookup"><span data-stu-id="e22cf-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="e22cf-105">成员</span><span class="sxs-lookup"><span data-stu-id="e22cf-105">Members</span></span>  
  
|<span data-ttu-id="e22cf-106">成员</span><span class="sxs-lookup"><span data-stu-id="e22cf-106">Member</span></span>|<span data-ttu-id="e22cf-107">描述</span><span class="sxs-lookup"><span data-stu-id="e22cf-107">Description</span></span>|  
|------------|-----------------|  
|`componentID`|<span data-ttu-id="e22cf-108">该数组包含的对象的类型的标识符。</span><span class="sxs-lookup"><span data-stu-id="e22cf-108">The identifier of the type of objects that the array contains.</span></span>|  
|`componentType`|<span data-ttu-id="e22cf-109">CorElementType 枚举值，该值指示组件是否是垃圾回收引用、 值类或基元。</span><span class="sxs-lookup"><span data-stu-id="e22cf-109">A CorElementType enumeration value that indicates whether the component is a garbage collection reference, a value class, or a primitive.</span></span>|  
|`firstElementOffset`|<span data-ttu-id="e22cf-110">到数组中的第一个元素的偏移量。</span><span class="sxs-lookup"><span data-stu-id="e22cf-110">The offset to the first element in the array.</span></span>|  
|`elementSize`|<span data-ttu-id="e22cf-111">每个元素的大小。</span><span class="sxs-lookup"><span data-stu-id="e22cf-111">The size of each element.</span></span>|  
|`countOffset`|<span data-ttu-id="e22cf-112">到数组中元素的数目的偏移量。</span><span class="sxs-lookup"><span data-stu-id="e22cf-112">The offset to the number of elements in the array.</span></span>|  
|`rankSize`|<span data-ttu-id="e22cf-113">秩，以字节为单位的大小。</span><span class="sxs-lookup"><span data-stu-id="e22cf-113">The size of the rank, in bytes.</span></span>|  
|`numRanks`|<span data-ttu-id="e22cf-114">数组中的排名数。</span><span class="sxs-lookup"><span data-stu-id="e22cf-114">The number of ranks in the array.</span></span>|  
|`rankOffset`|<span data-ttu-id="e22cf-115">排名开始偏移量。</span><span class="sxs-lookup"><span data-stu-id="e22cf-115">The offset at which the ranks start.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e22cf-116">备注</span><span class="sxs-lookup"><span data-stu-id="e22cf-116">Remarks</span></span>  
 <span data-ttu-id="e22cf-117">`rankSize`字段多维数组中指定级别的大小。</span><span class="sxs-lookup"><span data-stu-id="e22cf-117">The `rankSize` field specifies the size of a rank in a multi-dimensional array.</span></span> <span data-ttu-id="e22cf-118">它是一维数组以及准确的。</span><span class="sxs-lookup"><span data-stu-id="e22cf-118">It is accurate for single-dimensional arrays as well.</span></span>  
  
 <span data-ttu-id="e22cf-119">值`numRanks`对于一维数组是 1 和`N`的多维数组的`N`维度。</span><span class="sxs-lookup"><span data-stu-id="e22cf-119">The value of `numRanks` is 1 for a single-dimensional array and `N` for a multi-dimensional array of `N` dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e22cf-120">要求</span><span class="sxs-lookup"><span data-stu-id="e22cf-120">Requirements</span></span>  
 <span data-ttu-id="e22cf-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e22cf-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e22cf-122">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e22cf-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e22cf-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e22cf-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e22cf-124">**.NET framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e22cf-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e22cf-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="e22cf-125">See Also</span></span>  
 [<span data-ttu-id="e22cf-126">调试结构</span><span class="sxs-lookup"><span data-stu-id="e22cf-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="e22cf-127">调试</span><span class="sxs-lookup"><span data-stu-id="e22cf-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
