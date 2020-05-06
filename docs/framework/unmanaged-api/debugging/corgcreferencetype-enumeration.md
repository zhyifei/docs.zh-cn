---
title: CorGCReferenceType 枚举
ms.date: 03/30/2017
api_name:
- CorGCReferenceType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorGCReferenceType
helpviewer_keywords:
- CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type:
- apiref
ms.openlocfilehash: d156f103c3812c91da380e722a1c6c95d621df4c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860913"
---
# <a name="corgcreferencetype-enumeration"></a><span data-ttu-id="8cf40-102">CorGCReferenceType 枚举</span><span class="sxs-lookup"><span data-stu-id="8cf40-102">CorGCReferenceType Enumeration</span></span>
<span data-ttu-id="8cf40-103">标识要进行垃圾回收的对象的源。</span><span class="sxs-lookup"><span data-stu-id="8cf40-103">Identifies the source of an object to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cf40-104">语法</span><span class="sxs-lookup"><span data-stu-id="8cf40-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="8cf40-105">成员</span><span class="sxs-lookup"><span data-stu-id="8cf40-105">Members</span></span>  
  
|<span data-ttu-id="8cf40-106">成员名称</span><span class="sxs-lookup"><span data-stu-id="8cf40-106">Member name</span></span>|<span data-ttu-id="8cf40-107">说明</span><span class="sxs-lookup"><span data-stu-id="8cf40-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorHandleStrong`|<span data-ttu-id="8cf40-108">来自对象句柄表的强引用的句柄。</span><span class="sxs-lookup"><span data-stu-id="8cf40-108">A handle to a strong reference from the object handle table.</span></span>|  
|`CorHandleStrongPinning`|<span data-ttu-id="8cf40-109">来自对象句柄表的固定强引用的句柄。</span><span class="sxs-lookup"><span data-stu-id="8cf40-109">A handle to a pinned strong reference from the object handle table.</span></span>|  
|`CorHandleWeakShort`|<span data-ttu-id="8cf40-110">来自对象句柄表的弱引用的句柄。</span><span class="sxs-lookup"><span data-stu-id="8cf40-110">A handle to a weak reference from the object handle table.</span></span>|  
|`CorHandleWeakRefCount`|<span data-ttu-id="8cf40-111">对象句柄表中弱引用计数对象的句柄。</span><span class="sxs-lookup"><span data-stu-id="8cf40-111">A handle to a weak reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongRefCount`|<span data-ttu-id="8cf40-112">对象句柄表中的引用计数对象的句柄。</span><span class="sxs-lookup"><span data-stu-id="8cf40-112">A handle to a reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongDependent`|<span data-ttu-id="8cf40-113">来自对象句柄表的依赖对象的句柄。</span><span class="sxs-lookup"><span data-stu-id="8cf40-113">A handle to a dependent object from the object handle table.</span></span>|  
|`CorHandleStrongAsyncPinned`|<span data-ttu-id="8cf40-114">来自对象句柄表的异步固定对象。</span><span class="sxs-lookup"><span data-stu-id="8cf40-114">An asynchronous pinned object from the object handle table.</span></span>|  
|`CorHandleStrongSizedByref`|<span data-ttu-id="8cf40-115">在垃圾回收时间保留所有对象和对象根的集体闭合的近似大小的强句柄。</span><span class="sxs-lookup"><span data-stu-id="8cf40-115">A strong handle that keeps an approximate size of the collective closure of all objects and object roots at garbage collection time.</span></span>|  
|`CorReferenceStack`|<span data-ttu-id="8cf40-116">托管堆栈中的引用。</span><span class="sxs-lookup"><span data-stu-id="8cf40-116">A reference from the managed stack.</span></span>|  
|`CorReferenceFinalizer`|<span data-ttu-id="8cf40-117">终结器队列中的引用。</span><span class="sxs-lookup"><span data-stu-id="8cf40-117">A reference from the finalizer queue.</span></span>|  
|<span data-ttu-id="8cf40-118">CorHandleStrongOnly</span><span class="sxs-lookup"><span data-stu-id="8cf40-118">CorHandleStrongOnly</span></span>|<span data-ttu-id="8cf40-119">仅返回句柄表中的强引用。</span><span class="sxs-lookup"><span data-stu-id="8cf40-119">Return only strong references from the handle table.</span></span> <span data-ttu-id="8cf40-120">此值仅由[ICorDebugProcess5：： EnumerateHandles](icordebugprocess5-enumeratehandles-method.md)方法使用。</span><span class="sxs-lookup"><span data-stu-id="8cf40-120">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleWeakOnly`|<span data-ttu-id="8cf40-121">仅返回句柄表中的弱引用。</span><span class="sxs-lookup"><span data-stu-id="8cf40-121">Return only weak references from the handle table.</span></span> <span data-ttu-id="8cf40-122">此值仅由[ICorDebugProcess5：： EnumerateHandles](icordebugprocess5-enumeratehandles-method.md)方法使用。</span><span class="sxs-lookup"><span data-stu-id="8cf40-122">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleAll`|<span data-ttu-id="8cf40-123">返回句柄表中的所有引用。</span><span class="sxs-lookup"><span data-stu-id="8cf40-123">Return all references from the handle table.</span></span> <span data-ttu-id="8cf40-124">此值仅由[ICorDebugProcess5：： EnumerateHandles](icordebugprocess5-enumeratehandles-method.md)方法使用。</span><span class="sxs-lookup"><span data-stu-id="8cf40-124">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8cf40-125">备注</span><span class="sxs-lookup"><span data-stu-id="8cf40-125">Remarks</span></span>  
 <span data-ttu-id="8cf40-126">`CorGCReferenceType`枚举的使用方式如下：</span><span class="sxs-lookup"><span data-stu-id="8cf40-126">The `CorGCReferenceType` enumeration is used as follows:</span></span>  
  
- <span data-ttu-id="8cf40-127">作为`type` [COR_GC_REFERENCE](cor-gc-reference-structure.md)结构的字段的值，它指示引用或句柄的源。</span><span class="sxs-lookup"><span data-stu-id="8cf40-127">As the value of the `type` field of the [COR_GC_REFERENCE](cor-gc-reference-structure.md) structure, it indicates the source of a reference or handle.</span></span>  
  
- <span data-ttu-id="8cf40-128">作为`types` [ICorDebugProcess5：： EnumerateHandles](icordebugprocess5-enumeratehandles-method.md)方法的参数，它指定要包括在枚举中的句柄的类型。</span><span class="sxs-lookup"><span data-stu-id="8cf40-128">As the `types` argument to the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method, it specifies the types of handles to include in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cf40-129">要求</span><span class="sxs-lookup"><span data-stu-id="8cf40-129">Requirements</span></span>  
 <span data-ttu-id="8cf40-130">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8cf40-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cf40-131">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8cf40-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8cf40-132">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cf40-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cf40-133">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cf40-133">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cf40-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8cf40-134">See also</span></span>

- [<span data-ttu-id="8cf40-135">调试枚举</span><span class="sxs-lookup"><span data-stu-id="8cf40-135">Debugging Enumerations</span></span>](debugging-enumerations.md)
