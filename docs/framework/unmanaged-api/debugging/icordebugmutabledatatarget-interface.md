---
title: "ICorDebugMutableDataTarget 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 14aad5b3-84ab-4bbc-94e3-1eb92e258d10
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e638b01b30f7969ac3116c6c2725fb4cb3768a68
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmutabledatatarget-interface"></a><span data-ttu-id="e1193-102">ICorDebugMutableDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="e1193-102">ICorDebugMutableDataTarget Interface</span></span>
<span data-ttu-id="e1193-103">扩展[ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)接口以支持可变数据目标。</span><span class="sxs-lookup"><span data-stu-id="e1193-103">Extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1193-104">方法</span><span class="sxs-lookup"><span data-stu-id="e1193-104">Methods</span></span>  
  
|<span data-ttu-id="e1193-105">方法</span><span class="sxs-lookup"><span data-stu-id="e1193-105">Method</span></span>|<span data-ttu-id="e1193-106">描述</span><span class="sxs-lookup"><span data-stu-id="e1193-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1193-107">ContinueStatusChanged 方法</span><span class="sxs-lookup"><span data-stu-id="e1193-107">ContinueStatusChanged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-continuestatuschanged-method.md)|<span data-ttu-id="e1193-108">更改指定线程上未完成的调试事件的延续状态。</span><span class="sxs-lookup"><span data-stu-id="e1193-108">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>|  
|[<span data-ttu-id="e1193-109">SetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="e1193-109">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-setthreadcontext-method.md)|<span data-ttu-id="e1193-110">设置某个线程的上下文（寄存器值）。</span><span class="sxs-lookup"><span data-stu-id="e1193-110">Sets the context (register values) for a thread.</span></span>|  
|[<span data-ttu-id="e1193-111">WriteVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="e1193-111">WriteVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-writevirtual-method.md)|<span data-ttu-id="e1193-112">将内存写入目标进程地址空间。</span><span class="sxs-lookup"><span data-stu-id="e1193-112">Writes memory into the target process address space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1193-113">备注</span><span class="sxs-lookup"><span data-stu-id="e1193-113">Remarks</span></span>  
 <span data-ttu-id="e1193-114">此扩展[ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)通过调试想要修改目标进程 （例如，若要执行实时侵入性调试） 的工具可以实现接口。</span><span class="sxs-lookup"><span data-stu-id="e1193-114">This extension to the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface can be implemented by debugging tools that wish to modify the target process (for example, to perform live invasive debugging).</span></span>  
  
 <span data-ttu-id="e1193-115">如果不实现此接口，或者如果调用这些方法失败，则不会丢失任何基于检测的核心调试功能，从这个意义上来说，所有这些方法都是可选的。</span><span class="sxs-lookup"><span data-stu-id="e1193-115">All of these methods are optional in the sense that no core inspection-based debugging functionality is lost by not implementing this interface or by the failure of calls to these methods.</span></span>  <span data-ttu-id="e1193-116">这些方法中的任何故障 `HRESULT` 都将作为 ICorDebug 方法调用的 `HRESULT`传播。</span><span class="sxs-lookup"><span data-stu-id="e1193-116">Any failure `HRESULT` from these methods will propagate out as the `HRESULT` from the ICorDebug method call.</span></span>  
  
 <span data-ttu-id="e1193-117">请注意，一个 ICorDebug 方法调用可能会导致多个突变，并且没有任何机制可确保是否事务性应用了相关突变（全或无）。</span><span class="sxs-lookup"><span data-stu-id="e1193-117">Note that a single ICorDebug method call may result in multiple mutations, and that there is no mechanism for ensuring related mutations are applied transactionally (all-or-none).</span></span>  <span data-ttu-id="e1193-118">这意味着如果某个突变在其他突变（对于相同的 ICorDebug 调用）成功后失败，则目标进程可能会处于不一致状态，且调试可能变得不可靠。</span><span class="sxs-lookup"><span data-stu-id="e1193-118">This means that if a mutation fails after others (for the same ICorDebug call) have succeeded, the target process may be left in an inconsistent state and debugging may become unreliable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1193-119">惠?</span><span class="sxs-lookup"><span data-stu-id="e1193-119">Requirements</span></span>  
 <span data-ttu-id="e1193-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e1193-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1193-121">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1193-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1193-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1193-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1193-123">**.NET framework 版本：**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1193-123">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1193-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1193-124">See Also</span></span>  
 [<span data-ttu-id="e1193-125">调试接口</span><span class="sxs-lookup"><span data-stu-id="e1193-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="e1193-126">调试</span><span class="sxs-lookup"><span data-stu-id="e1193-126">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
