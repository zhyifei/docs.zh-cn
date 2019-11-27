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
ms.openlocfilehash: 63e41df8af85d94df068526ef69708687b341e78
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446942"
---
# <a name="icorprofilercallbackshutdown-method"></a><span data-ttu-id="53570-102">ICorProfilerCallback::Shutdown 方法</span><span class="sxs-lookup"><span data-stu-id="53570-102">ICorProfilerCallback::Shutdown Method</span></span>
<span data-ttu-id="53570-103">通知探查器应用程序正在关闭。</span><span class="sxs-lookup"><span data-stu-id="53570-103">Notifies the profiler that the application is shutting down.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53570-104">语法</span><span class="sxs-lookup"><span data-stu-id="53570-104">Syntax</span></span>  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a><span data-ttu-id="53570-105">备注</span><span class="sxs-lookup"><span data-stu-id="53570-105">Remarks</span></span>  
 <span data-ttu-id="53570-106">调用 `Shutdown` 方法之后，探查器代码将无法安全地调用[ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)接口的方法。</span><span class="sxs-lookup"><span data-stu-id="53570-106">The profiler code cannot safely call methods of the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface after the `Shutdown` method is called.</span></span> <span data-ttu-id="53570-107">调用 `ICorProfilerInfo` 方法会导致在 `Shutdown` 方法返回后出现未定义的行为。</span><span class="sxs-lookup"><span data-stu-id="53570-107">Any calls to `ICorProfilerInfo` methods result in undefined behavior after the `Shutdown` method returns.</span></span> <span data-ttu-id="53570-108">某些不可变事件可能仍会在关闭后发生;此事件发生时，探查器应小心立即返回。</span><span class="sxs-lookup"><span data-stu-id="53570-108">Certain immutable events may still occur after shutdown; the profiler should take care to return immediately when this occurs.</span></span>  
  
 <span data-ttu-id="53570-109">仅当要分析的托管应用程序作为托管代码启动时（即，处理堆栈上的初始帧是托管的），将调用 `Shutdown` 方法。</span><span class="sxs-lookup"><span data-stu-id="53570-109">The `Shutdown` method will be called only if the managed application that is being profiled started as managed code (that is, the initial frame on the process stack is managed).</span></span> <span data-ttu-id="53570-110">如果应用程序启动为非托管代码，但后来跳转到托管代码，从而创建公共语言运行时（CLR）的实例，则不会调用 `Shutdown`。</span><span class="sxs-lookup"><span data-stu-id="53570-110">If the application started as unmanaged code but later jumped into managed code, thereby creating an instance of the common language runtime (CLR), then `Shutdown` will not be called.</span></span> <span data-ttu-id="53570-111">对于这些情况，探查器应在其库中包含一个 `DllMain` 例程，该例程使用 DLL_PROCESS_DETACH 值来释放所有资源并对其数据执行清理处理，如将跟踪刷新到磁盘等。</span><span class="sxs-lookup"><span data-stu-id="53570-111">For these cases, the profiler should include in its library a `DllMain` routine that uses the DLL_PROCESS_DETACH value to free any resources and perform clean-up processing of its data, such as flushing traces to disk and so on.</span></span>  
  
 <span data-ttu-id="53570-112">通常，探查器必须处理意外关闭。</span><span class="sxs-lookup"><span data-stu-id="53570-112">In general, the profiler must cope with unexpected shutdowns.</span></span> <span data-ttu-id="53570-113">例如，进程可能由 Win32 `TerminateProcess` 方法（在 Winbase.h 中声明）暂停。</span><span class="sxs-lookup"><span data-stu-id="53570-113">For example, a process might be halted by Win32's `TerminateProcess` method (declared in Winbase.h).</span></span> <span data-ttu-id="53570-114">在其他情况下，CLR 将暂停某些托管线程（后台线程），而无需为它们传递有序的析构消息。</span><span class="sxs-lookup"><span data-stu-id="53570-114">In other cases, the CLR will halt certain managed threads (background threads) without delivering orderly destruction messages for them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53570-115">要求</span><span class="sxs-lookup"><span data-stu-id="53570-115">Requirements</span></span>  
 <span data-ttu-id="53570-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="53570-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53570-117">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="53570-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="53570-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53570-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53570-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53570-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53570-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53570-120">See also</span></span>

- [<span data-ttu-id="53570-121">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="53570-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="53570-122">Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="53570-122">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
