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
ms.openlocfilehash: c92ee580caed9f1fb87a31b676747769ad31a0e2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867242"
---
# <a name="cor_prf_function_argument_info-structure"></a><span data-ttu-id="f3c0a-102">COR_PRF_FUNCTION_ARGUMENT_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="f3c0a-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>
<span data-ttu-id="f3c0a-103">按从左向右的顺序表示函数的参数。</span><span class="sxs-lookup"><span data-stu-id="f3c0a-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3c0a-104">语法</span><span class="sxs-lookup"><span data-stu-id="f3c0a-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="f3c0a-105">Members</span><span class="sxs-lookup"><span data-stu-id="f3c0a-105">Members</span></span>  
  
|<span data-ttu-id="f3c0a-106">成员</span><span class="sxs-lookup"><span data-stu-id="f3c0a-106">Member</span></span>|<span data-ttu-id="f3c0a-107">描述</span><span class="sxs-lookup"><span data-stu-id="f3c0a-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="f3c0a-108">参数块的数目。</span><span class="sxs-lookup"><span data-stu-id="f3c0a-108">The number of blocks of arguments.</span></span> <span data-ttu-id="f3c0a-109">也就是说，此值是 `ranges` 数组中[COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md)结构的数目。</span><span class="sxs-lookup"><span data-stu-id="f3c0a-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="f3c0a-110">所有参数的总大小。</span><span class="sxs-lookup"><span data-stu-id="f3c0a-110">The total size of all arguments.</span></span> <span data-ttu-id="f3c0a-111">换言之，此值是自变量长度之和。</span><span class="sxs-lookup"><span data-stu-id="f3c0a-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="f3c0a-112">`COR_PRF_FUNCTION_ARGUMENT_RANGE` 结构的数组，其中每个结构都表示一个函数参数块。</span><span class="sxs-lookup"><span data-stu-id="f3c0a-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3c0a-113">备注</span><span class="sxs-lookup"><span data-stu-id="f3c0a-113">Remarks</span></span>  
 <span data-ttu-id="f3c0a-114">函数可以包含多个参数。</span><span class="sxs-lookup"><span data-stu-id="f3c0a-114">A function may have many arguments.</span></span> <span data-ttu-id="f3c0a-115">这些参数可能不会连续存储在内存中。</span><span class="sxs-lookup"><span data-stu-id="f3c0a-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="f3c0a-116">在一个位置，您可能有一个包含三个自变量的块、另一个位置中的两个参数块，以及在不同位置中的一个自变量的最后一个块。</span><span class="sxs-lookup"><span data-stu-id="f3c0a-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="f3c0a-117">这些参数全部用于相同的函数;它们只是存储在不同的位置。</span><span class="sxs-lookup"><span data-stu-id="f3c0a-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="f3c0a-118">`COR_PRF_FUNCTION_ARGUMENT_INFO` 结构表示一个函数的所有自变量。</span><span class="sxs-lookup"><span data-stu-id="f3c0a-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="f3c0a-119">它使用数组引用函数参数的所有块。</span><span class="sxs-lookup"><span data-stu-id="f3c0a-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="f3c0a-120">因此，对于单个函数，有一个 `COR_PRF_FUNCTION_ARGUMENT_INFO` 结构，该结构引用多个 `COR_PRF_FUNCTION_ARGUMENT_RANGE` 结构，其中每个结构都指向一个或多个函数参数。</span><span class="sxs-lookup"><span data-stu-id="f3c0a-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="f3c0a-121">存储在寄存器中的参数会溢出到内存中以生成结构。</span><span class="sxs-lookup"><span data-stu-id="f3c0a-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3c0a-122">需求</span><span class="sxs-lookup"><span data-stu-id="f3c0a-122">Requirements</span></span>  
 <span data-ttu-id="f3c0a-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f3c0a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3c0a-124">**标头：** Corprof.idl .idl</span><span class="sxs-lookup"><span data-stu-id="f3c0a-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="f3c0a-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3c0a-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3c0a-126">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3c0a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3c0a-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3c0a-127">See also</span></span>

- [<span data-ttu-id="f3c0a-128">分析结构</span><span class="sxs-lookup"><span data-stu-id="f3c0a-128">Profiling Structures</span></span>](profiling-structures.md)
