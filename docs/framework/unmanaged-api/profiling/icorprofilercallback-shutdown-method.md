---
title: "ICorProfilerCallback::Shutdown 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.Shutdown
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ea738414c21536377705260646e0f0684442492d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="78f61-102">ICorProfilerCallback::Shutdown 方法</span><span class="sxs-lookup"><span data-stu-id="78f61-102">ICorProfilerCallback::Shutdown Method</span></span>
<span data-ttu-id="78f61-103">通知探查器应用程序正在关闭。</span><span class="sxs-lookup"><span data-stu-id="78f61-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78f61-104">语法</span><span class="sxs-lookup"><span data-stu-id="78f61-104">Syntax</span></span>  
  
```  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="78f61-105">备注</span><span class="sxs-lookup"><span data-stu-id="78f61-105">Remarks</span></span>  
 <span data-ttu-id="78f61-106">探查器代码不能安全地调用方法的[ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)接口后`Shutdown`调用方法。</span><span class="sxs-lookup"><span data-stu-id="78f61-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="78f61-107">对任何调用`ICorProfilerInfo`方法都会导致未定义的行为后`Shutdown`方法返回。</span><span class="sxs-lookup"><span data-stu-id="78f61-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="78f61-108">某些不可变事件还是会出现后关闭;探查器应注意发生这种情况时立即返回。</span><span class="sxs-lookup"><span data-stu-id="78f61-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="78f61-109">`Shutdown`将调用方法，仅当所分析的托管应用程序启动为托管代码 （即，托管进程堆栈中的初始帧）。</span><span class="sxs-lookup"><span data-stu-id="78f61-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="78f61-110">如果应用程序作为非托管代码已启动，但稍后又跳转到托管代码，从而然后创建的公共语言运行时 (CLR) 实例`Shutdown`将不会调用。</span><span class="sxs-lookup"><span data-stu-id="78f61-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="78f61-111">对于这些情况下，探查器应包括在其库`DllMain`例程使用 DLL_PROCESS_DETACH 要释放任何资源并执行其数据，如刷新跟踪，依此类推磁盘清理处理的值。</span><span class="sxs-lookup"><span data-stu-id="78f61-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="78f61-112">一般情况下，探查器必须处理意外关闭。</span><span class="sxs-lookup"><span data-stu-id="78f61-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="78f61-113">例如，进程可能会暂停通过 Win32 的`TerminateProcess`方法 （在 Winbase.h 中声明）。</span><span class="sxs-lookup"><span data-stu-id="78f61-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="78f61-114">在其他情况下，CLR 将暂停某些托管的线程 （后台线程），而无需为它们提供有序析构消息。</span><span class="sxs-lookup"><span data-stu-id="78f61-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78f61-115">要求</span><span class="sxs-lookup"><span data-stu-id="78f61-115">Requirements</span></span>  
 <span data-ttu-id="78f61-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="78f61-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78f61-117">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="78f61-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="78f61-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78f61-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78f61-119">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78f61-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78f61-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78f61-120">See Also</span></span>  
 [<span data-ttu-id="78f61-121">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="78f61-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="78f61-122">Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="78f61-122">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
