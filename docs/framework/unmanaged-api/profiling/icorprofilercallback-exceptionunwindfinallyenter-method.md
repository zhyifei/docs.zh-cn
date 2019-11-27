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
ms.openlocfilehash: 1f16add7b5a9d18e0c1eb33209b609e9bf7e18b0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445322"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="a6f58-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter 方法</span><span class="sxs-lookup"><span data-stu-id="a6f58-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="a6f58-103">通知探查器异常处理的展开阶段正在输入指定函数中包含的 `finally` 子句。</span><span class="sxs-lookup"><span data-stu-id="a6f58-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6f58-104">语法</span><span class="sxs-lookup"><span data-stu-id="a6f58-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6f58-105">参数</span><span class="sxs-lookup"><span data-stu-id="a6f58-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a6f58-106">中包含 `finally` 子句的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="a6f58-106">[in] The ID of the function that contains the `finally` clause.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6f58-107">备注</span><span class="sxs-lookup"><span data-stu-id="a6f58-107">Remarks</span></span>  
 <span data-ttu-id="a6f58-108">探查器不应在此方法的实现中被阻止，因为堆栈可能不处于允许垃圾回收的状态，因此无法启用抢先垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="a6f58-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="a6f58-109">如果探查器在此处阻止并且试图进行垃圾回收，则运行时将被阻止，直到此回调返回。</span><span class="sxs-lookup"><span data-stu-id="a6f58-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="a6f58-110">探查器的此方法的实现不应调入托管代码或以任何方式导致托管内存分配。</span><span class="sxs-lookup"><span data-stu-id="a6f58-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6f58-111">要求</span><span class="sxs-lookup"><span data-stu-id="a6f58-111">Requirements</span></span>  
 <span data-ttu-id="a6f58-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a6f58-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6f58-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a6f58-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a6f58-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6f58-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6f58-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6f58-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6f58-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6f58-116">See also</span></span>

- [<span data-ttu-id="a6f58-117">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="a6f58-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a6f58-118">GetNotifiedExceptionClauseInfo 方法</span><span class="sxs-lookup"><span data-stu-id="a6f58-118">GetNotifiedExceptionClauseInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="a6f58-119">ExceptionUnwindFinallyLeave 方法</span><span class="sxs-lookup"><span data-stu-id="a6f58-119">ExceptionUnwindFinallyLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)
