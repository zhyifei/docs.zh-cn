---
title: ICorProfilerCallback::ExceptionUnwindFinallyLeave 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave method [.NET Framework profiling]
- ExceptionUnwindFinallyLeave method [.NET Framework profiling]
ms.assetid: 2350351e-f253-4c0c-a191-f952bc5700e6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ce413ba184cfec731c6bac0d7f561c345bf53181
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452005"
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a><span data-ttu-id="99be8-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave 方法</span><span class="sxs-lookup"><span data-stu-id="99be8-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave Method</span></span>
<span data-ttu-id="99be8-103">通知探查器将处理已离开的异常在展开阶段`finally`子句。</span><span class="sxs-lookup"><span data-stu-id="99be8-103">Notifies the profiler that the unwind phase of exception handling has left a `finally` clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99be8-104">语法</span><span class="sxs-lookup"><span data-stu-id="99be8-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="99be8-105">备注</span><span class="sxs-lookup"><span data-stu-id="99be8-105">Remarks</span></span>  
 <span data-ttu-id="99be8-106">探查器在此调用期间不应进行阻止，因为堆栈可能未处于允许垃圾回收的状态，因此无法启用 preemptive 垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="99be8-106">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="99be8-107">如果尝试此处的探查器块和垃圾回收，则运行时将阻止，直到此回调返回。</span><span class="sxs-lookup"><span data-stu-id="99be8-107">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="99be8-108">此外，在此调用后，探查器必须调用进入托管代码或以任何方式导致托管内存分配。</span><span class="sxs-lookup"><span data-stu-id="99be8-108">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99be8-109">要求</span><span class="sxs-lookup"><span data-stu-id="99be8-109">Requirements</span></span>  
 <span data-ttu-id="99be8-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="99be8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99be8-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="99be8-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="99be8-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99be8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99be8-113">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99be8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99be8-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="99be8-114">See Also</span></span>  
 [<span data-ttu-id="99be8-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="99be8-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="99be8-116">ExceptionUnwindFinallyEnter 方法</span><span class="sxs-lookup"><span data-stu-id="99be8-116">ExceptionUnwindFinallyEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)
