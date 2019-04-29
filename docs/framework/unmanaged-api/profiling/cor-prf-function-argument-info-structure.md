---
title: COR_PRF_FUNCTION_ARGUMENT_INFO 结构
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 293ad30ebf47ca8684d158b1ae1772ab245d7981
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775084"
---
# <a name="corprffunctionargumentinfo-structure"></a><span data-ttu-id="bb0a8-102">COR_PRF_FUNCTION_ARGUMENT_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="bb0a8-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>
<span data-ttu-id="bb0a8-103">按从左向右的顺序表示函数的参数。</span><span class="sxs-lookup"><span data-stu-id="bb0a8-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb0a8-104">语法</span><span class="sxs-lookup"><span data-stu-id="bb0a8-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="bb0a8-105">成员</span><span class="sxs-lookup"><span data-stu-id="bb0a8-105">Members</span></span>  
  
|<span data-ttu-id="bb0a8-106">成员</span><span class="sxs-lookup"><span data-stu-id="bb0a8-106">Member</span></span>|<span data-ttu-id="bb0a8-107">描述</span><span class="sxs-lookup"><span data-stu-id="bb0a8-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="bb0a8-108">自变量的块的数目。</span><span class="sxs-lookup"><span data-stu-id="bb0a8-108">The number of blocks of arguments.</span></span> <span data-ttu-id="bb0a8-109">也就是说，此值是数[COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md)结构中`ranges`数组。</span><span class="sxs-lookup"><span data-stu-id="bb0a8-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="bb0a8-110">所有自变量的总大小。</span><span class="sxs-lookup"><span data-stu-id="bb0a8-110">The total size of all arguments.</span></span> <span data-ttu-id="bb0a8-111">换而言之，此值是参数长度的总和。</span><span class="sxs-lookup"><span data-stu-id="bb0a8-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="bb0a8-112">一个数组`COR_PRF_FUNCTION_ARGUMENT_RANGE`结构，其中每个表示一个函数自变量的块。</span><span class="sxs-lookup"><span data-stu-id="bb0a8-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb0a8-113">备注</span><span class="sxs-lookup"><span data-stu-id="bb0a8-113">Remarks</span></span>  
 <span data-ttu-id="bb0a8-114">一个函数可能会有多的参数。</span><span class="sxs-lookup"><span data-stu-id="bb0a8-114">A function may have many arguments.</span></span> <span data-ttu-id="bb0a8-115">不可能在内存中连续存储这些参数。</span><span class="sxs-lookup"><span data-stu-id="bb0a8-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="bb0a8-116">你可能在一个位置的三个参数的块、 在另一个位置中的两个参数的块和一个自变量的不同位置中的最后一个块。</span><span class="sxs-lookup"><span data-stu-id="bb0a8-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="bb0a8-117">这些参数均为相同的功能;它们只存储在不同的位置。</span><span class="sxs-lookup"><span data-stu-id="bb0a8-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="bb0a8-118">`COR_PRF_FUNCTION_ARGUMENT_INFO`结构表示的单个函数的所有自变量。</span><span class="sxs-lookup"><span data-stu-id="bb0a8-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="bb0a8-119">它使用数组引用的函数自变量的所有块。</span><span class="sxs-lookup"><span data-stu-id="bb0a8-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="bb0a8-120">因此，对于单个函数，具有单个`COR_PRF_FUNCTION_ARGUMENT_INFO`结构，它引用多个`COR_PRF_FUNCTION_ARGUMENT_RANGE`结构，其中每个点对一个或多个函数参数。</span><span class="sxs-lookup"><span data-stu-id="bb0a8-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="bb0a8-121">存储在寄存器中的参数将溢出到内存中才能生成结构。</span><span class="sxs-lookup"><span data-stu-id="bb0a8-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb0a8-122">要求</span><span class="sxs-lookup"><span data-stu-id="bb0a8-122">Requirements</span></span>  
 <span data-ttu-id="bb0a8-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bb0a8-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb0a8-124">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="bb0a8-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="bb0a8-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb0a8-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb0a8-126">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb0a8-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb0a8-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb0a8-127">See also</span></span>

- [<span data-ttu-id="bb0a8-128">分析结构</span><span class="sxs-lookup"><span data-stu-id="bb0a8-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
