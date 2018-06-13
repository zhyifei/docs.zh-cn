---
title: ICorProfilerCallback::ExceptionUnwindFinallyEnter 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter method [.NET Framework profiling]
- ExceptionUnwindFinallyEnter method [.NET Framework profiling]
ms.assetid: c7fab986-b69f-4ec8-b7b7-91dcfc239cd0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9bd144717decd16a84d2f005d84a22b4ef824d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452226"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="50a45-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter 方法</span><span class="sxs-lookup"><span data-stu-id="50a45-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="50a45-103">通知探查器，异常在展开阶段处理正在进入该`finally`子句包含在指定的函数。</span><span class="sxs-lookup"><span data-stu-id="50a45-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50a45-104">语法</span><span class="sxs-lookup"><span data-stu-id="50a45-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="50a45-105">参数</span><span class="sxs-lookup"><span data-stu-id="50a45-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="50a45-106">[in]包含函数的 ID`finally`子句。</span><span class="sxs-lookup"><span data-stu-id="50a45-106">[in] The ID of the function that contains the `finally` clause.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50a45-107">备注</span><span class="sxs-lookup"><span data-stu-id="50a45-107">Remarks</span></span>  
 <span data-ttu-id="50a45-108">探查器不应在其实现此方法阻止因为堆栈可能未处于允许垃圾回收的状态，因此无法启用 preemptive 垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="50a45-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="50a45-109">如果探查器进行阻止并尝试执行垃圾回收，运行时将阻塞，直到此回调返回。</span><span class="sxs-lookup"><span data-stu-id="50a45-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="50a45-110">进入托管代码或以任何方式导致托管内存分配，不应调用此方法的探查器的实现。</span><span class="sxs-lookup"><span data-stu-id="50a45-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50a45-111">要求</span><span class="sxs-lookup"><span data-stu-id="50a45-111">Requirements</span></span>  
 <span data-ttu-id="50a45-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="50a45-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50a45-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="50a45-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="50a45-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50a45-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50a45-115">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50a45-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50a45-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="50a45-116">See Also</span></span>  
 [<span data-ttu-id="50a45-117">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="50a45-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="50a45-118">GetNotifiedExceptionClauseInfo 方法</span><span class="sxs-lookup"><span data-stu-id="50a45-118">GetNotifiedExceptionClauseInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)  
 [<span data-ttu-id="50a45-119">ExceptionUnwindFinallyLeave 方法</span><span class="sxs-lookup"><span data-stu-id="50a45-119">ExceptionUnwindFinallyLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)
