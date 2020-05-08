---
title: ICorDebugEval 接口
ms.date: 03/30/2017
api_name:
- ICorDebugEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval
helpviewer_keywords:
- ICorDebugEval interface [.NET Framework debugging]
ms.assetid: 3a5c9815-832d-47e1-b7f7-bbba135d7cf1
topic_type:
- apiref
ms.openlocfilehash: f13cd6d6cae5bae0c51674e00f275a2c4853c915
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976221"
---
# <a name="icordebugeval-interface"></a><span data-ttu-id="d33bc-102">ICorDebugEval 接口</span><span class="sxs-lookup"><span data-stu-id="d33bc-102">ICorDebugEval Interface</span></span>

<span data-ttu-id="d33bc-103">提供使调试器能够在正在调试的代码的上下文中执行代码的方法。</span><span class="sxs-lookup"><span data-stu-id="d33bc-103">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d33bc-104">方法</span><span class="sxs-lookup"><span data-stu-id="d33bc-104">Methods</span></span>  
  
|<span data-ttu-id="d33bc-105">方法</span><span class="sxs-lookup"><span data-stu-id="d33bc-105">Method</span></span>|<span data-ttu-id="d33bc-106">说明</span><span class="sxs-lookup"><span data-stu-id="d33bc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d33bc-107">Abort 方法</span><span class="sxs-lookup"><span data-stu-id="d33bc-107">Abort Method</span></span>](icordebugeval-abort-method.md)|<span data-ttu-id="d33bc-108">中止此`ICorDebugEval`对象当前正在执行的计算。</span><span class="sxs-lookup"><span data-stu-id="d33bc-108">Aborts the computation this `ICorDebugEval` object is currently performing.</span></span>|  
|[<span data-ttu-id="d33bc-109">CallFunction 方法</span><span class="sxs-lookup"><span data-stu-id="d33bc-109">CallFunction Method</span></span>](icordebugeval-callfunction-method.md)|<span data-ttu-id="d33bc-110">设置对指定函数的调用。</span><span class="sxs-lookup"><span data-stu-id="d33bc-110">Sets up a call to the specified function.</span></span> <span data-ttu-id="d33bc-111">（在 .NET Framework 版本2.0 中已过时; 请改用[ICorDebugEval2：： CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) 。）</span><span class="sxs-lookup"><span data-stu-id="d33bc-111">(Obsolete in the .NET Framework version 2.0; use [ICorDebugEval2::CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) instead.)</span></span>|  
|[<span data-ttu-id="d33bc-112">CreateValue 方法</span><span class="sxs-lookup"><span data-stu-id="d33bc-112">CreateValue Method</span></span>](icordebugeval-createvalue-method.md)|<span data-ttu-id="d33bc-113">获取一个接口指针，该指针指向指定类型的 "ICorDebugValue" 对象，其初始值为零或 null。</span><span class="sxs-lookup"><span data-stu-id="d33bc-113">Gets an interface pointer to an "ICorDebugValue" object of the specified type, with an initial value of zero or null.</span></span> <span data-ttu-id="d33bc-114">（在 .NET Framework 2.0 中已过时; 请改用[ICorDebugEval2：： CreateValueForType](icordebugeval2-createvaluefortype-method.md) 。）</span><span class="sxs-lookup"><span data-stu-id="d33bc-114">(Obsolete in the .NET Framework 2.0; use [ICorDebugEval2::CreateValueForType](icordebugeval2-createvaluefortype-method.md) instead.)</span></span>|  
|[<span data-ttu-id="d33bc-115">GetResult 方法</span><span class="sxs-lookup"><span data-stu-id="d33bc-115">GetResult Method</span></span>](icordebugeval-getresult-method.md)|<span data-ttu-id="d33bc-116">获取一个`ICorDebugValue`接口指针，该指针指向包含计算结果的。</span><span class="sxs-lookup"><span data-stu-id="d33bc-116">Gets an interface pointer to an `ICorDebugValue` that contains the results of the evaluation.</span></span>|  
|[<span data-ttu-id="d33bc-117">GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="d33bc-117">GetThread Method</span></span>](icordebugeval-getthread-method.md)|<span data-ttu-id="d33bc-118">获取一个接口指针，该指针指向正在执行或将执行此计算的 "ICorDebugThread"。</span><span class="sxs-lookup"><span data-stu-id="d33bc-118">Gets an interface pointer to the "ICorDebugThread" where this evaluation is executing or will execute.</span></span>|  
|[<span data-ttu-id="d33bc-119">IsActive 方法</span><span class="sxs-lookup"><span data-stu-id="d33bc-119">IsActive Method</span></span>](icordebugeval-isactive-method.md)|<span data-ttu-id="d33bc-120">获取一个值，该值指示此`ICorDebugEval`对象当前是否正在执行。</span><span class="sxs-lookup"><span data-stu-id="d33bc-120">Gets a value that indicates whether this `ICorDebugEval` object is currently executing.</span></span>|  
|[<span data-ttu-id="d33bc-121">NewArray 方法</span><span class="sxs-lookup"><span data-stu-id="d33bc-121">NewArray Method</span></span>](icordebugeval-newarray-method.md)|<span data-ttu-id="d33bc-122">分配指定元素类型和维度的新数组。</span><span class="sxs-lookup"><span data-stu-id="d33bc-122">Allocates a new array of the specified element type and dimensions.</span></span> <span data-ttu-id="d33bc-123">（在 .NET Framework 2.0 中已过时; 请改用[ICorDebugEval2：： NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) 。）</span><span class="sxs-lookup"><span data-stu-id="d33bc-123">(Obsolete in the .NET Framework 2.0; use [ICorDebugEval2::NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) instead.)</span></span>|  
|[<span data-ttu-id="d33bc-124">NewObject 方法</span><span class="sxs-lookup"><span data-stu-id="d33bc-124">NewObject Method</span></span>](icordebugeval-newobject-method.md)|<span data-ttu-id="d33bc-125">分配一个新的对象实例，并调用指定的构造函数方法。</span><span class="sxs-lookup"><span data-stu-id="d33bc-125">Allocates a new object instance and calls the specified constructor method.</span></span> <span data-ttu-id="d33bc-126">（在 .NET Framework 2.0 中已过时; 请改用[ICorDebugEval2：： NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md) 。）</span><span class="sxs-lookup"><span data-stu-id="d33bc-126">(Obsolete in the .NET Framework 2.0; use [ICorDebugEval2::NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md) instead.)</span></span>|  
|[<span data-ttu-id="d33bc-127">NewObjectNoConstructor 方法</span><span class="sxs-lookup"><span data-stu-id="d33bc-127">NewObjectNoConstructor Method</span></span>](icordebugeval-newobjectnoconstructor-method.md)|<span data-ttu-id="d33bc-128">分配指定类型的新对象实例，而不尝试调用构造函数方法。</span><span class="sxs-lookup"><span data-stu-id="d33bc-128">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span> <span data-ttu-id="d33bc-129">（在 .NET Framework 2.0 中已过时; 请改用[ICorDebugEval2：： NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md) 。）</span><span class="sxs-lookup"><span data-stu-id="d33bc-129">(Obsolete in the .NET Framework 2.0; use [ICorDebugEval2::NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.)</span></span>|  
|[<span data-ttu-id="d33bc-130">NewString 方法</span><span class="sxs-lookup"><span data-stu-id="d33bc-130">NewString Method</span></span>](icordebugeval-newstring-method.md)|<span data-ttu-id="d33bc-131">使用指定的内容分配新的字符串对象。</span><span class="sxs-lookup"><span data-stu-id="d33bc-131">Allocates a new string object with the specified contents.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d33bc-132">备注</span><span class="sxs-lookup"><span data-stu-id="d33bc-132">Remarks</span></span>  
 <span data-ttu-id="d33bc-133">在`ICorDebugEval`用于执行计算的特定线程的上下文中创建对象。</span><span class="sxs-lookup"><span data-stu-id="d33bc-133">An `ICorDebugEval` object is created in the context of a specific thread that is used to perform the evaluations.</span></span> <span data-ttu-id="d33bc-134">给定计算中使用的所有对象和类型必须位于同一个应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="d33bc-134">All objects and types used in a given evaluation must reside within the same application domain.</span></span> <span data-ttu-id="d33bc-135">该应用程序域不需要与该线程的当前应用程序域相同。</span><span class="sxs-lookup"><span data-stu-id="d33bc-135">That application domain need not be the same as the current application domain of the thread.</span></span> <span data-ttu-id="d33bc-136">评估可以嵌套。</span><span class="sxs-lookup"><span data-stu-id="d33bc-136">Evaluations can be nested.</span></span>  
  
 <span data-ttu-id="d33bc-137">直到调试程序调用[ICorDebugController：： Continue](icordebugcontroller-continue-method.md)并收到[ICorDebugManagedCallback：： EvalComplete](icordebugmanagedcallback-evalcomplete-method.md)回调后，计算的操作才会完成。</span><span class="sxs-lookup"><span data-stu-id="d33bc-137">The evaluation's operations do not complete until the debugger calls [ICorDebugController::Continue](icordebugcontroller-continue-method.md), and then receives an [ICorDebugManagedCallback::EvalComplete](icordebugmanagedcallback-evalcomplete-method.md) callback.</span></span> <span data-ttu-id="d33bc-138">如果需要使用评估功能而不允许其他线程运行，请在调用[ICorDebugController：： Continue](icordebugcontroller-continue-method.md)之前，通过使用[ICorDebugController：： SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md)或[ICorDebugController：： Stop](icordebugcontroller-stop-method.md)挂起线程。</span><span class="sxs-lookup"><span data-stu-id="d33bc-138">If you need to use the evaluation functionality without allowing other threads to run, suspend the threads by using either [ICorDebugController::SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) or [ICorDebugController::Stop](icordebugcontroller-stop-method.md) before calling [ICorDebugController::Continue](icordebugcontroller-continue-method.md).</span></span>  
  
 <span data-ttu-id="d33bc-139">由于正在进行计算时用户代码正在运行，因此可能会发生任何调试事件，包括类加载和断点。</span><span class="sxs-lookup"><span data-stu-id="d33bc-139">Because user code is running when the evaluation is in progress, any debug events can occur, including class loads and breakpoints.</span></span> <span data-ttu-id="d33bc-140">对于这些事件，调试器将接收回拨。</span><span class="sxs-lookup"><span data-stu-id="d33bc-140">The debugger will receive callbacks, as normal, for these events.</span></span> <span data-ttu-id="d33bc-141">评估的状态将被视为正常程序状态的一部分。</span><span class="sxs-lookup"><span data-stu-id="d33bc-141">The state of the evaluation will be seen as part of the inspection of the normal program state.</span></span> <span data-ttu-id="d33bc-142">堆栈链将是一个`CHAIN_FUNC_EVAL`链（请参阅 "CorDebugStepReason" 枚举和[ICorDebugChain：： GetReason](icordebugchain-getreason-method.md)方法）。</span><span class="sxs-lookup"><span data-stu-id="d33bc-142">The stack chain will be a `CHAIN_FUNC_EVAL` chain (see the "CorDebugStepReason" enumeration and the [ICorDebugChain::GetReason](icordebugchain-getreason-method.md) method).</span></span> <span data-ttu-id="d33bc-143">完整的调试器 API 将继续正常运行。</span><span class="sxs-lookup"><span data-stu-id="d33bc-143">The full debugger API will continue to operate as normal.</span></span>  
  
 <span data-ttu-id="d33bc-144">如果发生死锁或无限循环，用户代码可能永远无法完成。</span><span class="sxs-lookup"><span data-stu-id="d33bc-144">If a deadlocked or infinite looping situation arises, the user code may never complete.</span></span> <span data-ttu-id="d33bc-145">在这种情况下，必须在恢复程序之前调用[ICorDebugEval：： Abort](icordebugeval-abort-method.md) 。</span><span class="sxs-lookup"><span data-stu-id="d33bc-145">In such a case, you must call [ICorDebugEval::Abort](icordebugeval-abort-method.md) before resuming the program.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d33bc-146">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="d33bc-146">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d33bc-147">要求</span><span class="sxs-lookup"><span data-stu-id="d33bc-147">Requirements</span></span>  
 <span data-ttu-id="d33bc-148">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d33bc-148">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d33bc-149">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d33bc-149">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d33bc-150">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d33bc-150">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d33bc-151">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d33bc-151">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d33bc-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d33bc-152">See also</span></span>

- [<span data-ttu-id="d33bc-153">调试接口</span><span class="sxs-lookup"><span data-stu-id="d33bc-153">Debugging Interfaces</span></span>](debugging-interfaces.md)
