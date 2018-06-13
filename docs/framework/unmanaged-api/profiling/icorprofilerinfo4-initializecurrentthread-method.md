---
title: ICorProfilerInfo4::InitializeCurrentThread 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4::InitializeCurrentThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f5a4a6bc7b1e79068b11b099352cec64dd09f301
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459448"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a><span data-ttu-id="26d98-102">ICorProfilerInfo4::InitializeCurrentThread 方法</span><span class="sxs-lookup"><span data-stu-id="26d98-102">ICorProfilerInfo4::InitializeCurrentThread Method</span></span>
<span data-ttu-id="26d98-103">初始化之前在同一线程调用的 API，因此可以避免该死锁的后续探查器的当前线程。</span><span class="sxs-lookup"><span data-stu-id="26d98-103">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26d98-104">语法</span><span class="sxs-lookup"><span data-stu-id="26d98-104">Syntax</span></span>  
  
```  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="26d98-105">备注</span><span class="sxs-lookup"><span data-stu-id="26d98-105">Remarks</span></span>  
 <span data-ttu-id="26d98-106">我们建议调用`InitializeCurrentThread`将调用探查器的任何线程 API 尽管有挂起的线程。</span><span class="sxs-lookup"><span data-stu-id="26d98-106">We recommend that you call `InitializeCurrentThread` on any thread that will call a profiler API while there are suspended threads.</span></span> <span data-ttu-id="26d98-107">此方法通常由采样探查器可创建自己的线程来调用[icorprofilerinfo2:: Dostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)方法来执行堆栈将指导此目标线程被挂起时。</span><span class="sxs-lookup"><span data-stu-id="26d98-107">This method is typically used by sampling profilers that create their own thread to call the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method to perform stack walks while the target thread is suspended.</span></span> <span data-ttu-id="26d98-108">通过调用`InitializeCurrentThread`后当探查器首先创建采样线程，探查器可以确保每个线程迟缓初始化 CLR 将执行在第一次调用期间`DoStackSnapshot`现在可以发生的安全地没有其他线程都时挂起。</span><span class="sxs-lookup"><span data-stu-id="26d98-108">By calling `InitializeCurrentThread` once when the profiler first creates the sampling thread, profilers can ensure that lazy per-thread initialization that the CLR would otherwise perform during the first call to `DoStackSnapshot` can now occur safely when no other threads are suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26d98-109">`InitializeCurrentThread` 执行初始化提前以完成任务，可采用锁，并可能发生死锁。</span><span class="sxs-lookup"><span data-stu-id="26d98-109">`InitializeCurrentThread` does the initialization in advance to finish tasks that take locks, and may deadlock.</span></span> <span data-ttu-id="26d98-110">调用`InitializeCurrentThread`仅当没有任何挂起的线程时。</span><span class="sxs-lookup"><span data-stu-id="26d98-110">Call `InitializeCurrentThread` only when there are no suspended threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26d98-111">要求</span><span class="sxs-lookup"><span data-stu-id="26d98-111">Requirements</span></span>  
 <span data-ttu-id="26d98-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="26d98-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26d98-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="26d98-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="26d98-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26d98-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26d98-115">**.NET framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26d98-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26d98-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="26d98-116">See Also</span></span>  
 [<span data-ttu-id="26d98-117">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="26d98-117">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="26d98-118">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="26d98-118">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="26d98-119">分析</span><span class="sxs-lookup"><span data-stu-id="26d98-119">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
