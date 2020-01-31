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
ms.openlocfilehash: ab7c8cbc41967af04c4c9a8813f32b9b1f01c6a1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866346"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="89d5d-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter 方法</span><span class="sxs-lookup"><span data-stu-id="89d5d-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="89d5d-103">通知探查器异常处理的展开阶段正在输入指定函数中包含的 `finally` 子句。</span><span class="sxs-lookup"><span data-stu-id="89d5d-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89d5d-104">语法</span><span class="sxs-lookup"><span data-stu-id="89d5d-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89d5d-105">参数</span><span class="sxs-lookup"><span data-stu-id="89d5d-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="89d5d-106">\[中] 包含 `finally` 子句的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="89d5d-106">\[in] The ID of the function that contains the `finally` clause.</span></span>

## <a name="remarks"></a><span data-ttu-id="89d5d-107">备注</span><span class="sxs-lookup"><span data-stu-id="89d5d-107">Remarks</span></span>  
 <span data-ttu-id="89d5d-108">探查器不应在此方法的实现中被阻止，因为堆栈可能不处于允许垃圾回收的状态，因此无法启用抢先垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="89d5d-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="89d5d-109">如果探查器在此处阻止并且试图进行垃圾回收，则运行时将被阻止，直到此回调返回。</span><span class="sxs-lookup"><span data-stu-id="89d5d-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="89d5d-110">探查器的此方法的实现不应调入托管代码或以任何方式导致托管内存分配。</span><span class="sxs-lookup"><span data-stu-id="89d5d-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89d5d-111">需求</span><span class="sxs-lookup"><span data-stu-id="89d5d-111">Requirements</span></span>  
 <span data-ttu-id="89d5d-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="89d5d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89d5d-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89d5d-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89d5d-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89d5d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89d5d-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89d5d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89d5d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89d5d-116">See also</span></span>

- [<span data-ttu-id="89d5d-117">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="89d5d-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="89d5d-118">GetNotifiedExceptionClauseInfo 方法</span><span class="sxs-lookup"><span data-stu-id="89d5d-118">GetNotifiedExceptionClauseInfo Method</span></span>](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="89d5d-119">ExceptionUnwindFinallyLeave 方法</span><span class="sxs-lookup"><span data-stu-id="89d5d-119">ExceptionUnwindFinallyLeave Method</span></span>](icorprofilercallback-exceptionunwindfinallyleave-method.md)
