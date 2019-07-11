---
title: COR_PRF_GC_GENERATION 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION
helpviewer_keywords:
- COR_GC_GENERATION_FLAGS enumeration [.NET Framework profiling]
ms.assetid: d6ece160-26ad-4d39-abd7-05acd6f78c48
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 74e70f58600205d44a9ba052981b2cc67b3a44ec
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753812"
---
# <a name="corprfgcgeneration-enumeration"></a><span data-ttu-id="fa578-102">COR_PRF_GC_GENERATION 枚举</span><span class="sxs-lookup"><span data-stu-id="fa578-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="fa578-103">标识垃圾回收的代。</span><span class="sxs-lookup"><span data-stu-id="fa578-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa578-104">语法</span><span class="sxs-lookup"><span data-stu-id="fa578-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="fa578-105">成员</span><span class="sxs-lookup"><span data-stu-id="fa578-105">Members</span></span>  
  
|<span data-ttu-id="fa578-106">成员</span><span class="sxs-lookup"><span data-stu-id="fa578-106">Member</span></span>|<span data-ttu-id="fa578-107">描述</span><span class="sxs-lookup"><span data-stu-id="fa578-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="fa578-108">该对象存储为第 0 代中。</span><span class="sxs-lookup"><span data-stu-id="fa578-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="fa578-109">该对象存储为第 1 代。</span><span class="sxs-lookup"><span data-stu-id="fa578-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="fa578-110">该对象存储为第 2 代。</span><span class="sxs-lookup"><span data-stu-id="fa578-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="fa578-111">该对象存储在大型对象堆。</span><span class="sxs-lookup"><span data-stu-id="fa578-111">The object is stored in the large-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa578-112">备注</span><span class="sxs-lookup"><span data-stu-id="fa578-112">Remarks</span></span>  
 <span data-ttu-id="fa578-113">垃圾回收器提高将对象划分为几个代根据年龄内存管理性能。</span><span class="sxs-lookup"><span data-stu-id="fa578-113">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="fa578-114">垃圾回收器当前正在使用三代，编号为 0、 1 和 2，以及用于大型对象的特殊堆段。</span><span class="sxs-lookup"><span data-stu-id="fa578-114">The garbage collector currently uses three generations, numbered 0, 1, and 2, plus a special heap segment that is used for large objects.</span></span> <span data-ttu-id="fa578-115">其大小大于特定值的对象存储在大型对象堆。</span><span class="sxs-lookup"><span data-stu-id="fa578-115">Objects whose size is larger than a particular value are stored in the large-object heap.</span></span> <span data-ttu-id="fa578-116">其他分配的对象最初属于第 0 代。</span><span class="sxs-lookup"><span data-stu-id="fa578-116">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="fa578-117">第 0 代中发生了垃圾回收后存在的所有对象都提升到第 1 代。</span><span class="sxs-lookup"><span data-stu-id="fa578-117">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="fa578-118">在第 1 代垃圾回收后存在的对象将移到第 2 代。</span><span class="sxs-lookup"><span data-stu-id="fa578-118">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="fa578-119">代的使用意味着，垃圾收集器在任何一次处理已分配对象的一个子集。</span><span class="sxs-lookup"><span data-stu-id="fa578-119">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="fa578-120">`COR_PRF_GC_GENERATION`枚举由[COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="fa578-120">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa578-121">要求</span><span class="sxs-lookup"><span data-stu-id="fa578-121">Requirements</span></span>  
 <span data-ttu-id="fa578-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fa578-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa578-123">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fa578-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fa578-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa578-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa578-125">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa578-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa578-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa578-126">See also</span></span>

- [<span data-ttu-id="fa578-127">分析枚举</span><span class="sxs-lookup"><span data-stu-id="fa578-127">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
