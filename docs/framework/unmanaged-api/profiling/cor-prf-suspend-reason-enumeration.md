---
title: "COR_PRF_SUSPEND_REASON 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- COR_PRF_SUSPEND_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SUSPEND_REASON
helpviewer_keywords:
- COR_PRF_SUSPEND_REASON enumeration [.NET Framework profiling]
ms.assetid: 75594833-bed3-47b2-a426-b75c5fe6fbcf
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 713360b3cdc30ce7bca3e0df115016d66e59b0df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corprfsuspendreason-enumeration"></a><span data-ttu-id="916ae-102">COR_PRF_SUSPEND_REASON 枚举</span><span class="sxs-lookup"><span data-stu-id="916ae-102">COR_PRF_SUSPEND_REASON Enumeration</span></span>
<span data-ttu-id="916ae-103">指示运行时挂起的原因。</span><span class="sxs-lookup"><span data-stu-id="916ae-103">Indicates the reason that the runtime is suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="916ae-104">语法</span><span class="sxs-lookup"><span data-stu-id="916ae-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_SUSPEND_OTHER                   = 0x00,  
    COR_PRF_SUSPEND_FOR_GC                  = 0x01,  
    COR_PRF_SUSPEND_FOR_APPDOMAIN_SHUTDOWN  = 0x02,  
    COR_PRF_SUSPEND_FOR_CODE_PITCHING       = 0x03,  
    COR_PRF_SUSPEND_FOR_SHUTDOWN            = 0x04,  
    COR_PRF_SUSPEND_FOR_INPROC_DEBUGGER     = 0x06,  
    COR_PRF_SUSPEND_FOR_GC_PREP             = 0x07,    COR_PRF_SUSPEND_FOR_REJIT               = 8  
} COR_PRF_SUSPEND_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="916ae-105">成员</span><span class="sxs-lookup"><span data-stu-id="916ae-105">Members</span></span>  
  
|<span data-ttu-id="916ae-106">成员</span><span class="sxs-lookup"><span data-stu-id="916ae-106">Member</span></span>|<span data-ttu-id="916ae-107">描述</span><span class="sxs-lookup"><span data-stu-id="916ae-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|<span data-ttu-id="916ae-108">运行时挂起，原因不明。</span><span class="sxs-lookup"><span data-stu-id="916ae-108">The runtime is suspended for an unspecified reason.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|<span data-ttu-id="916ae-109">运行时挂起，以便垃圾回收请求提供服务。</span><span class="sxs-lookup"><span data-stu-id="916ae-109">The runtime is suspended to service a garbage collection request.</span></span><br /><br /> <span data-ttu-id="916ae-110">垃圾回收集合相关回调之间发生[icorprofilercallback:: Runtimesuspendfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)和[icorprofilercallback:: Runtimeresumestarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="916ae-110">The garbage collection-related callbacks occur between the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|<span data-ttu-id="916ae-111">运行时挂起，以便`AppDomain`可以关闭。</span><span class="sxs-lookup"><span data-stu-id="916ae-111">The runtime is suspended so that an `AppDomain` can be shut down.</span></span><br /><br /> <span data-ttu-id="916ae-112">当挂起时运行时，运行时将确定哪些线程正在`AppDomain`，它是被关闭，然后将它们设置为继续时中止。</span><span class="sxs-lookup"><span data-stu-id="916ae-112">While the runtime is suspended, the runtime will determine which threads are in the `AppDomain` that is being shut down and set them to abort when they resume.</span></span> <span data-ttu-id="916ae-113">有没有`AppDomain`-此挂起期间的特定回调。</span><span class="sxs-lookup"><span data-stu-id="916ae-113">There are no `AppDomain`-specific callbacks during this suspension.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|<span data-ttu-id="916ae-114">运行时挂起，这样代码间距调整才能发生。</span><span class="sxs-lookup"><span data-stu-id="916ae-114">The runtime is suspended so that code pitching can occur.</span></span><br /><br /> <span data-ttu-id="916ae-115">代码间距调整时，才会仅在实时 (JIT) 编译器处于活动状态时使用代码间距调整启用。</span><span class="sxs-lookup"><span data-stu-id="916ae-115">Code pitching ensues only when the just-in-time (JIT) compiler is active with code pitching enabled.</span></span> <span data-ttu-id="916ae-116">代码间距调整回调之间发生`ICorProfilerCallback::RuntimeSuspendFinished`和`ICorProfilerCallback::RuntimeResumeStarted`回调。</span><span class="sxs-lookup"><span data-stu-id="916ae-116">Code pitching callbacks occur between the `ICorProfilerCallback::RuntimeSuspendFinished` and `ICorProfilerCallback::RuntimeResumeStarted` callbacks.</span></span> <span data-ttu-id="916ae-117">**注意：** CLR JIT 不推广函数在.NET Framework 2.0 版中，以便在 2.0 中不使用此值。</span><span class="sxs-lookup"><span data-stu-id="916ae-117">**Note:**  The CLR JIT does not pitch functions in the .NET Framework version 2.0, so this value is not used in 2.0.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|<span data-ttu-id="916ae-118">运行时挂起，以便它可以关闭。</span><span class="sxs-lookup"><span data-stu-id="916ae-118">The runtime is suspended so that it can shut down.</span></span> <span data-ttu-id="916ae-119">它必须挂起所有线程以完成该操作。</span><span class="sxs-lookup"><span data-stu-id="916ae-119">It must suspend all threads to complete the operation.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|<span data-ttu-id="916ae-120">运行时已挂起，进程内调试。</span><span class="sxs-lookup"><span data-stu-id="916ae-120">The runtime is suspended for in-process debugging.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|<span data-ttu-id="916ae-121">运行时挂起来准备垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="916ae-121">The runtime is suspended to prepare for a garbage collection.</span></span>|  
|`COR_PRF_SUSPEND_FOR_REJIT`|<span data-ttu-id="916ae-122">已挂起运行时，JIT 重新编译。</span><span class="sxs-lookup"><span data-stu-id="916ae-122">The runtime is suspended for JIT recompilation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="916ae-123">备注</span><span class="sxs-lookup"><span data-stu-id="916ae-123">Remarks</span></span>  
 <span data-ttu-id="916ae-124">非托管代码中的所有运行时线程可以继续运行，直到它们尝试重新输入运行时，此时它们也会挂起，直到运行时恢复。</span><span class="sxs-lookup"><span data-stu-id="916ae-124">All runtime threads that are in unmanaged code are permitted to continue running until they try to re-enter the runtime, at which point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="916ae-125">这也适用于输入运行时的新线程。</span><span class="sxs-lookup"><span data-stu-id="916ae-125">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="916ae-126">运行时中的所有线程立即挂起; 如果它们是在可中断的代码中，连接，或者需要挂起时它们到达可中断的代码。</span><span class="sxs-lookup"><span data-stu-id="916ae-126">All threads within the runtime are either suspended immediately if they are in interruptible code, or asked to suspend when they do reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="916ae-127">惠?</span><span class="sxs-lookup"><span data-stu-id="916ae-127">Requirements</span></span>  
 <span data-ttu-id="916ae-128">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="916ae-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="916ae-129">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="916ae-129">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="916ae-130">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="916ae-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="916ae-131">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="916ae-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="916ae-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="916ae-132">See Also</span></span>  
 [<span data-ttu-id="916ae-133">分析枚举</span><span class="sxs-lookup"><span data-stu-id="916ae-133">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
