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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cc63a0a42c1da11daa5d38ecce505296a893616b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453923"
---
# <a name="icorprofilercallback3-interface"></a><span data-ttu-id="bf799-102">ICorProfilerCallback3 接口</span><span class="sxs-lookup"><span data-stu-id="bf799-102">ICorProfilerCallback3 Interface</span></span>
<span data-ttu-id="bf799-103">提供公共语言运行时 (CLR) 用于通信的回叫方法附加和分离探查器的状态信息。</span><span class="sxs-lookup"><span data-stu-id="bf799-103">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bf799-104">方法</span><span class="sxs-lookup"><span data-stu-id="bf799-104">Methods</span></span>  
  
|<span data-ttu-id="bf799-105">方法</span><span class="sxs-lookup"><span data-stu-id="bf799-105">Method</span></span>|<span data-ttu-id="bf799-106">描述</span><span class="sxs-lookup"><span data-stu-id="bf799-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bf799-107">InitializeForAttach 方法</span><span class="sxs-lookup"><span data-stu-id="bf799-107">InitializeForAttach Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md)|<span data-ttu-id="bf799-108">由 CLR 使探查器可以将其状态初始化附加操作后调用。</span><span class="sxs-lookup"><span data-stu-id="bf799-108">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span></span>|  
|[<span data-ttu-id="bf799-109">ProfilerAttachComplete 方法</span><span class="sxs-lookup"><span data-stu-id="bf799-109">ProfilerAttachComplete Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerattachcomplete-method.md)|<span data-ttu-id="bf799-110">由 CLR 以指示探查器现在可以调用追赶方法调用。</span><span class="sxs-lookup"><span data-stu-id="bf799-110">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span></span>|  
|[<span data-ttu-id="bf799-111">ProfilerDetachSucceeded 方法</span><span class="sxs-lookup"><span data-stu-id="bf799-111">ProfilerDetachSucceeded Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerdetachsucceeded-method.md)|<span data-ttu-id="bf799-112">通知探查器公共语言运行时 (CLR) 将要卸载探查器 DLL。</span><span class="sxs-lookup"><span data-stu-id="bf799-112">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf799-113">备注</span><span class="sxs-lookup"><span data-stu-id="bf799-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf799-114">要求</span><span class="sxs-lookup"><span data-stu-id="bf799-114">Requirements</span></span>  
 <span data-ttu-id="bf799-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bf799-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf799-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bf799-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bf799-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf799-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf799-118">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf799-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf799-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf799-119">See Also</span></span>  
 [<span data-ttu-id="bf799-120">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="bf799-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="bf799-121">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="bf799-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="bf799-122">ICorProfilerCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="bf799-122">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [<span data-ttu-id="bf799-123">ICorProfilerCallback4 接口</span><span class="sxs-lookup"><span data-stu-id="bf799-123">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
