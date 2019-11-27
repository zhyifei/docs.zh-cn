---
title: ICorProfilerCallback4 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4
helpviewer_keywords:
- ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 665f3cfc-cd6f-4880-906c-ea65ad384783
topic_type:
- apiref
ms.openlocfilehash: a3394820f673e35777e1749229d4f8319841ca58
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439387"
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="107e8-102">ICorProfilerCallback4 接口</span><span class="sxs-lookup"><span data-stu-id="107e8-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="107e8-103">提供公共语言运行时（CLR）用于将信息传递给探查器的回调方法。</span><span class="sxs-lookup"><span data-stu-id="107e8-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="107e8-104">方法</span><span class="sxs-lookup"><span data-stu-id="107e8-104">Methods</span></span>  
  
|<span data-ttu-id="107e8-105">方法</span><span class="sxs-lookup"><span data-stu-id="107e8-105">Method</span></span>|<span data-ttu-id="107e8-106">说明</span><span class="sxs-lookup"><span data-stu-id="107e8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="107e8-107">GetReJITParameters 方法</span><span class="sxs-lookup"><span data-stu-id="107e8-107">GetReJITParameters Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="107e8-108">允许代码探查器为新的重新编译的方法体设置备用代码生成标志。</span><span class="sxs-lookup"><span data-stu-id="107e8-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="107e8-109">MovedReferences2 方法</span><span class="sxs-lookup"><span data-stu-id="107e8-109">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="107e8-110">作为压缩垃圾回收的结果，报告堆中对象的新布局。</span><span class="sxs-lookup"><span data-stu-id="107e8-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="107e8-111">ReJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="107e8-111">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="107e8-112">通知探查器，实时（JIT）编译器已完成函数的重新编译。</span><span class="sxs-lookup"><span data-stu-id="107e8-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="107e8-113">ReJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="107e8-113">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="107e8-114">通知探查器实时（JIT）编译器已开始重新编译某个函数。</span><span class="sxs-lookup"><span data-stu-id="107e8-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="107e8-115">ReJITError 方法</span><span class="sxs-lookup"><span data-stu-id="107e8-115">ReJITError Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="107e8-116">报告处理重新编译请求时遇到的错误。</span><span class="sxs-lookup"><span data-stu-id="107e8-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="107e8-117">SurvivingReferences2 方法</span><span class="sxs-lookup"><span data-stu-id="107e8-117">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="107e8-118">将堆中对象的布局报告为非压缩垃圾回收的结果。</span><span class="sxs-lookup"><span data-stu-id="107e8-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="107e8-119">备注</span><span class="sxs-lookup"><span data-stu-id="107e8-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="107e8-120">要求</span><span class="sxs-lookup"><span data-stu-id="107e8-120">Requirements</span></span>  
 <span data-ttu-id="107e8-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="107e8-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="107e8-122">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="107e8-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="107e8-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="107e8-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="107e8-124">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="107e8-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="107e8-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="107e8-125">See also</span></span>

- [<span data-ttu-id="107e8-126">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="107e8-126">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [<span data-ttu-id="107e8-127">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="107e8-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="107e8-128">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="107e8-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
