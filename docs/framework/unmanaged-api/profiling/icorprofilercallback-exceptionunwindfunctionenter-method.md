---
title: ICorProfilerCallback::ExceptionUnwindFunctionEnter 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionEnter method [.NET Framework profiling]
- ExceptionUnwindFunctionEnter method [.NET Framework profiling]
ms.assetid: ea3dc625-5650-4bf4-8e67-01e42be065b1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6169d00065fad57b7ce346ab9029f242eff5498a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451436"
---
# <a name="icorprofilercallbackexceptionunwindfunctionenter-method"></a><span data-ttu-id="71b77-102">ICorProfilerCallback::ExceptionUnwindFunctionEnter 方法</span><span class="sxs-lookup"><span data-stu-id="71b77-102">ICorProfilerCallback::ExceptionUnwindFunctionEnter Method</span></span>
<span data-ttu-id="71b77-103">通知探查器的异常处理在展开阶段已开始展开一个函数。</span><span class="sxs-lookup"><span data-stu-id="71b77-103">Notifies the profiler that the unwind phase of exception handling has begun to unwind a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71b77-104">语法</span><span class="sxs-lookup"><span data-stu-id="71b77-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71b77-105">参数</span><span class="sxs-lookup"><span data-stu-id="71b77-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="71b77-106">[in]正在展开的函数 ID。</span><span class="sxs-lookup"><span data-stu-id="71b77-106">[in] The ID of the function that is being unwound.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71b77-107">备注</span><span class="sxs-lookup"><span data-stu-id="71b77-107">Remarks</span></span>  
 <span data-ttu-id="71b77-108">探查器不应在其实现此方法阻止因为堆栈可能未处于允许垃圾回收的状态，因此无法启用 preemptive 垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="71b77-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="71b77-109">如果探查器进行阻止并尝试执行垃圾回收，运行时将阻塞，直到此回调返回。</span><span class="sxs-lookup"><span data-stu-id="71b77-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="71b77-110">进入托管代码或以任何方式导致托管内存分配，不应调用此方法的探查器的实现。</span><span class="sxs-lookup"><span data-stu-id="71b77-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71b77-111">要求</span><span class="sxs-lookup"><span data-stu-id="71b77-111">Requirements</span></span>  
 <span data-ttu-id="71b77-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="71b77-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71b77-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="71b77-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="71b77-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71b77-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71b77-115">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71b77-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71b77-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="71b77-116">See Also</span></span>  
 [<span data-ttu-id="71b77-117">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="71b77-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="71b77-118">ExceptionUnwindFunctionLeave 方法</span><span class="sxs-lookup"><span data-stu-id="71b77-118">ExceptionUnwindFunctionLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)
