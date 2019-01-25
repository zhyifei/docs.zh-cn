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
ms.openlocfilehash: 15bd3ed8f1642e44ecf9c4df49feebd72eeac8c2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590128"
---
# <a name="corprfgcgeneration-enumeration"></a><span data-ttu-id="5fe7b-102">COR_PRF_GC_GENERATION 枚举</span><span class="sxs-lookup"><span data-stu-id="5fe7b-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="5fe7b-103">标识垃圾回收的代。</span><span class="sxs-lookup"><span data-stu-id="5fe7b-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fe7b-104">语法</span><span class="sxs-lookup"><span data-stu-id="5fe7b-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="5fe7b-105">成员</span><span class="sxs-lookup"><span data-stu-id="5fe7b-105">Members</span></span>  
  
|<span data-ttu-id="5fe7b-106">成员</span><span class="sxs-lookup"><span data-stu-id="5fe7b-106">Member</span></span>|<span data-ttu-id="5fe7b-107">描述</span><span class="sxs-lookup"><span data-stu-id="5fe7b-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="5fe7b-108">该对象存储为第 0 代中。</span><span class="sxs-lookup"><span data-stu-id="5fe7b-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="5fe7b-109">该对象存储为第 1 代。</span><span class="sxs-lookup"><span data-stu-id="5fe7b-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="5fe7b-110">该对象存储为第 2 代。</span><span class="sxs-lookup"><span data-stu-id="5fe7b-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="5fe7b-111">该对象存储在大型对象堆。</span><span class="sxs-lookup"><span data-stu-id="5fe7b-111">The object is stored in the large-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fe7b-112">备注</span><span class="sxs-lookup"><span data-stu-id="5fe7b-112">Remarks</span></span>  
 <span data-ttu-id="5fe7b-113">垃圾回收器提高将对象划分为几个代根据年龄内存管理性能。</span><span class="sxs-lookup"><span data-stu-id="5fe7b-113">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="5fe7b-114">垃圾回收器当前正在使用三代，编号为 0、 1 和 2，以及用于大型对象的特殊堆段。</span><span class="sxs-lookup"><span data-stu-id="5fe7b-114">The garbage collector currently uses three generations, numbered 0, 1, and 2, plus a special heap segment that is used for large objects.</span></span> <span data-ttu-id="5fe7b-115">其大小大于特定值的对象存储在大型对象堆。</span><span class="sxs-lookup"><span data-stu-id="5fe7b-115">Objects whose size is larger than a particular value are stored in the large-object heap.</span></span> <span data-ttu-id="5fe7b-116">其他分配的对象最初属于第 0 代。</span><span class="sxs-lookup"><span data-stu-id="5fe7b-116">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="5fe7b-117">第 0 代中发生了垃圾回收后存在的所有对象都提升到第 1 代。</span><span class="sxs-lookup"><span data-stu-id="5fe7b-117">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="5fe7b-118">在第 1 代垃圾回收后存在的对象将移到第 2 代。</span><span class="sxs-lookup"><span data-stu-id="5fe7b-118">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="5fe7b-119">代的使用意味着，垃圾收集器在任何一次处理已分配对象的一个子集。</span><span class="sxs-lookup"><span data-stu-id="5fe7b-119">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="5fe7b-120">`COR_PRF_GC_GENERATION`枚举由[COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="5fe7b-120">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fe7b-121">要求</span><span class="sxs-lookup"><span data-stu-id="5fe7b-121">Requirements</span></span>  
 <span data-ttu-id="5fe7b-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5fe7b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fe7b-123">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5fe7b-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5fe7b-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fe7b-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fe7b-125">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fe7b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fe7b-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="5fe7b-126">See also</span></span>
- [<span data-ttu-id="5fe7b-127">分析枚举</span><span class="sxs-lookup"><span data-stu-id="5fe7b-127">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
