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
ms.openlocfilehash: b52a0e7f993629c1005883723c734996d75300a7
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868429"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a><span data-ttu-id="6e752-102">ICorProfilerInfo4::InitializeCurrentThread 方法</span><span class="sxs-lookup"><span data-stu-id="6e752-102">ICorProfilerInfo4::InitializeCurrentThread Method</span></span>
<span data-ttu-id="6e752-103">在同一线程上的后续探查器 API 调用之前初始化当前线程，以便避免死锁。</span><span class="sxs-lookup"><span data-stu-id="6e752-103">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e752-104">语法</span><span class="sxs-lookup"><span data-stu-id="6e752-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="6e752-105">备注</span><span class="sxs-lookup"><span data-stu-id="6e752-105">Remarks</span></span>  
 <span data-ttu-id="6e752-106">建议在存在挂起的线程时，对将调用探查器 API 的任何线程调用 `InitializeCurrentThread`。</span><span class="sxs-lookup"><span data-stu-id="6e752-106">We recommend that you call `InitializeCurrentThread` on any thread that will call a profiler API while there are suspended threads.</span></span> <span data-ttu-id="6e752-107">此方法通常由创建自己的线程的探查器使用，用来调用[ICorProfilerInfo2：:D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md)方法，在目标线程挂起时执行堆栈遍历。</span><span class="sxs-lookup"><span data-stu-id="6e752-107">This method is typically used by sampling profilers that create their own thread to call the [ICorProfilerInfo2::DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method to perform stack walks while the target thread is suspended.</span></span> <span data-ttu-id="6e752-108">通过在探查器首次创建采样线程时调用 `InitializeCurrentThread` 一次，探查器可以确保在第一次调用 `DoStackSnapshot` 时，CLR 将以其他方式执行的延迟的每个线程初始化，而不会挂起其他线程。</span><span class="sxs-lookup"><span data-stu-id="6e752-108">By calling `InitializeCurrentThread` once when the profiler first creates the sampling thread, profilers can ensure that lazy per-thread initialization that the CLR would otherwise perform during the first call to `DoStackSnapshot` can now occur safely when no other threads are suspended.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6e752-109">`InitializeCurrentThread` 会提前执行初始化来完成接受锁定的任务，并可能导致死锁。</span><span class="sxs-lookup"><span data-stu-id="6e752-109">`InitializeCurrentThread` does the initialization in advance to finish tasks that take locks, and may deadlock.</span></span> <span data-ttu-id="6e752-110">仅当没有挂起的线程时才调用 `InitializeCurrentThread`。</span><span class="sxs-lookup"><span data-stu-id="6e752-110">Call `InitializeCurrentThread` only when there are no suspended threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e752-111">需求</span><span class="sxs-lookup"><span data-stu-id="6e752-111">Requirements</span></span>  
 <span data-ttu-id="6e752-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6e752-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e752-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6e752-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6e752-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e752-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e752-115">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e752-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e752-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e752-116">See also</span></span>

- [<span data-ttu-id="6e752-117">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="6e752-117">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="6e752-118">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="6e752-118">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="6e752-119">分析</span><span class="sxs-lookup"><span data-stu-id="6e752-119">Profiling</span></span>](index.md)
