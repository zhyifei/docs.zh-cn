---
title: "COR_PRF_FUNCTION_ARGUMENT_INFO 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_FUNCTION_ARGUMENT_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords: COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e4e791bdc41707133fb787a511a39d3ec3d7453a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="corprffunctionargumentinfo-structure"></a><span data-ttu-id="25cc9-102">COR_PRF_FUNCTION_ARGUMENT_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="25cc9-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>
<span data-ttu-id="25cc9-103">按从左向右的顺序表示函数的自变量。</span><span class="sxs-lookup"><span data-stu-id="25cc9-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25cc9-104">语法</span><span class="sxs-lookup"><span data-stu-id="25cc9-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="25cc9-105">成员</span><span class="sxs-lookup"><span data-stu-id="25cc9-105">Members</span></span>  
  
|<span data-ttu-id="25cc9-106">成员</span><span class="sxs-lookup"><span data-stu-id="25cc9-106">Member</span></span>|<span data-ttu-id="25cc9-107">描述</span><span class="sxs-lookup"><span data-stu-id="25cc9-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="25cc9-108">自变量块的数量。</span><span class="sxs-lookup"><span data-stu-id="25cc9-108">The number of blocks of arguments.</span></span> <span data-ttu-id="25cc9-109">也就是说，此值是数[COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md)结构中`ranges`数组。</span><span class="sxs-lookup"><span data-stu-id="25cc9-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="25cc9-110">所有自变量的总大小。</span><span class="sxs-lookup"><span data-stu-id="25cc9-110">The total size of all arguments.</span></span> <span data-ttu-id="25cc9-111">换而言之，此值是自变量长度的总和。</span><span class="sxs-lookup"><span data-stu-id="25cc9-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="25cc9-112">数组`COR_PRF_FUNCTION_ARGUMENT_RANGE`结构，其中每个表示的函数自变量的一个块。</span><span class="sxs-lookup"><span data-stu-id="25cc9-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25cc9-113">备注</span><span class="sxs-lookup"><span data-stu-id="25cc9-113">Remarks</span></span>  
 <span data-ttu-id="25cc9-114">一个函数可能具有多个自变量。</span><span class="sxs-lookup"><span data-stu-id="25cc9-114">A function may have many arguments.</span></span> <span data-ttu-id="25cc9-115">不可能在内存中连续存储这些自变量。</span><span class="sxs-lookup"><span data-stu-id="25cc9-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="25cc9-116">你可能必须在一个位置的三个自变量的块、 在另一个位置中的两个自变量的块和最后一个块中的其他位置的一个自变量。</span><span class="sxs-lookup"><span data-stu-id="25cc9-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="25cc9-117">这些参数均为相同的函数;它们只存储在不同的位置。</span><span class="sxs-lookup"><span data-stu-id="25cc9-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="25cc9-118">`COR_PRF_FUNCTION_ARGUMENT_INFO`结构表示单个函数的所有参数。</span><span class="sxs-lookup"><span data-stu-id="25cc9-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="25cc9-119">它使用数组引用的函数自变量的所有块。</span><span class="sxs-lookup"><span data-stu-id="25cc9-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="25cc9-120">因此，对于单个函数具有单个`COR_PRF_FUNCTION_ARGUMENT_INFO`结构，即在引用多个`COR_PRF_FUNCTION_ARGUMENT_RANGE`结构，其中每个指向一个或多个函数自变量。</span><span class="sxs-lookup"><span data-stu-id="25cc9-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="25cc9-121">存储在寄存器中的自变量会溢出至内存来生成结构。</span><span class="sxs-lookup"><span data-stu-id="25cc9-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25cc9-122">要求</span><span class="sxs-lookup"><span data-stu-id="25cc9-122">Requirements</span></span>  
 <span data-ttu-id="25cc9-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="25cc9-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25cc9-124">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="25cc9-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="25cc9-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25cc9-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25cc9-126">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25cc9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25cc9-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25cc9-127">See Also</span></span>  
 [<span data-ttu-id="25cc9-128">分析结构</span><span class="sxs-lookup"><span data-stu-id="25cc9-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
