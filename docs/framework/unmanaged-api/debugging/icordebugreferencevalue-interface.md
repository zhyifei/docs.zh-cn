---
title: "ICorDebugReferenceValue 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugReferenceValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugReferenceValue
helpviewer_keywords: ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ac6260a601f7fdacf84034a6ae83c9423fafa11
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugreferencevalue-interface1"></a><span data-ttu-id="6bf97-102">ICorDebugReferenceValue 接口 1</span><span class="sxs-lookup"><span data-stu-id="6bf97-102">ICorDebugReferenceValue Interface1</span></span>
<span data-ttu-id="6bf97-103">提供管理是对一个对象的引用的值的方法。</span><span class="sxs-lookup"><span data-stu-id="6bf97-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="6bf97-104">（也就是说，此接口提供管理指针的方法。）此接口实现"ICorDebugValue"。</span><span class="sxs-lookup"><span data-stu-id="6bf97-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6bf97-105">方法</span><span class="sxs-lookup"><span data-stu-id="6bf97-105">Methods</span></span>  
  
|<span data-ttu-id="6bf97-106">方法</span><span class="sxs-lookup"><span data-stu-id="6bf97-106">Method</span></span>|<span data-ttu-id="6bf97-107">描述</span><span class="sxs-lookup"><span data-stu-id="6bf97-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6bf97-108">Dereference 方法</span><span class="sxs-lookup"><span data-stu-id="6bf97-108">Dereference Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="6bf97-109">获取引用的对象。</span><span class="sxs-lookup"><span data-stu-id="6bf97-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="6bf97-110">DereferenceStrong 方法</span><span class="sxs-lookup"><span data-stu-id="6bf97-110">DereferenceStrong Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="6bf97-111">未实现。</span><span class="sxs-lookup"><span data-stu-id="6bf97-111">Not implemented.</span></span> <span data-ttu-id="6bf97-112">请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="6bf97-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="6bf97-113">GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="6bf97-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="6bf97-114">获取被引用的对象的当前内存地址。</span><span class="sxs-lookup"><span data-stu-id="6bf97-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="6bf97-115">IsNull 方法</span><span class="sxs-lookup"><span data-stu-id="6bf97-115">IsNull Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="6bf97-116">获取一个值，该值指示是否这`ICorDebugReferenceValue`在这种情况下为 null 值，`ICorDebugReferenceValue`不指向的对象。</span><span class="sxs-lookup"><span data-stu-id="6bf97-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="6bf97-117">SetValue 方法</span><span class="sxs-lookup"><span data-stu-id="6bf97-117">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="6bf97-118">设置当前的内存地址。</span><span class="sxs-lookup"><span data-stu-id="6bf97-118">Sets the current memory address.</span></span> <span data-ttu-id="6bf97-119">此方法，即设置此`ICorDebugReferenceValue`要指向的对象。</span><span class="sxs-lookup"><span data-stu-id="6bf97-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6bf97-120">备注</span><span class="sxs-lookup"><span data-stu-id="6bf97-120">Remarks</span></span>  
 <span data-ttu-id="6bf97-121">公共语言运行时 (CLR) 调试的进程将继续运行，可能执行对象的垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="6bf97-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="6bf97-122">垃圾回收可能移动对象在内存中。</span><span class="sxs-lookup"><span data-stu-id="6bf97-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="6bf97-123">`ICorDebugReferenceValue`将协同与垃圾回收，以便垃圾回收之后，更新其信息或将在垃圾回收之前隐式失效。</span><span class="sxs-lookup"><span data-stu-id="6bf97-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="6bf97-124">`ICorDebugReferenceValue`调试的进程一直之后，对象可能会隐式失效。</span><span class="sxs-lookup"><span data-stu-id="6bf97-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="6bf97-125">不会失效派生"ICorDebugHandleValue"，直到显式释放或公开它。</span><span class="sxs-lookup"><span data-stu-id="6bf97-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6bf97-126">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="6bf97-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bf97-127">惠?</span><span class="sxs-lookup"><span data-stu-id="6bf97-127">Requirements</span></span>  
 <span data-ttu-id="6bf97-128">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6bf97-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bf97-129">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6bf97-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6bf97-130">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6bf97-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6bf97-131">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bf97-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bf97-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="6bf97-132">See Also</span></span>  
    
    
 [<span data-ttu-id="6bf97-133">调试接口</span><span class="sxs-lookup"><span data-stu-id="6bf97-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
