---
title: ICorProfilerCallback3 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3
helpviewer_keywords:
- ICorProfilerCallback3 interface [.NET Framework profiling]
ms.assetid: be83af41-3dec-4c77-8529-9dd6b8042af6
topic_type:
- apiref
ms.openlocfilehash: ad9c5445cbef0be7919570db64b027556d923752
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865566"
---
# <a name="icorprofilercallback3-interface"></a><span data-ttu-id="2757e-102">ICorProfilerCallback3 接口</span><span class="sxs-lookup"><span data-stu-id="2757e-102">ICorProfilerCallback3 Interface</span></span>
<span data-ttu-id="2757e-103">提供公共语言运行时（CLR）用来向探查器传达附加和分离状态信息的回调方法。</span><span class="sxs-lookup"><span data-stu-id="2757e-103">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2757e-104">方法</span><span class="sxs-lookup"><span data-stu-id="2757e-104">Methods</span></span>  
  
|<span data-ttu-id="2757e-105">方法</span><span class="sxs-lookup"><span data-stu-id="2757e-105">Method</span></span>|<span data-ttu-id="2757e-106">描述</span><span class="sxs-lookup"><span data-stu-id="2757e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2757e-107">InitializeForAttach 方法</span><span class="sxs-lookup"><span data-stu-id="2757e-107">InitializeForAttach Method</span></span>](icorprofilercallback3-initializeforattach-method.md)|<span data-ttu-id="2757e-108">由 CLR 调用，以使探查器能够在附加操作后初始化其状态。</span><span class="sxs-lookup"><span data-stu-id="2757e-108">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span></span>|  
|[<span data-ttu-id="2757e-109">ProfilerAttachComplete 方法</span><span class="sxs-lookup"><span data-stu-id="2757e-109">ProfilerAttachComplete Method</span></span>](icorprofilercallback3-profilerattachcomplete-method.md)|<span data-ttu-id="2757e-110">由 CLR 调用以指示探查器现在可以调用追赶方法。</span><span class="sxs-lookup"><span data-stu-id="2757e-110">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span></span>|  
|[<span data-ttu-id="2757e-111">ProfilerDetachSucceeded 方法</span><span class="sxs-lookup"><span data-stu-id="2757e-111">ProfilerDetachSucceeded Method</span></span>](icorprofilercallback3-profilerdetachsucceeded-method.md)|<span data-ttu-id="2757e-112">通知探查器公共语言运行时 (CLR) 将要卸载探查器 DLL。</span><span class="sxs-lookup"><span data-stu-id="2757e-112">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2757e-113">备注</span><span class="sxs-lookup"><span data-stu-id="2757e-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2757e-114">需求</span><span class="sxs-lookup"><span data-stu-id="2757e-114">Requirements</span></span>  
 <span data-ttu-id="2757e-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2757e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2757e-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2757e-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2757e-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2757e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2757e-118">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2757e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2757e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2757e-119">See also</span></span>

- [<span data-ttu-id="2757e-120">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="2757e-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="2757e-121">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="2757e-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="2757e-122">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="2757e-122">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
- [<span data-ttu-id="2757e-123">ICorProfilerCallback4 接口</span><span class="sxs-lookup"><span data-stu-id="2757e-123">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
