---
title: ICorProfilerCallback::ExceptionThrown 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionThrown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionThrown
helpviewer_keywords:
- ExceptionThrown method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionThrown method [.NET Framework profiling]
ms.assetid: f1a23f3b-ac21-4905-8abf-8ea59f15af53
topic_type:
- apiref
ms.openlocfilehash: b1799472c4923aaccfabeae459ad72f6ae94c80d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866372"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="5c9f4-102">ICorProfilerCallback::ExceptionThrown 方法</span><span class="sxs-lookup"><span data-stu-id="5c9f4-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="5c9f4-103">通知探查器引发了异常。</span><span class="sxs-lookup"><span data-stu-id="5c9f4-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5c9f4-104">仅当异常到达托管代码时，才调用此函数。</span><span class="sxs-lookup"><span data-stu-id="5c9f4-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c9f4-105">语法</span><span class="sxs-lookup"><span data-stu-id="5c9f4-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c9f4-106">参数</span><span class="sxs-lookup"><span data-stu-id="5c9f4-106">Parameters</span></span>

- `thrownObjectId`

  <span data-ttu-id="5c9f4-107">中 \[] 导致引发异常的对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="5c9f4-107">\[in] The ID of the object that caused the exception to be thrown.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5c9f4-108">备注</span><span class="sxs-lookup"><span data-stu-id="5c9f4-108">Remarks</span></span>  
 <span data-ttu-id="5c9f4-109">探查器不应在此方法的实现中被阻止，因为堆栈可能不处于允许垃圾回收的状态，因此无法启用抢先垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="5c9f4-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="5c9f4-110">如果探查器在此处阻止并且试图进行垃圾回收，则运行时将被阻止，直到此回调返回。</span><span class="sxs-lookup"><span data-stu-id="5c9f4-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="5c9f4-111">探查器的此方法的实现不应调入托管代码或以任何方式导致托管内存分配。</span><span class="sxs-lookup"><span data-stu-id="5c9f4-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c9f4-112">需求</span><span class="sxs-lookup"><span data-stu-id="5c9f4-112">Requirements</span></span>  
 <span data-ttu-id="5c9f4-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5c9f4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c9f4-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5c9f4-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5c9f4-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c9f4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c9f4-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c9f4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c9f4-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c9f4-117">See also</span></span>

- [<span data-ttu-id="5c9f4-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="5c9f4-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
