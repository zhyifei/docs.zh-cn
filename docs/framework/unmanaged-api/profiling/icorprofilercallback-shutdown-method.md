---
title: ICorProfilerCallback::Shutdown 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Shutdown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb2bfe927eddaf6812b0185a586135e76f649c1b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728117"
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="0fe63-102">ICorProfilerCallback::Shutdown 方法</span><span class="sxs-lookup"><span data-stu-id="0fe63-102">ICorProfilerCallback::Shutdown Method</span></span>
<span data-ttu-id="0fe63-103">通知探查器正在关闭应用程序。</span><span class="sxs-lookup"><span data-stu-id="0fe63-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fe63-104">语法</span><span class="sxs-lookup"><span data-stu-id="0fe63-104">Syntax</span></span>  
  
```  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="0fe63-105">备注</span><span class="sxs-lookup"><span data-stu-id="0fe63-105">Remarks</span></span>  
 <span data-ttu-id="0fe63-106">探查器代码不能安全地调用的方法[ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)接口后`Shutdown`调用方法。</span><span class="sxs-lookup"><span data-stu-id="0fe63-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="0fe63-107">对任何调用`ICorProfilerInfo`方法会导致未定义的行为后`Shutdown`方法返回。</span><span class="sxs-lookup"><span data-stu-id="0fe63-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="0fe63-108">某些不可变事件可能仍会发生后关闭;请注意探查器应发生这种情况时立即返回。</span><span class="sxs-lookup"><span data-stu-id="0fe63-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="0fe63-109">`Shutdown`作为托管代码所分析的托管应用程序启动时，才会调用方法 （即，托管进程堆栈上的初始帧）。</span><span class="sxs-lookup"><span data-stu-id="0fe63-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="0fe63-110">如果应用程序作为非托管代码启动，但稍后又跳转到托管代码，从而创建公共语言运行时 (CLR) 的实例则`Shutdown`将不会调用。</span><span class="sxs-lookup"><span data-stu-id="0fe63-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="0fe63-111">对于这些情况下，探查器应包含在其库中`DllMain`例程使用 DLL_PROCESS_DETACH 值以释放任何资源并执行清理处理数据，例如刷新跟踪磁盘，等等。</span><span class="sxs-lookup"><span data-stu-id="0fe63-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="0fe63-112">一般情况下，探查器必须处理意外关闭。</span><span class="sxs-lookup"><span data-stu-id="0fe63-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="0fe63-113">例如，进程可能会暂停通过 Win32 的`TerminateProcess`方法 （在 Winbase.h 中声明）。</span><span class="sxs-lookup"><span data-stu-id="0fe63-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="0fe63-114">在其他情况下，CLR 将暂停特定托管的线程 （后台线程），而无需为其提供有序销毁消息。</span><span class="sxs-lookup"><span data-stu-id="0fe63-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fe63-115">要求</span><span class="sxs-lookup"><span data-stu-id="0fe63-115">Requirements</span></span>  
 <span data-ttu-id="0fe63-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0fe63-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fe63-117">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0fe63-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0fe63-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fe63-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fe63-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fe63-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fe63-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fe63-120">See also</span></span>
- [<span data-ttu-id="0fe63-121">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="0fe63-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="0fe63-122">Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="0fe63-122">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
