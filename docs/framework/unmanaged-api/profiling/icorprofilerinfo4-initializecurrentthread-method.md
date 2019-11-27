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
ms.openlocfilehash: 39882a554f9d47040bef00ff320d15b56abea533
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445724"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a><span data-ttu-id="4dce0-102">ICorProfilerInfo4::InitializeCurrentThread 方法</span><span class="sxs-lookup"><span data-stu-id="4dce0-102">ICorProfilerInfo4::InitializeCurrentThread Method</span></span>
<span data-ttu-id="4dce0-103">在同一线程上的后续探查器 API 调用之前初始化当前线程，以便避免死锁。</span><span class="sxs-lookup"><span data-stu-id="4dce0-103">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dce0-104">语法</span><span class="sxs-lookup"><span data-stu-id="4dce0-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="4dce0-105">备注</span><span class="sxs-lookup"><span data-stu-id="4dce0-105">Remarks</span></span>  
 <span data-ttu-id="4dce0-106">建议在存在挂起的线程时，对将调用探查器 API 的任何线程调用 `InitializeCurrentThread`。</span><span class="sxs-lookup"><span data-stu-id="4dce0-106">We recommend that you call `InitializeCurrentThread` on any thread that will call a profiler API while there are suspended threads.</span></span> <span data-ttu-id="4dce0-107">此方法通常由创建自己的线程的探查器使用，用来调用[ICorProfilerInfo2：:D ostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)方法，在目标线程挂起时执行堆栈遍历。</span><span class="sxs-lookup"><span data-stu-id="4dce0-107">This method is typically used by sampling profilers that create their own thread to call the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method to perform stack walks while the target thread is suspended.</span></span> <span data-ttu-id="4dce0-108">通过在探查器首次创建采样线程时调用 `InitializeCurrentThread` 一次，探查器可以确保在第一次调用 `DoStackSnapshot` 时，CLR 将以其他方式执行的延迟的每个线程初始化，而不会挂起其他线程。</span><span class="sxs-lookup"><span data-stu-id="4dce0-108">By calling `InitializeCurrentThread` once when the profiler first creates the sampling thread, profilers can ensure that lazy per-thread initialization that the CLR would otherwise perform during the first call to `DoStackSnapshot` can now occur safely when no other threads are suspended.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4dce0-109">`InitializeCurrentThread` 会提前执行初始化来完成接受锁定的任务，并可能导致死锁。</span><span class="sxs-lookup"><span data-stu-id="4dce0-109">`InitializeCurrentThread` does the initialization in advance to finish tasks that take locks, and may deadlock.</span></span> <span data-ttu-id="4dce0-110">仅当没有挂起的线程时才调用 `InitializeCurrentThread`。</span><span class="sxs-lookup"><span data-stu-id="4dce0-110">Call `InitializeCurrentThread` only when there are no suspended threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dce0-111">要求</span><span class="sxs-lookup"><span data-stu-id="4dce0-111">Requirements</span></span>  
 <span data-ttu-id="4dce0-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4dce0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dce0-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4dce0-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4dce0-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4dce0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4dce0-115">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dce0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dce0-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4dce0-116">See also</span></span>

- [<span data-ttu-id="4dce0-117">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="4dce0-117">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="4dce0-118">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="4dce0-118">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="4dce0-119">分析</span><span class="sxs-lookup"><span data-stu-id="4dce0-119">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
