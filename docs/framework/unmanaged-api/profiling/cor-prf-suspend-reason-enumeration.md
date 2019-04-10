---
title: COR_PRF_SUSPEND_REASON 枚举
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 21533b5173bcd91d0c944fbde4eafc9817de8315
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220052"
---
# <a name="corprfsuspendreason-enumeration"></a><span data-ttu-id="368fa-102">COR_PRF_SUSPEND_REASON 枚举</span><span class="sxs-lookup"><span data-stu-id="368fa-102">COR_PRF_SUSPEND_REASON Enumeration</span></span>
<span data-ttu-id="368fa-103">指示运行时挂起的原因。</span><span class="sxs-lookup"><span data-stu-id="368fa-103">Indicates the reason that the runtime is suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="368fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="368fa-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="368fa-105">成员</span><span class="sxs-lookup"><span data-stu-id="368fa-105">Members</span></span>  
  
|<span data-ttu-id="368fa-106">成员</span><span class="sxs-lookup"><span data-stu-id="368fa-106">Member</span></span>|<span data-ttu-id="368fa-107">描述</span><span class="sxs-lookup"><span data-stu-id="368fa-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|<span data-ttu-id="368fa-108">运行时挂起，原因不明。</span><span class="sxs-lookup"><span data-stu-id="368fa-108">The runtime is suspended for an unspecified reason.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|<span data-ttu-id="368fa-109">在运行时挂起垃圾回收集合请求提供服务。</span><span class="sxs-lookup"><span data-stu-id="368fa-109">The runtime is suspended to service a garbage collection request.</span></span><br /><br /> <span data-ttu-id="368fa-110">垃圾收集相关回调之间发生[icorprofilercallback:: Runtimesuspendfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)并[icorprofilercallback:: Runtimeresumestarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="368fa-110">The garbage collection-related callbacks occur between the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|<span data-ttu-id="368fa-111">运行时挂起，以便`AppDomain`可以关闭。</span><span class="sxs-lookup"><span data-stu-id="368fa-111">The runtime is suspended so that an `AppDomain` can be shut down.</span></span><br /><br /> <span data-ttu-id="368fa-112">当挂起运行时，运行时将确定哪些线程处于`AppDomain`，它是正在关闭，并将它们设置为继续时中止。</span><span class="sxs-lookup"><span data-stu-id="368fa-112">While the runtime is suspended, the runtime will determine which threads are in the `AppDomain` that is being shut down and set them to abort when they resume.</span></span> <span data-ttu-id="368fa-113">有没有`AppDomain`-此挂起期间的特定回调。</span><span class="sxs-lookup"><span data-stu-id="368fa-113">There are no `AppDomain`-specific callbacks during this suspension.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|<span data-ttu-id="368fa-114">运行时挂起，以便进行代码间距调整。</span><span class="sxs-lookup"><span data-stu-id="368fa-114">The runtime is suspended so that code pitching can occur.</span></span><br /><br /> <span data-ttu-id="368fa-115">代码时，才会仅在实时 (JIT) 编译器处于活动状态时使用代码间距调整已启用。</span><span class="sxs-lookup"><span data-stu-id="368fa-115">Code pitching ensues only when the just-in-time (JIT) compiler is active with code pitching enabled.</span></span> <span data-ttu-id="368fa-116">代码间距调整回调发生之间`ICorProfilerCallback::RuntimeSuspendFinished`和`ICorProfilerCallback::RuntimeResumeStarted`回调。</span><span class="sxs-lookup"><span data-stu-id="368fa-116">Code pitching callbacks occur between the `ICorProfilerCallback::RuntimeSuspendFinished` and `ICorProfilerCallback::RuntimeResumeStarted` callbacks.</span></span> <span data-ttu-id="368fa-117">**注意：** CLR JIT 不会在.NET Framework 2.0 版中，不宣传函数，以便在 2.0 中不使用此值。</span><span class="sxs-lookup"><span data-stu-id="368fa-117">**Note:**  The CLR JIT does not pitch functions in the .NET Framework version 2.0, so this value is not used in 2.0.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|<span data-ttu-id="368fa-118">运行时挂起，以便它可以关闭。</span><span class="sxs-lookup"><span data-stu-id="368fa-118">The runtime is suspended so that it can shut down.</span></span> <span data-ttu-id="368fa-119">它必须挂起所有线程完成该操作。</span><span class="sxs-lookup"><span data-stu-id="368fa-119">It must suspend all threads to complete the operation.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|<span data-ttu-id="368fa-120">运行时挂起进行进程内调试。</span><span class="sxs-lookup"><span data-stu-id="368fa-120">The runtime is suspended for in-process debugging.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|<span data-ttu-id="368fa-121">在运行时挂起垃圾回收准备。</span><span class="sxs-lookup"><span data-stu-id="368fa-121">The runtime is suspended to prepare for a garbage collection.</span></span>|  
|`COR_PRF_SUSPEND_FOR_REJIT`|<span data-ttu-id="368fa-122">运行时挂起为 JIT 重新编译。</span><span class="sxs-lookup"><span data-stu-id="368fa-122">The runtime is suspended for JIT recompilation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="368fa-123">备注</span><span class="sxs-lookup"><span data-stu-id="368fa-123">Remarks</span></span>  
 <span data-ttu-id="368fa-124">非托管代码中的所有运行时线程都可以继续运行，直到它们尝试重新输入运行时，此时它们还会挂起，直到运行时恢复。</span><span class="sxs-lookup"><span data-stu-id="368fa-124">All runtime threads that are in unmanaged code are permitted to continue running until they try to re-enter the runtime, at which point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="368fa-125">这也适用于输入运行时的新线程。</span><span class="sxs-lookup"><span data-stu-id="368fa-125">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="368fa-126">在运行时中的所有线程立即挂起; 如果它们是在可中断代码中，连接，或者需要挂起时它们到达可中断的代码。</span><span class="sxs-lookup"><span data-stu-id="368fa-126">All threads within the runtime are either suspended immediately if they are in interruptible code, or asked to suspend when they do reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="368fa-127">要求</span><span class="sxs-lookup"><span data-stu-id="368fa-127">Requirements</span></span>  
 <span data-ttu-id="368fa-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="368fa-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="368fa-129">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="368fa-129">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="368fa-130">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="368fa-130">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="368fa-131">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="368fa-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="368fa-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="368fa-132">See also</span></span>

- [<span data-ttu-id="368fa-133">分析枚举</span><span class="sxs-lookup"><span data-stu-id="368fa-133">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
