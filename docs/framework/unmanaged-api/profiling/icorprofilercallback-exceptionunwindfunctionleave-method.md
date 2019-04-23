---
title: ICorProfilerCallback::ExceptionUnwindFunctionLeave 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave method [.NET Framework profiling]
- ExceptionUnwindFunctionLeave method [.NET Framework profiling]
ms.assetid: ebaad1d5-ee0a-4cb0-96bc-8ba5d371b747
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 305c8c7abf778ea68efe06f3bdb57af001ea1b9a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227704"
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a><span data-ttu-id="214a2-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave 方法</span><span class="sxs-lookup"><span data-stu-id="214a2-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave Method</span></span>
<span data-ttu-id="214a2-103">通知探查器的异常处理展开阶段已完成展开函数。</span><span class="sxs-lookup"><span data-stu-id="214a2-103">Notifies the profiler that the unwind phase of exception handling has finished unwinding a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="214a2-104">语法</span><span class="sxs-lookup"><span data-stu-id="214a2-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="214a2-105">备注</span><span class="sxs-lookup"><span data-stu-id="214a2-105">Remarks</span></span>  
 <span data-ttu-id="214a2-106">当`ExceptionUnwindFunctionLeave`方法调用，从堆栈移除的函数实例和其堆栈数据。</span><span class="sxs-lookup"><span data-stu-id="214a2-106">When the `ExceptionUnwindFunctionLeave` method is called, the function instance and its stack data are removed from the stack.</span></span>  
  
 <span data-ttu-id="214a2-107">探查器在此调用期间不应进行阻止，因为堆栈可能未处于允许垃圾回收的状态，因此不能启用抢先式垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="214a2-107">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="214a2-108">如果尝试进行事件探查器阻止和垃圾回收，直到此回调返回，将阻止运行时。</span><span class="sxs-lookup"><span data-stu-id="214a2-108">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="214a2-109">此外，在此调用过程探查器必须调入托管代码或以任何方式导致托管内存分配。</span><span class="sxs-lookup"><span data-stu-id="214a2-109">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="214a2-110">要求</span><span class="sxs-lookup"><span data-stu-id="214a2-110">Requirements</span></span>  
 <span data-ttu-id="214a2-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="214a2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="214a2-112">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="214a2-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="214a2-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="214a2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="214a2-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="214a2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="214a2-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="214a2-115">See also</span></span>

- [<span data-ttu-id="214a2-116">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="214a2-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="214a2-117">ExceptionUnwindFunctionEnter 方法</span><span class="sxs-lookup"><span data-stu-id="214a2-117">ExceptionUnwindFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)
