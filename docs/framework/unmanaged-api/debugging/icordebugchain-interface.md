---
title: ICorDebugChain 接口 1
ms.date: 03/30/2017
api_name:
- ICorDebugChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain
helpviewer_keywords:
- ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0bb716f1ad4087642a76dc84266ec6d3f46c1ae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54571199"
---
# <a name="icordebugchain-interface1"></a><span data-ttu-id="372eb-102">ICorDebugChain 接口 1</span><span class="sxs-lookup"><span data-stu-id="372eb-102">ICorDebugChain Interface1</span></span>
<span data-ttu-id="372eb-103">表示一个物理或逻辑调用堆栈段。</span><span class="sxs-lookup"><span data-stu-id="372eb-103">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="372eb-104">方法</span><span class="sxs-lookup"><span data-stu-id="372eb-104">Methods</span></span>  
  
|<span data-ttu-id="372eb-105">方法</span><span class="sxs-lookup"><span data-stu-id="372eb-105">Method</span></span>|<span data-ttu-id="372eb-106">描述</span><span class="sxs-lookup"><span data-stu-id="372eb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="372eb-107">EnumerateFrames 方法</span><span class="sxs-lookup"><span data-stu-id="372eb-107">EnumerateFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|<span data-ttu-id="372eb-108">获取一个枚举器包含在链中的所有托管的堆栈帧并从最新帧开始。</span><span class="sxs-lookup"><span data-stu-id="372eb-108">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="372eb-109">GetActiveFrame 方法</span><span class="sxs-lookup"><span data-stu-id="372eb-109">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|<span data-ttu-id="372eb-110">获取活动 (即，最新) 链上的帧。</span><span class="sxs-lookup"><span data-stu-id="372eb-110">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="372eb-111">GetCallee 方法</span><span class="sxs-lookup"><span data-stu-id="372eb-111">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|<span data-ttu-id="372eb-112">获取此链调用链。</span><span class="sxs-lookup"><span data-stu-id="372eb-112">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="372eb-113">GetCaller 方法</span><span class="sxs-lookup"><span data-stu-id="372eb-113">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|<span data-ttu-id="372eb-114">获取调用此链的链。</span><span class="sxs-lookup"><span data-stu-id="372eb-114">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="372eb-115">GetContext 方法</span><span class="sxs-lookup"><span data-stu-id="372eb-115">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|<span data-ttu-id="372eb-116">未实现。</span><span class="sxs-lookup"><span data-stu-id="372eb-116">Not implemented.</span></span>|  
|[<span data-ttu-id="372eb-117">GetNext 方法</span><span class="sxs-lookup"><span data-stu-id="372eb-117">GetNext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|<span data-ttu-id="372eb-118">获取线程的下一帧链。</span><span class="sxs-lookup"><span data-stu-id="372eb-118">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="372eb-119">GetPrevious 方法</span><span class="sxs-lookup"><span data-stu-id="372eb-119">GetPrevious Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|<span data-ttu-id="372eb-120">获取线程的上一帧链。</span><span class="sxs-lookup"><span data-stu-id="372eb-120">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="372eb-121">GetReason 方法</span><span class="sxs-lookup"><span data-stu-id="372eb-121">GetReason Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|<span data-ttu-id="372eb-122">获取生成此调用链的原因。</span><span class="sxs-lookup"><span data-stu-id="372eb-122">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="372eb-123">GetRegisterSet 方法</span><span class="sxs-lookup"><span data-stu-id="372eb-123">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|<span data-ttu-id="372eb-124">获取为此证书链的活动部分设置的寄存器。</span><span class="sxs-lookup"><span data-stu-id="372eb-124">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="372eb-125">GetStackRange 方法</span><span class="sxs-lookup"><span data-stu-id="372eb-125">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|<span data-ttu-id="372eb-126">获取此链堆栈段的地址范围。</span><span class="sxs-lookup"><span data-stu-id="372eb-126">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="372eb-127">GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="372eb-127">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|<span data-ttu-id="372eb-128">获取此调用链的物理线程的一部分。</span><span class="sxs-lookup"><span data-stu-id="372eb-128">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="372eb-129">IsManaged 方法</span><span class="sxs-lookup"><span data-stu-id="372eb-129">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|<span data-ttu-id="372eb-130">获取一个值，该值指示此链是否正在运行托管的代码。</span><span class="sxs-lookup"><span data-stu-id="372eb-130">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="372eb-131">备注</span><span class="sxs-lookup"><span data-stu-id="372eb-131">Remarks</span></span>  
 <span data-ttu-id="372eb-132">在一个链中的堆栈帧占据相邻的堆栈空间，并共享相同的线程和上下文。</span><span class="sxs-lookup"><span data-stu-id="372eb-132">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="372eb-133">链可以表示任一托管或非托管代码链。</span><span class="sxs-lookup"><span data-stu-id="372eb-133">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="372eb-134">一个空`ICorDebugChain`实例表示的非托管的代码链。</span><span class="sxs-lookup"><span data-stu-id="372eb-134">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="372eb-135">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="372eb-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="372eb-136">要求</span><span class="sxs-lookup"><span data-stu-id="372eb-136">Requirements</span></span>  
 <span data-ttu-id="372eb-137">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="372eb-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="372eb-138">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="372eb-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="372eb-139">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="372eb-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="372eb-140">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="372eb-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="372eb-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="372eb-141">See also</span></span>
- [<span data-ttu-id="372eb-142">调试接口</span><span class="sxs-lookup"><span data-stu-id="372eb-142">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
