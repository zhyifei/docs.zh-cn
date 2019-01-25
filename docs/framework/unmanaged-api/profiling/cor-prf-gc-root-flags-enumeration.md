---
title: COR_PRF_GC_ROOT_FLAGS 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords:
- COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f4ce8fb8d9d941544982c8da852260b8018788a6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680737"
---
# <a name="corprfgcrootflags-enumeration"></a><span data-ttu-id="bee8e-102">COR_PRF_GC_ROOT_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="bee8e-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="bee8e-103">指示垃圾回收根的属性。</span><span class="sxs-lookup"><span data-stu-id="bee8e-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bee8e-104">语法</span><span class="sxs-lookup"><span data-stu-id="bee8e-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="bee8e-105">成员</span><span class="sxs-lookup"><span data-stu-id="bee8e-105">Members</span></span>  
  
|<span data-ttu-id="bee8e-106">成员</span><span class="sxs-lookup"><span data-stu-id="bee8e-106">Member</span></span>|<span data-ttu-id="bee8e-107">描述</span><span class="sxs-lookup"><span data-stu-id="bee8e-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="bee8e-108">根可防止垃圾回收将对象移动。</span><span class="sxs-lookup"><span data-stu-id="bee8e-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="bee8e-109">根不会阻止垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="bee8e-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="bee8e-110">根引用的对象，而不是对象本身的字段。</span><span class="sxs-lookup"><span data-stu-id="bee8e-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="bee8e-111">如果该对象的引用计数为某个特定值，根可防止垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="bee8e-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bee8e-112">备注</span><span class="sxs-lookup"><span data-stu-id="bee8e-112">Remarks</span></span>  
 <span data-ttu-id="bee8e-113">`COR_PRF_GC_ROOT_FLAGS` 是一个位掩码，提供了特殊的根的其他信息。</span><span class="sxs-lookup"><span data-stu-id="bee8e-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="bee8e-114">但是，并非所有根都是特殊的。</span><span class="sxs-lookup"><span data-stu-id="bee8e-114">However, not all roots are special.</span></span> <span data-ttu-id="bee8e-115">例如，某些根不是弱引用，固定的或引用计数的内部指针。</span><span class="sxs-lookup"><span data-stu-id="bee8e-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="bee8e-116">对于此类的根，有要传达的标志。</span><span class="sxs-lookup"><span data-stu-id="bee8e-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="bee8e-117">因此，使用此枚举中，如下所示的方法[ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)方法中，发送 0 标志位掩码，指示所有标记为关闭状态。</span><span class="sxs-lookup"><span data-stu-id="bee8e-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bee8e-118">要求</span><span class="sxs-lookup"><span data-stu-id="bee8e-118">Requirements</span></span>  
 <span data-ttu-id="bee8e-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bee8e-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bee8e-120">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bee8e-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bee8e-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bee8e-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bee8e-122">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bee8e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bee8e-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="bee8e-123">See also</span></span>
- [<span data-ttu-id="bee8e-124">分析枚举</span><span class="sxs-lookup"><span data-stu-id="bee8e-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
