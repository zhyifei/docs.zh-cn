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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e9cdbc2234519c0dba1a5004246492e7609ea2b3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180487"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="29f3c-102">ICorProfilerCallback::ExceptionThrown 方法</span><span class="sxs-lookup"><span data-stu-id="29f3c-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="29f3c-103">通知探查器已引发异常。</span><span class="sxs-lookup"><span data-stu-id="29f3c-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29f3c-104">仅当异常到达托管的代码调用此函数。</span><span class="sxs-lookup"><span data-stu-id="29f3c-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29f3c-105">语法</span><span class="sxs-lookup"><span data-stu-id="29f3c-105">Syntax</span></span>  
  
```  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29f3c-106">参数</span><span class="sxs-lookup"><span data-stu-id="29f3c-106">Parameters</span></span>  
 `thrownObjectId`  
 <span data-ttu-id="29f3c-107">[in]导致引发异常的对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="29f3c-107">[in] The ID of the object that caused the exception to be thrown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29f3c-108">备注</span><span class="sxs-lookup"><span data-stu-id="29f3c-108">Remarks</span></span>  
 <span data-ttu-id="29f3c-109">探查器不应在其实现此方法阻止因为堆栈可能未处于允许垃圾回收的状态，因此不能启用抢先式垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="29f3c-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="29f3c-110">如果探查器进行阻止并尝试执行垃圾回收，运行时将阻塞，直到此回调返回。</span><span class="sxs-lookup"><span data-stu-id="29f3c-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="29f3c-111">为托管代码或以任何方式导致托管内存分配，不应调用此方法的探查器的实现。</span><span class="sxs-lookup"><span data-stu-id="29f3c-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29f3c-112">要求</span><span class="sxs-lookup"><span data-stu-id="29f3c-112">Requirements</span></span>  
 <span data-ttu-id="29f3c-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="29f3c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29f3c-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="29f3c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="29f3c-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29f3c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29f3c-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29f3c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29f3c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="29f3c-117">See also</span></span>

- [<span data-ttu-id="29f3c-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="29f3c-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
