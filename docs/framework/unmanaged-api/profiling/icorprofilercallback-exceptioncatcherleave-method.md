---
title: ICorProfilerCallback::ExceptionCatcherLeave 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherLeave
helpviewer_keywords:
- ExceptionCatcherLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCatcherLeave method [.NET Framework profiling]
ms.assetid: 1f3dbdf5-db0c-4b07-bbb7-375de2a63673
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d0fef75a1d47ba0c16569d3955ee447c2e7332d4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776126"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="565b7-102">ICorProfilerCallback::ExceptionCatcherLeave 方法</span><span class="sxs-lookup"><span data-stu-id="565b7-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="565b7-103">通知探查器将控制权传递带相应`catch`块。</span><span class="sxs-lookup"><span data-stu-id="565b7-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="565b7-104">语法</span><span class="sxs-lookup"><span data-stu-id="565b7-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="565b7-105">备注</span><span class="sxs-lookup"><span data-stu-id="565b7-105">Remarks</span></span>  
 <span data-ttu-id="565b7-106">探查器不应在其实现此方法阻止因为堆栈可能未处于允许垃圾回收的状态，因此不能启用抢先式垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="565b7-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="565b7-107">如果探查器进行阻止并尝试执行垃圾回收，运行时将阻塞，直到此回调返回。</span><span class="sxs-lookup"><span data-stu-id="565b7-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="565b7-108">为托管代码或以任何方式导致托管内存分配，不应调用此方法的探查器的实现。</span><span class="sxs-lookup"><span data-stu-id="565b7-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="565b7-109">要求</span><span class="sxs-lookup"><span data-stu-id="565b7-109">Requirements</span></span>  
 <span data-ttu-id="565b7-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="565b7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="565b7-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="565b7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="565b7-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="565b7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="565b7-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="565b7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="565b7-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="565b7-114">See also</span></span>

- [<span data-ttu-id="565b7-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="565b7-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="565b7-116">ExceptionCatcherEnter 方法</span><span class="sxs-lookup"><span data-stu-id="565b7-116">ExceptionCatcherEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)
