---
title: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
ms.assetid: f0621465-b84f-40ab-a4e5-56a7abc776a7
topic_type:
- apiref
ms.openlocfilehash: 3e07d2b61e85bb626613c40832c1a6aa499ef248
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868494"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3-method"></a><span data-ttu-id="86e94-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 方法</span><span class="sxs-lookup"><span data-stu-id="86e94-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 Method</span></span>
<span data-ttu-id="86e94-103">指定将在[FunctionEnter3](functionenter3-function.md)、 [FunctionLeave3](functionleave3-function.md)和[FunctionTailcall3](functiontailcall3-function.md)函数上调用的探查器实现函数。</span><span class="sxs-lookup"><span data-stu-id="86e94-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86e94-104">语法</span><span class="sxs-lookup"><span data-stu-id="86e94-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3(  
            [in] FunctionEnter3    *pFuncEnter3,  
            [in] FunctionLeave3    *pFuncLeave3,  
            [in] FunctionTailcall3 *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86e94-105">参数</span><span class="sxs-lookup"><span data-stu-id="86e94-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="86e94-106">中指向要用作 `FunctionEnter3` 回调的实现的指针。</span><span class="sxs-lookup"><span data-stu-id="86e94-106">[in] A pointer to the implementation to be used as the `FunctionEnter3` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="86e94-107">中指向要用作 `FunctionLeave3` 回调的实现的指针。</span><span class="sxs-lookup"><span data-stu-id="86e94-107">[in] A pointer to the implementation to be used as the `FunctionLeave3` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="86e94-108">中指向要用作 `FunctionTailcall3` 回调的实现的指针。</span><span class="sxs-lookup"><span data-stu-id="86e94-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86e94-109">备注</span><span class="sxs-lookup"><span data-stu-id="86e94-109">Remarks</span></span>  
 <span data-ttu-id="86e94-110">[FunctionEnter3](functionenter3-function.md)、 [FunctionLeave3](functionleave3-function.md)和[FunctionTailcall3](functiontailcall3-function.md)挂钩不提供堆栈帧和参数检查。</span><span class="sxs-lookup"><span data-stu-id="86e94-110">[FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md) hooks do not provide stack frame and argument inspection.</span></span> <span data-ttu-id="86e94-111">若要访问该信息，必须设置 `COR_PRF_ENABLE_FUNCTION_ARGS`、`COR_PRF_ENABLE_FUNCTION_RETVAL`和/或 `COR_PRF_ENABLE_FRAME_INFO` 标志。</span><span class="sxs-lookup"><span data-stu-id="86e94-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or  `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="86e94-112">探查器可以使用[ICorProfilerInfo：： SetEventMask](icorprofilerinfo-seteventmask-method.md)方法来设置事件标志，然后使用[ICorProfilerInfo3：： SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)方法来注册此函数的实现。</span><span class="sxs-lookup"><span data-stu-id="86e94-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="86e94-113">一次只能有一组回调处于活动状态，最新版本优先。</span><span class="sxs-lookup"><span data-stu-id="86e94-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="86e94-114">因此，如果探查器同时调用[SetEnterLeaveFunctionHooks2 方法](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)和 `SetEnterLeaveFunctionHooks3` 方法，则使用 `SetEnterLeaveFunctionHooks3`。</span><span class="sxs-lookup"><span data-stu-id="86e94-114">Therefore, if a profiler calls both the [SetEnterLeaveFunctionHooks2 Method](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and the `SetEnterLeaveFunctionHooks3` method, `SetEnterLeaveFunctionHooks3` is used.</span></span>  
  
 <span data-ttu-id="86e94-115">只能从探查器的[ICorProfilerCallback：： Initialize](icorprofilercallback-initialize-method.md)回调调用 `SetEnterLeaveFunctionHooks3` 方法。</span><span class="sxs-lookup"><span data-stu-id="86e94-115">The `SetEnterLeaveFunctionHooks3` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86e94-116">需求</span><span class="sxs-lookup"><span data-stu-id="86e94-116">Requirements</span></span>  
 <span data-ttu-id="86e94-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="86e94-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86e94-118">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="86e94-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="86e94-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86e94-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86e94-120">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86e94-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86e94-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86e94-121">See also</span></span>

- [<span data-ttu-id="86e94-122">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="86e94-122">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="86e94-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="86e94-123">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="86e94-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="86e94-124">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="86e94-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="86e94-125">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="86e94-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="86e94-126">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="86e94-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="86e94-127">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="86e94-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="86e94-128">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="86e94-129">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="86e94-129">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
- [<span data-ttu-id="86e94-130">ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="86e94-130">ICorProfilerInfo3</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="86e94-131">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="86e94-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="86e94-132">分析</span><span class="sxs-lookup"><span data-stu-id="86e94-132">Profiling</span></span>](index.md)
