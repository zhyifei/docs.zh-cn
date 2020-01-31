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
ms.openlocfilehash: 6b7aa7c60b5e861787d7a115d90a00d67cc48db0
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866528"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="6d122-102">ICorProfilerCallback::ExceptionCatcherLeave 方法</span><span class="sxs-lookup"><span data-stu-id="6d122-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="6d122-103">通知探查器控制正在从相应的 `catch` 块传递出去。</span><span class="sxs-lookup"><span data-stu-id="6d122-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d122-104">语法</span><span class="sxs-lookup"><span data-stu-id="6d122-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="6d122-105">备注</span><span class="sxs-lookup"><span data-stu-id="6d122-105">Remarks</span></span>  
 <span data-ttu-id="6d122-106">探查器不应在此方法的实现中被阻止，因为堆栈可能不处于允许垃圾回收的状态，因此无法启用抢先垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="6d122-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="6d122-107">如果探查器在此处阻止并且试图进行垃圾回收，则运行时将被阻止，直到此回调返回。</span><span class="sxs-lookup"><span data-stu-id="6d122-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="6d122-108">探查器的此方法的实现不应调入托管代码或以任何方式导致托管内存分配。</span><span class="sxs-lookup"><span data-stu-id="6d122-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d122-109">需求</span><span class="sxs-lookup"><span data-stu-id="6d122-109">Requirements</span></span>  
 <span data-ttu-id="6d122-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6d122-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d122-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6d122-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6d122-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d122-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d122-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d122-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d122-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d122-114">See also</span></span>

- [<span data-ttu-id="6d122-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="6d122-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="6d122-116">ExceptionCatcherEnter 方法</span><span class="sxs-lookup"><span data-stu-id="6d122-116">ExceptionCatcherEnter Method</span></span>](icorprofilercallback-exceptioncatcherenter-method.md)
