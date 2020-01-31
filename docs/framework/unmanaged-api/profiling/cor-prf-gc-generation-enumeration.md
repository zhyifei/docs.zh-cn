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
ms.openlocfilehash: 4eff8472e353c4e5fd2505b281cc9efc89f013fc
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867202"
---
# <a name="cor_prf_gc_generation-enumeration"></a><span data-ttu-id="06a12-102">COR_PRF_GC_GENERATION 枚举</span><span class="sxs-lookup"><span data-stu-id="06a12-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="06a12-103">标识垃圾回收生成。</span><span class="sxs-lookup"><span data-stu-id="06a12-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06a12-104">语法</span><span class="sxs-lookup"><span data-stu-id="06a12-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="06a12-105">Members</span><span class="sxs-lookup"><span data-stu-id="06a12-105">Members</span></span>  
  
|<span data-ttu-id="06a12-106">成员</span><span class="sxs-lookup"><span data-stu-id="06a12-106">Member</span></span>|<span data-ttu-id="06a12-107">描述</span><span class="sxs-lookup"><span data-stu-id="06a12-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="06a12-108">对象存储为第0代。</span><span class="sxs-lookup"><span data-stu-id="06a12-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="06a12-109">对象存储为第1代。</span><span class="sxs-lookup"><span data-stu-id="06a12-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="06a12-110">对象存储为第2代。</span><span class="sxs-lookup"><span data-stu-id="06a12-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="06a12-111">对象存储在大型对象堆中。</span><span class="sxs-lookup"><span data-stu-id="06a12-111">The object is stored in the large-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06a12-112">备注</span><span class="sxs-lookup"><span data-stu-id="06a12-112">Remarks</span></span>  
 <span data-ttu-id="06a12-113">垃圾回收器通过将对象划分为基于年龄的代来改善内存管理性能。</span><span class="sxs-lookup"><span data-stu-id="06a12-113">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="06a12-114">垃圾回收器当前使用三代，编号为0、1和2，以及用于大型对象的特殊堆段。</span><span class="sxs-lookup"><span data-stu-id="06a12-114">The garbage collector currently uses three generations, numbered 0, 1, and 2, plus a special heap segment that is used for large objects.</span></span> <span data-ttu-id="06a12-115">大小大于特定值的对象存储在大型对象堆中。</span><span class="sxs-lookup"><span data-stu-id="06a12-115">Objects whose size is larger than a particular value are stored in the large-object heap.</span></span> <span data-ttu-id="06a12-116">其他已分配对象开始属于0代。</span><span class="sxs-lookup"><span data-stu-id="06a12-116">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="06a12-117">发生垃圾回收后存在的所有对象都将升级到第1代。</span><span class="sxs-lookup"><span data-stu-id="06a12-117">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="06a12-118">在第1代中发生垃圾回收后存在的对象将移入第2代。</span><span class="sxs-lookup"><span data-stu-id="06a12-118">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="06a12-119">代的使用意味着垃圾回收器在任一时间只需要处理已分配对象的子集。</span><span class="sxs-lookup"><span data-stu-id="06a12-119">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="06a12-120">`COR_PRF_GC_GENERATION` 枚举由[COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md)结构使用。</span><span class="sxs-lookup"><span data-stu-id="06a12-120">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06a12-121">需求</span><span class="sxs-lookup"><span data-stu-id="06a12-121">Requirements</span></span>  
 <span data-ttu-id="06a12-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="06a12-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06a12-123">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="06a12-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="06a12-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06a12-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06a12-125">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06a12-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06a12-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06a12-126">See also</span></span>

- [<span data-ttu-id="06a12-127">分析枚举</span><span class="sxs-lookup"><span data-stu-id="06a12-127">Profiling Enumerations</span></span>](profiling-enumerations.md)
