---
title: "StackSnapshotCallback 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StackSnapshotCallback
api_location: mscorwks.dll
api_type: COM
f1_keywords: StackSnapshotCallback
helpviewer_keywords: StackSnapshotCallback function [.NET Framework profiling]
ms.assetid: d0f235b2-91fe-4f82-b7d5-e5c64186eea8
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 32cf21fb5a76fdec4daa322d53a8eb218ae2f2b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="stacksnapshotcallback-function"></a><span data-ttu-id="fa807-102">StackSnapshotCallback 函数</span><span class="sxs-lookup"><span data-stu-id="fa807-102">StackSnapshotCallback Function</span></span>
<span data-ttu-id="fa807-103">探查器提供了有关每个托管的帧和非托管的帧每次运行在堆栈上的堆栈审核，启动的过程信息，以及[icorprofilerinfo2:: Dostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="fa807-103">Provides the profiler with information about each managed frame and each run of unmanaged frames on the stack during a stack walk, which is initiated by the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa807-104">语法</span><span class="sxs-lookup"><span data-stu-id="fa807-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="fa807-105">参数</span><span class="sxs-lookup"><span data-stu-id="fa807-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="fa807-106">[in]对于运行的非托管的帧; 如果此值为零，是此回调否则为它是托管函数的标识符，此回调可能会个托管帧。</span><span class="sxs-lookup"><span data-stu-id="fa807-106">[in] If this value is zero, this callback is for a run of unmanaged frames; otherwise, it is the identifier of a managed function and this callback is for a managed frame.</span></span>  
  
 `ip`  
 <span data-ttu-id="fa807-107">[in]在框架中的本机代码指令指针的值。</span><span class="sxs-lookup"><span data-stu-id="fa807-107">[in] The value of the native code instruction pointer in the frame.</span></span>  
  
 `frameInfo`  
 <span data-ttu-id="fa807-108">[in]A`COR_PRF_FRAME_INFO`引用有关堆栈帧的信息的值。</span><span class="sxs-lookup"><span data-stu-id="fa807-108">[in] A `COR_PRF_FRAME_INFO` value that references information about the stack frame.</span></span> <span data-ttu-id="fa807-109">此值可用于使用仅在此回调。</span><span class="sxs-lookup"><span data-stu-id="fa807-109">This value is valid for use only during this callback.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="fa807-110">[in]大小`CONTEXT`结构，这通过引用`context`参数。</span><span class="sxs-lookup"><span data-stu-id="fa807-110">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
 `context`  
 <span data-ttu-id="fa807-111">[in]一个指向 Win32`CONTEXT`结构，它表示此帧的 CPU 的状态。</span><span class="sxs-lookup"><span data-stu-id="fa807-111">[in] A pointer to a Win32 `CONTEXT` structure that represents the state of the CPU for this frame.</span></span>  
  
 <span data-ttu-id="fa807-112">`context`参数才有效仅当传入的 COR_PRF_SNAPSHOT_CONTEXT 标志`ICorProfilerInfo2::DoStackSnapshot`。</span><span class="sxs-lookup"><span data-stu-id="fa807-112">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="fa807-113">[in]指向客户端数据，这直接通过传递从`ICorProfilerInfo2::DoStackSnapshot`。</span><span class="sxs-lookup"><span data-stu-id="fa807-113">[in] A pointer to the client data, which is passed straight through from `ICorProfilerInfo2::DoStackSnapshot`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa807-114">备注</span><span class="sxs-lookup"><span data-stu-id="fa807-114">Remarks</span></span>  
 <span data-ttu-id="fa807-115">`StackSnapshotCallback`函数由探查器编写器实现。</span><span class="sxs-lookup"><span data-stu-id="fa807-115">The `StackSnapshotCallback` function is implemented by the profiler writer.</span></span> <span data-ttu-id="fa807-116">你必须限制完成工作的复杂性`StackSnapshotCallback`。</span><span class="sxs-lookup"><span data-stu-id="fa807-116">You must limit the complexity of work done in `StackSnapshotCallback`.</span></span> <span data-ttu-id="fa807-117">例如，在使用`ICorProfilerInfo2::DoStackSnapshot`以异步方式，此目标线程可能会持有锁。</span><span class="sxs-lookup"><span data-stu-id="fa807-117">For example, when using `ICorProfilerInfo2::DoStackSnapshot` in an asynchronous manner, the target thread may be holding locks.</span></span> <span data-ttu-id="fa807-118">如果中的代码`StackSnapshotCallback`需要相同的锁定，死锁无法随之发生。</span><span class="sxs-lookup"><span data-stu-id="fa807-118">If code within `StackSnapshotCallback` requires the same locks, a deadlock could ensue.</span></span>  
  
 <span data-ttu-id="fa807-119">`ICorProfilerInfo2::DoStackSnapshot`方法调用`StackSnapshotCallback`函数一次每个托管帧或第一次每次运行的非托管的帧。</span><span class="sxs-lookup"><span data-stu-id="fa807-119">The `ICorProfilerInfo2::DoStackSnapshot` method calls the `StackSnapshotCallback` function once per managed frame or once per run of unmanaged frames.</span></span> <span data-ttu-id="fa807-120">如果`StackSnapshotCallback`调用探查器可能对于非托管帧的运行时，使用寄存器上下文 (所引用的`context`参数) 来执行其自己的非托管的堆栈审核。</span><span class="sxs-lookup"><span data-stu-id="fa807-120">If `StackSnapshotCallback` is called for a run of unmanaged frames, the profiler may use the register context (referenced by the `context` parameter) to perform its own unmanaged stack walk.</span></span> <span data-ttu-id="fa807-121">在此情况下，Win32`CONTEXT`结构表示中的非托管帧运行最近推入镇的 CPU 状态。</span><span class="sxs-lookup"><span data-stu-id="fa807-121">In this case, the Win32 `CONTEXT` structure represents the CPU state for the most recently pushed frame within the run of unmanaged frames.</span></span> <span data-ttu-id="fa807-122">尽管 Win32`CONTEXT`结构包括所有寄存器的值，但您应依赖于的堆栈指针寄存器、 帧指针寄存器、 指令指针寄存器和非易失的 （即保留） 的值仅整数寄存器。</span><span class="sxs-lookup"><span data-stu-id="fa807-122">Although the Win32 `CONTEXT` structure includes values for all registers, you should rely only on the values of the stack pointer register, frame pointer register, instruction pointer register, and the nonvolatile (that is, preserved) integer registers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa807-123">惠?</span><span class="sxs-lookup"><span data-stu-id="fa807-123">Requirements</span></span>  
 <span data-ttu-id="fa807-124">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fa807-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa807-125">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="fa807-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="fa807-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa807-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa807-127">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa807-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa807-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa807-128">See Also</span></span>  
 [<span data-ttu-id="fa807-129">DoStackSnapshot 方法</span><span class="sxs-lookup"><span data-stu-id="fa807-129">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
 [<span data-ttu-id="fa807-130">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="fa807-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
