---
title: "ICorProfilerCallback::ExceptionUnwindFunctionLeave 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eba7f6e5123108a7040bd2185eb57fc703c72c30
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a><span data-ttu-id="64d42-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave 方法</span><span class="sxs-lookup"><span data-stu-id="64d42-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave Method</span></span>
<span data-ttu-id="64d42-103">通知探查器的异常处理在展开阶段已完成展开函数。</span><span class="sxs-lookup"><span data-stu-id="64d42-103">Notifies the profiler that the unwind phase of exception handling has finished unwinding a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64d42-104">语法</span><span class="sxs-lookup"><span data-stu-id="64d42-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="64d42-105">备注</span><span class="sxs-lookup"><span data-stu-id="64d42-105">Remarks</span></span>  
 <span data-ttu-id="64d42-106">当`ExceptionUnwindFunctionLeave`方法调用，因此函数实例和其堆栈数据从堆栈中移除。</span><span class="sxs-lookup"><span data-stu-id="64d42-106">When the `ExceptionUnwindFunctionLeave` method is called, the function instance and its stack data are removed from the stack.</span></span>  
  
 <span data-ttu-id="64d42-107">探查器在此调用期间不应进行阻止，因为堆栈可能未处于允许垃圾回收的状态，因此无法启用 preemptive 垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="64d42-107">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="64d42-108">如果尝试此处的探查器块和垃圾回收，则运行时将阻止，直到此回调返回。</span><span class="sxs-lookup"><span data-stu-id="64d42-108">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="64d42-109">此外，在此调用后，探查器必须调用进入托管代码或以任何方式导致托管内存分配。</span><span class="sxs-lookup"><span data-stu-id="64d42-109">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64d42-110">惠?</span><span class="sxs-lookup"><span data-stu-id="64d42-110">Requirements</span></span>  
 <span data-ttu-id="64d42-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="64d42-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64d42-112">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="64d42-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="64d42-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64d42-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64d42-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64d42-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64d42-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="64d42-115">See Also</span></span>  
 [<span data-ttu-id="64d42-116">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="64d42-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="64d42-117">ExceptionUnwindFunctionEnter 方法</span><span class="sxs-lookup"><span data-stu-id="64d42-117">ExceptionUnwindFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)
