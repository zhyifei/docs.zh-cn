---
title: "COR_PRF_GC_ROOT_FLAGS 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_ROOT_FLAGS
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords: COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5e00f695edb94acbd54d6bd009ccd629aeec1b14
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corprfgcrootflags-enumeration"></a><span data-ttu-id="74963-102">COR_PRF_GC_ROOT_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="74963-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="74963-103">指示垃圾回收根的属性。</span><span class="sxs-lookup"><span data-stu-id="74963-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74963-104">语法</span><span class="sxs-lookup"><span data-stu-id="74963-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="74963-105">成员</span><span class="sxs-lookup"><span data-stu-id="74963-105">Members</span></span>  
  
|<span data-ttu-id="74963-106">成员</span><span class="sxs-lookup"><span data-stu-id="74963-106">Member</span></span>|<span data-ttu-id="74963-107">描述</span><span class="sxs-lookup"><span data-stu-id="74963-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="74963-108">根可以防止移动该对象进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="74963-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="74963-109">根不会阻止垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="74963-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="74963-110">根引用的对象，而不是对象本身的字段。</span><span class="sxs-lookup"><span data-stu-id="74963-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="74963-111">如果该对象的引用计数为某个特定值，则根可防止垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="74963-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74963-112">备注</span><span class="sxs-lookup"><span data-stu-id="74963-112">Remarks</span></span>  
 <span data-ttu-id="74963-113">`COR_PRF_GC_ROOT_FLAGS`是提供特殊的根的附加信息的位掩码。</span><span class="sxs-lookup"><span data-stu-id="74963-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="74963-114">但是，并非所有根都是特殊的。</span><span class="sxs-lookup"><span data-stu-id="74963-114">However, not all roots are special.</span></span> <span data-ttu-id="74963-115">例如，某些根不是弱引用，已固定，或引用计数的内部指针。</span><span class="sxs-lookup"><span data-stu-id="74963-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="74963-116">对于这种根有要传达的标志。</span><span class="sxs-lookup"><span data-stu-id="74963-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="74963-117">因此，使用此枚举中，如的方法[icorprofilercallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)方法，发送 0 标志的位掩码，指示所有标志处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="74963-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74963-118">惠?</span><span class="sxs-lookup"><span data-stu-id="74963-118">Requirements</span></span>  
 <span data-ttu-id="74963-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="74963-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74963-120">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="74963-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="74963-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74963-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74963-122">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74963-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74963-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="74963-123">See Also</span></span>  
 [<span data-ttu-id="74963-124">分析枚举</span><span class="sxs-lookup"><span data-stu-id="74963-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
