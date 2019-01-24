---
title: ICorProfilerCallback::ExceptionCatcherEnter 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cb31da8b3fb9148bb41cf7216b44e7cbf610eaee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671611"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="50e53-102">ICorProfilerCallback::ExceptionCatcherEnter 方法</span><span class="sxs-lookup"><span data-stu-id="50e53-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>
<span data-ttu-id="50e53-103">通知探查器将控制权传递到相应`catch`块。</span><span class="sxs-lookup"><span data-stu-id="50e53-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50e53-104">语法</span><span class="sxs-lookup"><span data-stu-id="50e53-104">Syntax</span></span>  
  
```  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="50e53-105">参数</span><span class="sxs-lookup"><span data-stu-id="50e53-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="50e53-106">[in]函数包含的标识符`catch`块。</span><span class="sxs-lookup"><span data-stu-id="50e53-106">[in] The identifier of the function containing the `catch` block.</span></span>  
  
 `objectId`  
 <span data-ttu-id="50e53-107">[in]正在处理的异常的标识符。</span><span class="sxs-lookup"><span data-stu-id="50e53-107">[in] The identifier of the exception being handled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50e53-108">备注</span><span class="sxs-lookup"><span data-stu-id="50e53-108">Remarks</span></span>  
 <span data-ttu-id="50e53-109">`ExceptionCatcherEnter`才捕获点位于使用实时 (JIT) 编译器编译的代码中调用方法。</span><span class="sxs-lookup"><span data-stu-id="50e53-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="50e53-110">非托管代码中或在运行时的内部代码中捕获的异常将不会调用此通知。</span><span class="sxs-lookup"><span data-stu-id="50e53-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="50e53-111">`objectId`由于垃圾回收无法移动了对象，因为再次传递值`ExceptionThrown`通知。</span><span class="sxs-lookup"><span data-stu-id="50e53-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="50e53-112">探查器不应在其实现此方法阻止因为堆栈可能未处于允许垃圾回收的状态，因此不能启用抢先式垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="50e53-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="50e53-113">如果探查器进行阻止并尝试执行垃圾回收，运行时将阻塞，直到此回调返回。</span><span class="sxs-lookup"><span data-stu-id="50e53-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="50e53-114">为托管代码或以任何方式导致托管内存分配，不应调用此方法的探查器的实现。</span><span class="sxs-lookup"><span data-stu-id="50e53-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50e53-115">要求</span><span class="sxs-lookup"><span data-stu-id="50e53-115">Requirements</span></span>  
 <span data-ttu-id="50e53-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="50e53-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50e53-117">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="50e53-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="50e53-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50e53-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50e53-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50e53-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50e53-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="50e53-120">See also</span></span>
- [<span data-ttu-id="50e53-121">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="50e53-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="50e53-122">ExceptionCatcherLeave 方法</span><span class="sxs-lookup"><span data-stu-id="50e53-122">ExceptionCatcherLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)
