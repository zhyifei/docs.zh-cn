---
title: StackSnapshotCallback 函数
ms.date: 03/30/2017
api_name:
- StackSnapshotCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- StackSnapshotCallback
helpviewer_keywords:
- StackSnapshotCallback function [.NET Framework profiling]
ms.assetid: d0f235b2-91fe-4f82-b7d5-e5c64186eea8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 891423661f45a1167d53385e6e0306fb09487278
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198317"
---
# <a name="stacksnapshotcallback-function"></a><span data-ttu-id="3e176-102">StackSnapshotCallback 函数</span><span class="sxs-lookup"><span data-stu-id="3e176-102">StackSnapshotCallback Function</span></span>
<span data-ttu-id="3e176-103">提供有关每个托管的帧和非托管帧的每次运行在堆栈上的堆栈遍历，启动的过程信息，以及探查器[ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="3e176-103">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e176-104">语法</span><span class="sxs-lookup"><span data-stu-id="3e176-104">Syntax</span></span>  
  
```  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e176-105">参数</span><span class="sxs-lookup"><span data-stu-id="3e176-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="3e176-106">[in]如果此值为零，此回叫是运行非托管帧;否则为它是托管函数的标识符，并且此回叫是个托管帧。</span><span class="sxs-lookup"><span data-stu-id="3e176-106">[in] If this value is zero, this callback is for a run of unmanaged frames; otherwise, it is the identifier of a managed function and this callback is for a managed frame.</span></span>  
  
 `ip`  
 <span data-ttu-id="3e176-107">[in]在框架中的本机代码指令指针的值。</span><span class="sxs-lookup"><span data-stu-id="3e176-107">[in] The value of the native code instruction pointer in the frame.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="3e176-108">[in]一个`COR_PRF_FRAME_INFO`引用有关堆栈帧的信息的值。</span><span class="sxs-lookup"><span data-stu-id="3e176-108">[in] A `COR_PRF_FRAME_INFO` value that references information about the stack frame.</span></span> <span data-ttu-id="3e176-109">仅在此回调期间，此值是有效使用。</span><span class="sxs-lookup"><span data-stu-id="3e176-109">This value is valid for use only during this callback.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="3e176-110">[in]大小`CONTEXT`结构，它引用的`context`参数。</span><span class="sxs-lookup"><span data-stu-id="3e176-110">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
 `context`  
 <span data-ttu-id="3e176-111">[in]一个指向 Win32`CONTEXT`结构，它表示此帧的 CPU 的状态。</span><span class="sxs-lookup"><span data-stu-id="3e176-111">[in] A pointer to a Win32 `CONTEXT` structure that represents the state of the CPU for this frame.</span></span>  
  
 <span data-ttu-id="3e176-112">`context`参数才有效，仅当传入的 COR_PRF_SNAPSHOT_CONTEXT 标志`ICorProfilerInfo2::DoStackSnapshot`。</span><span class="sxs-lookup"><span data-stu-id="3e176-112">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="3e176-113">[in]指向客户端数据，直接通过传递从`ICorProfilerInfo2::DoStackSnapshot`。</span><span class="sxs-lookup"><span data-stu-id="3e176-113">[in] A pointer to the client data, which is passed straight through from `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e176-114">备注</span><span class="sxs-lookup"><span data-stu-id="3e176-114">Remarks</span></span>  
 <span data-ttu-id="3e176-115">`StackSnapshotCallback`由探查器编写器实现函数。</span><span class="sxs-lookup"><span data-stu-id="3e176-115">The `StackSnapshotCallback` function is implemented by the profiler writer.</span></span> <span data-ttu-id="3e176-116">您必须限制中完成工作的复杂性`StackSnapshotCallback`。</span><span class="sxs-lookup"><span data-stu-id="3e176-116">You must limit the complexity of work done in `StackSnapshotCallback`.</span></span> <span data-ttu-id="3e176-117">例如，在使用`ICorProfilerInfo2::DoStackSnapshot`以异步方式，，目标线程可能会持有锁。</span><span class="sxs-lookup"><span data-stu-id="3e176-117">For example, when using `ICorProfilerInfo2::DoStackSnapshot` in an asynchronous manner, the target thread may be holding locks.</span></span> <span data-ttu-id="3e176-118">如果中的代码`StackSnapshotCallback`需要同一个锁死锁可能会随之发生。</span><span class="sxs-lookup"><span data-stu-id="3e176-118">If code within `StackSnapshotCallback` requires the same locks, a deadlock could ensue.</span></span>  
  
 <span data-ttu-id="3e176-119">`ICorProfilerInfo2::DoStackSnapshot`方法调用`StackSnapshotCallback`函数一次每个托管帧或一次每次运行的非托管帧。</span><span class="sxs-lookup"><span data-stu-id="3e176-119">The `ICorProfilerInfo2::DoStackSnapshot` method calls the `StackSnapshotCallback` function once per managed frame or once per run of unmanaged frames.</span></span> <span data-ttu-id="3e176-120">如果`StackSnapshotCallback`称为非托管帧的运行，探查器可能使用寄存器上下文 (所引用的`context`参数) 来执行其自己的非托管的堆栈遍历。</span><span class="sxs-lookup"><span data-stu-id="3e176-120">If `StackSnapshotCallback` is called for a run of unmanaged frames, the profiler may use the register context (referenced by the `context` parameter) to perform its own unmanaged stack walk.</span></span> <span data-ttu-id="3e176-121">在此情况下，Win32`CONTEXT`结构表示非托管帧的运行中最近推送的帧的 CPU 的状态。</span><span class="sxs-lookup"><span data-stu-id="3e176-121">In this case, the Win32 `CONTEXT` structure represents the CPU state for the most recently pushed frame within the run of unmanaged frames.</span></span> <span data-ttu-id="3e176-122">尽管 Win32`CONTEXT`结构包括所有寄存器的值，但您应依赖于的堆栈指针寄存器、 帧指针寄存器、 指令指针寄存器和非易失性 （即保留） 的值仅整数寄存器。</span><span class="sxs-lookup"><span data-stu-id="3e176-122">Although the Win32 `CONTEXT` structure includes values for all registers, you should rely only on the values of the stack pointer register, frame pointer register, instruction pointer register, and the nonvolatile (that is, preserved) integer registers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e176-123">要求</span><span class="sxs-lookup"><span data-stu-id="3e176-123">Requirements</span></span>  
 <span data-ttu-id="3e176-124">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3e176-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e176-125">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="3e176-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="3e176-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e176-126">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3e176-127">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="3e176-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3e176-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e176-128">See also</span></span>

- [<span data-ttu-id="3e176-129">DoStackSnapshot 方法</span><span class="sxs-lookup"><span data-stu-id="3e176-129">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="3e176-130">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="3e176-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
