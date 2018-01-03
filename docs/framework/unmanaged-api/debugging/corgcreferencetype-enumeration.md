---
title: "CorGCReferenceType 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorGCReferenceType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorGCReferenceType
helpviewer_keywords: CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b314580f7628eca68a3996aaafb362081c6ed705
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corgcreferencetype-enumeration"></a><span data-ttu-id="61c5d-102">CorGCReferenceType 枚举</span><span class="sxs-lookup"><span data-stu-id="61c5d-102">CorGCReferenceType Enumeration</span></span>
<span data-ttu-id="61c5d-103">标识要进行垃圾回收的对象的源。</span><span class="sxs-lookup"><span data-stu-id="61c5d-103">Identifies the source of an object to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61c5d-104">语法</span><span class="sxs-lookup"><span data-stu-id="61c5d-104">Syntax</span></span>  
  
```  
typedef enum {  
    CorHandleStrong = 1,  
    CorHandleStrongPinning = 2,  
    CorHandleWeakShort = 4,  
    CorHandleWeakRefCount = 8,  
    CorHandleStrongRefCount = 32,  
    CorHandleStrongDependent = 64,  
    CorHandleStrongAsyncPinned = 128,  
    CorHandleStrongSizedByref = 256,  
  
    CorReferenceStack = 0x80000001,  
    CorReferenceFinalizer = 0x80000002,  
  
    CorHandleStrongOnly = 0x1E3,  
    CorHandleWeakOnly = 0xC,  
    CorHandleAll = 0x7FFFFFFF  
} CorGCReferenceType  
```  
  
## <a name="members"></a><span data-ttu-id="61c5d-105">成员</span><span class="sxs-lookup"><span data-stu-id="61c5d-105">Members</span></span>  
  
|<span data-ttu-id="61c5d-106">成员名称</span><span class="sxs-lookup"><span data-stu-id="61c5d-106">Member name</span></span>|<span data-ttu-id="61c5d-107">描述</span><span class="sxs-lookup"><span data-stu-id="61c5d-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorHandleStrong`|<span data-ttu-id="61c5d-108">来自对象句柄表的强引用的句柄。</span><span class="sxs-lookup"><span data-stu-id="61c5d-108">A handle to a strong reference from the object handle table.</span></span>|  
|`CorHandleStrongPinning`|<span data-ttu-id="61c5d-109">来自对象句柄表的固定强引用句柄。</span><span class="sxs-lookup"><span data-stu-id="61c5d-109">A handle to a pinned strong reference from the object handle table.</span></span>|  
|`CorHandleWeakShort`|<span data-ttu-id="61c5d-110">来自对象句柄表的弱引用句柄。</span><span class="sxs-lookup"><span data-stu-id="61c5d-110">A handle to a weak reference from the object handle table.</span></span>|  
|`CorHandleWeakRefCount`|<span data-ttu-id="61c5d-111">来自对象句柄表的弱引用计数对象句柄。</span><span class="sxs-lookup"><span data-stu-id="61c5d-111">A handle to a weak reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongRefCount`|<span data-ttu-id="61c5d-112">来自对象句柄表的引用计数对象句柄。</span><span class="sxs-lookup"><span data-stu-id="61c5d-112">A handle to a reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongDependent`|<span data-ttu-id="61c5d-113">来自对象句柄表的依赖对象句柄。</span><span class="sxs-lookup"><span data-stu-id="61c5d-113">A handle to a dependent object from the object handle table.</span></span>|  
|`CorHandleStrongAsyncPinned`|<span data-ttu-id="61c5d-114">来自对象句柄表的异步固定对象。</span><span class="sxs-lookup"><span data-stu-id="61c5d-114">An asynchronous pinned object from the object handle table.</span></span>|  
|`CorHandleStrongSizedByref`|<span data-ttu-id="61c5d-115">在垃圾回收时间保留所有对象和对象根的集体闭合的近似大小的强句柄。</span><span class="sxs-lookup"><span data-stu-id="61c5d-115">A strong handle that keeps an approximate size of the collective closure of all objects and object roots at garbage collection time.</span></span>|  
|`CorReferenceStack`|<span data-ttu-id="61c5d-116">托管堆栈中的引用。</span><span class="sxs-lookup"><span data-stu-id="61c5d-116">A reference from the managed stack.</span></span>|  
|`CorReferenceFinalizer`|<span data-ttu-id="61c5d-117">终结器队列中的引用。</span><span class="sxs-lookup"><span data-stu-id="61c5d-117">A reference from the finalizer queue.</span></span>|  
|<span data-ttu-id="61c5d-118">CorHandleStrongOnly</span><span class="sxs-lookup"><span data-stu-id="61c5d-118">CorHandleStrongOnly</span></span>|<span data-ttu-id="61c5d-119">从句柄表返回仅强引用。</span><span class="sxs-lookup"><span data-stu-id="61c5d-119">Return only strong references from the handle table.</span></span> <span data-ttu-id="61c5d-120">使用此值[icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)仅限方法。</span><span class="sxs-lookup"><span data-stu-id="61c5d-120">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleWeakOnly`|<span data-ttu-id="61c5d-121">从句柄表返回仅弱引用。</span><span class="sxs-lookup"><span data-stu-id="61c5d-121">Return only weak references from the handle table.</span></span> <span data-ttu-id="61c5d-122">使用此值[icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)仅限方法。</span><span class="sxs-lookup"><span data-stu-id="61c5d-122">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleAll`|<span data-ttu-id="61c5d-123">返回句柄表中的所有引用。</span><span class="sxs-lookup"><span data-stu-id="61c5d-123">Return all references from the handle table.</span></span> <span data-ttu-id="61c5d-124">使用此值[icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)仅限方法。</span><span class="sxs-lookup"><span data-stu-id="61c5d-124">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61c5d-125">备注</span><span class="sxs-lookup"><span data-stu-id="61c5d-125">Remarks</span></span>  
 <span data-ttu-id="61c5d-126">`CorGCReferenceType`枚举的使用方式如下：</span><span class="sxs-lookup"><span data-stu-id="61c5d-126">The `CorGCReferenceType` enumeration is used as follows:</span></span>  
  
-   <span data-ttu-id="61c5d-127">值作为`type`字段[COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)结构，它指示根源的引用或句柄。</span><span class="sxs-lookup"><span data-stu-id="61c5d-127">As the value of the `type` field of the [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) structure, it indicates the source of a reference or handle.</span></span>  
  
-   <span data-ttu-id="61c5d-128">作为`types`参数[icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)方法，它指定的句柄要包含在枚举中的类型。</span><span class="sxs-lookup"><span data-stu-id="61c5d-128">As the `types` argument to the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method, it specifies the types of handles to include in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61c5d-129">惠?</span><span class="sxs-lookup"><span data-stu-id="61c5d-129">Requirements</span></span>  
 <span data-ttu-id="61c5d-130">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="61c5d-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61c5d-131">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61c5d-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61c5d-132">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61c5d-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61c5d-133">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61c5d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61c5d-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="61c5d-134">See Also</span></span>  
 [<span data-ttu-id="61c5d-135">调试枚举</span><span class="sxs-lookup"><span data-stu-id="61c5d-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
