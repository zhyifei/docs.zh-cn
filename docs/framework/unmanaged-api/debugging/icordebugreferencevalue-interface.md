---
title: ICorDebugReferenceValue 接口
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue
helpviewer_keywords:
- ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type:
- apiref
ms.openlocfilehash: 2efba22b4ec372c5ddedd4982a29d66945d3511c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792133"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="48484-102">ICorDebugReferenceValue 接口</span><span class="sxs-lookup"><span data-stu-id="48484-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="48484-103">提供管理作为对对象的引用的值的方法。</span><span class="sxs-lookup"><span data-stu-id="48484-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="48484-104">（也就是说，此接口提供管理指针的方法。）此接口实现 "ICorDebugValue"。</span><span class="sxs-lookup"><span data-stu-id="48484-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="48484-105">方法</span><span class="sxs-lookup"><span data-stu-id="48484-105">Methods</span></span>  
  
|<span data-ttu-id="48484-106">方法</span><span class="sxs-lookup"><span data-stu-id="48484-106">Method</span></span>|<span data-ttu-id="48484-107">描述</span><span class="sxs-lookup"><span data-stu-id="48484-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="48484-108">Dereference 方法</span><span class="sxs-lookup"><span data-stu-id="48484-108">Dereference Method</span></span>](icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="48484-109">获取所引用的对象。</span><span class="sxs-lookup"><span data-stu-id="48484-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="48484-110">DereferenceStrong 方法</span><span class="sxs-lookup"><span data-stu-id="48484-110">DereferenceStrong Method</span></span>](icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="48484-111">未实现。</span><span class="sxs-lookup"><span data-stu-id="48484-111">Not implemented.</span></span> <span data-ttu-id="48484-112">请勿调用此方法。</span><span class="sxs-lookup"><span data-stu-id="48484-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="48484-113">GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="48484-113">GetValue Method</span></span>](icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="48484-114">获取所引用对象的当前内存地址。</span><span class="sxs-lookup"><span data-stu-id="48484-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="48484-115">IsNull 方法</span><span class="sxs-lookup"><span data-stu-id="48484-115">IsNull Method</span></span>](icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="48484-116">获取一个值，该值指示此 `ICorDebugReferenceValue` 是否为 null 值，在这种情况下，`ICorDebugReferenceValue` 不指向对象。</span><span class="sxs-lookup"><span data-stu-id="48484-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="48484-117">SetValue 方法</span><span class="sxs-lookup"><span data-stu-id="48484-117">SetValue Method</span></span>](icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="48484-118">设置当前内存地址。</span><span class="sxs-lookup"><span data-stu-id="48484-118">Sets the current memory address.</span></span> <span data-ttu-id="48484-119">也就是说，此方法会将此 `ICorDebugReferenceValue` 设置为指向某个对象。</span><span class="sxs-lookup"><span data-stu-id="48484-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48484-120">备注</span><span class="sxs-lookup"><span data-stu-id="48484-120">Remarks</span></span>  
 <span data-ttu-id="48484-121">当继续调试的进程时，公共语言运行时（CLR）可能会对对象进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="48484-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="48484-122">垃圾回收可能会在内存中移动对象。</span><span class="sxs-lookup"><span data-stu-id="48484-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="48484-123">`ICorDebugReferenceValue` 将与垃圾回收一起合作，以便在垃圾回收后更新其信息，或者在垃圾回收之前隐式地将其无效。</span><span class="sxs-lookup"><span data-stu-id="48484-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="48484-124">继续调试的进程后，`ICorDebugReferenceValue` 对象可能会隐式失效。</span><span class="sxs-lookup"><span data-stu-id="48484-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="48484-125">派生的 "ICorDebugHandleValue" 在显式发布或公开之前不会失效。</span><span class="sxs-lookup"><span data-stu-id="48484-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="48484-126">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="48484-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48484-127">需求</span><span class="sxs-lookup"><span data-stu-id="48484-127">Requirements</span></span>  
 <span data-ttu-id="48484-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="48484-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48484-129">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48484-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48484-130">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48484-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48484-131">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48484-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48484-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48484-132">See also</span></span>

- [<span data-ttu-id="48484-133">调试接口</span><span class="sxs-lookup"><span data-stu-id="48484-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
