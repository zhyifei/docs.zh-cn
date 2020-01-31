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
ms.openlocfilehash: 534e0672820cc2509f32765274ad970fda69ec5d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866502"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="9d343-102">ICorProfilerCallback::ExceptionCatcherEnter 方法</span><span class="sxs-lookup"><span data-stu-id="9d343-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>
<span data-ttu-id="9d343-103">通知探查器控制正在传递到适当的 `catch` 块。</span><span class="sxs-lookup"><span data-stu-id="9d343-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d343-104">语法</span><span class="sxs-lookup"><span data-stu-id="9d343-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d343-105">参数</span><span class="sxs-lookup"><span data-stu-id="9d343-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="9d343-106">\[中] 包含 `catch` 块的函数的标识符。</span><span class="sxs-lookup"><span data-stu-id="9d343-106">\[in] The identifier of the function containing the `catch` block.</span></span>
  
- `objectId`

  <span data-ttu-id="9d343-107">\[中] 正在处理的异常的标识符。</span><span class="sxs-lookup"><span data-stu-id="9d343-107">\[in] The identifier of the exception being handled.</span></span>

## <a name="remarks"></a><span data-ttu-id="9d343-108">备注</span><span class="sxs-lookup"><span data-stu-id="9d343-108">Remarks</span></span>  
 <span data-ttu-id="9d343-109">仅当 catch 点位于用实时（JIT）编译器编译的代码中时，才会调用 `ExceptionCatcherEnter` 方法。</span><span class="sxs-lookup"><span data-stu-id="9d343-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="9d343-110">在非托管代码中或在运行时的内部代码中捕获的异常将不会调用此通知。</span><span class="sxs-lookup"><span data-stu-id="9d343-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="9d343-111">该 `objectId` 值将再次传递，因为垃圾回收可能会因为 `ExceptionThrown` 通知而移动了对象。</span><span class="sxs-lookup"><span data-stu-id="9d343-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="9d343-112">探查器不应在此方法的实现中被阻止，因为堆栈可能不处于允许垃圾回收的状态，因此无法启用抢先垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="9d343-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="9d343-113">如果探查器在此处阻止并且试图进行垃圾回收，则运行时将被阻止，直到此回调返回。</span><span class="sxs-lookup"><span data-stu-id="9d343-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="9d343-114">探查器的此方法的实现不应调入托管代码或以任何方式导致托管内存分配。</span><span class="sxs-lookup"><span data-stu-id="9d343-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d343-115">需求</span><span class="sxs-lookup"><span data-stu-id="9d343-115">Requirements</span></span>  
 <span data-ttu-id="9d343-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9d343-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d343-117">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9d343-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9d343-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d343-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d343-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d343-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d343-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d343-120">See also</span></span>

- [<span data-ttu-id="9d343-121">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="9d343-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="9d343-122">ExceptionCatcherLeave 方法</span><span class="sxs-lookup"><span data-stu-id="9d343-122">ExceptionCatcherLeave Method</span></span>](icorprofilercallback-exceptioncatcherleave-method.md)
