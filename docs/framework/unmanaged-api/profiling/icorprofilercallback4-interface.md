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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3eb1f46900199db65be5d14c56bfc0b6f55bf269
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59205129"
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="4f59e-102">ICorProfilerCallback4 接口</span><span class="sxs-lookup"><span data-stu-id="4f59e-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="4f59e-103">提供的公共语言运行时 (CLR) 使用将信息传递给探查器回调方法。</span><span class="sxs-lookup"><span data-stu-id="4f59e-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f59e-104">方法</span><span class="sxs-lookup"><span data-stu-id="4f59e-104">Methods</span></span>  
  
|<span data-ttu-id="4f59e-105">方法</span><span class="sxs-lookup"><span data-stu-id="4f59e-105">Method</span></span>|<span data-ttu-id="4f59e-106">描述</span><span class="sxs-lookup"><span data-stu-id="4f59e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4f59e-107">GetReJITParameters 方法</span><span class="sxs-lookup"><span data-stu-id="4f59e-107">GetReJITParameters Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="4f59e-108">允许代码探查器来设置新的重新编译的方法主体的备用代码生成标志。</span><span class="sxs-lookup"><span data-stu-id="4f59e-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="4f59e-109">MovedReferences2 方法</span><span class="sxs-lookup"><span data-stu-id="4f59e-109">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="4f59e-110">报告由于压缩垃圾回收堆中的对象的新布局。</span><span class="sxs-lookup"><span data-stu-id="4f59e-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="4f59e-111">ReJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="4f59e-111">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="4f59e-112">通知探查器在实时 (JIT) 编译器已完成重新编译的函数。</span><span class="sxs-lookup"><span data-stu-id="4f59e-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="4f59e-113">ReJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="4f59e-113">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="4f59e-114">通知探查器在实时 (JIT) 编译器已开始重新编译函数。</span><span class="sxs-lookup"><span data-stu-id="4f59e-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="4f59e-115">ReJITError 方法</span><span class="sxs-lookup"><span data-stu-id="4f59e-115">ReJITError Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="4f59e-116">将报告处理的重新编译请求时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="4f59e-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="4f59e-117">SurvivingReferences2 方法</span><span class="sxs-lookup"><span data-stu-id="4f59e-117">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="4f59e-118">将堆中对象的布局报告为非压缩垃圾回收的结果。</span><span class="sxs-lookup"><span data-stu-id="4f59e-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f59e-119">备注</span><span class="sxs-lookup"><span data-stu-id="4f59e-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f59e-120">要求</span><span class="sxs-lookup"><span data-stu-id="4f59e-120">Requirements</span></span>  
 <span data-ttu-id="4f59e-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4f59e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f59e-122">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4f59e-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4f59e-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f59e-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f59e-124">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f59e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f59e-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f59e-125">See also</span></span>

- [<span data-ttu-id="4f59e-126">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="4f59e-126">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [<span data-ttu-id="4f59e-127">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="4f59e-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="4f59e-128">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="4f59e-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
