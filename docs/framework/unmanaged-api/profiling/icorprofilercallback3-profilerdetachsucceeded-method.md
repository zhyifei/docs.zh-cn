---
title: "ICorProfilerCallback3::ProfilerDetachSucceeded 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback3.ProfilerDetachSucceeded Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback3::ProfilerDetachSucceeded
helpviewer_keywords:
- ProfilerDetachSucceeded method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerDetachSucceeded method [.NET Framework profiling]
ms.assetid: 05164966-16ce-4cc9-a530-43a640c00711
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d4413e5c475bce6d6f2eea1f7a968c946237f47a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback3profilerdetachsucceeded-method"></a><span data-ttu-id="28cc4-102">ICorProfilerCallback3::ProfilerDetachSucceeded 方法</span><span class="sxs-lookup"><span data-stu-id="28cc4-102">ICorProfilerCallback3::ProfilerDetachSucceeded Method</span></span>
<span data-ttu-id="28cc4-103">通知探查器公共语言运行时 (CLR) 将要卸载探查器 DLL。</span><span class="sxs-lookup"><span data-stu-id="28cc4-103">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28cc4-104">语法</span><span class="sxs-lookup"><span data-stu-id="28cc4-104">Syntax</span></span>  
  
```  
HRESULT ProfilerDetachSucceeded();  
```  
  
## <a name="return-value"></a><span data-ttu-id="28cc4-105">返回值</span><span class="sxs-lookup"><span data-stu-id="28cc4-105">Return Value</span></span>  
 <span data-ttu-id="28cc4-106">将忽略来自此回调的返回值。</span><span class="sxs-lookup"><span data-stu-id="28cc4-106">The return value from this callback is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28cc4-107">备注</span><span class="sxs-lookup"><span data-stu-id="28cc4-107">Remarks</span></span>  
 <span data-ttu-id="28cc4-108">在所有线程均退出探查器的代码之后，发出`ProfilerDetachSucceeded` 回调。</span><span class="sxs-lookup"><span data-stu-id="28cc4-108">The `ProfilerDetachSucceeded` callback is issued after all threads have exited the profiler's code.</span></span> <span data-ttu-id="28cc4-109">当调用此方法时，探查器应执行任何不适合用于其析构函数的的最后执行的任务，例如通知其 UI 或日志记录组件。</span><span class="sxs-lookup"><span data-stu-id="28cc4-109">When this method is called, the profiler should perform any last-minute tasks that are not appropriate for its destructor, such as notifying its UI or logging component.</span></span> <span data-ttu-id="28cc4-110">但是，探查器必须不调用函数在此回调过程中由 CLR 提供的接口 (如[ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)或`IMetaData*`接口)。</span><span class="sxs-lookup"><span data-stu-id="28cc4-110">However, the profiler must not call functions on interfaces that are provided by the CLR during this callback (such as the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) or `IMetaData*` interfaces).</span></span>  
  
 <span data-ttu-id="28cc4-111">CLR 在 Windows 应用程序事件日志中创建条目，用于表示分离操作成功。</span><span class="sxs-lookup"><span data-stu-id="28cc4-111">The CLR creates an entry in the Windows Application event log to indicate that the detach operation is successful.</span></span>  
  
 <span data-ttu-id="28cc4-112">探查器从此回调返回后，CLR 将释放探查器对象并卸载探查器 DLL。</span><span class="sxs-lookup"><span data-stu-id="28cc4-112">After the profiler returns from this callback, the CLR releases the profiler object and unloads the profiler DLL.</span></span> <span data-ttu-id="28cc4-113">因此，探查器不可执行任何会导致探查器 DLL 从此回调返回后其内部进行执行的操作。</span><span class="sxs-lookup"><span data-stu-id="28cc4-113">Therefore, the profiler must not perform any actions that would cause execution to occur inside the profiler DLL after it returns from this callback.</span></span> <span data-ttu-id="28cc4-114">例如，它不能创建线程或注册计时器回调。</span><span class="sxs-lookup"><span data-stu-id="28cc4-114">For example, it must not create threads or register timer callbacks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28cc4-115">要求</span><span class="sxs-lookup"><span data-stu-id="28cc4-115">Requirements</span></span>  
 <span data-ttu-id="28cc4-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="28cc4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28cc4-117">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="28cc4-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="28cc4-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28cc4-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28cc4-119">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28cc4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28cc4-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28cc4-120">See Also</span></span>  
 [<span data-ttu-id="28cc4-121">元数据接口</span><span class="sxs-lookup"><span data-stu-id="28cc4-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="28cc4-122">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="28cc4-122">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="28cc4-123">分析接口</span><span class="sxs-lookup"><span data-stu-id="28cc4-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="28cc4-124">分析</span><span class="sxs-lookup"><span data-stu-id="28cc4-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
