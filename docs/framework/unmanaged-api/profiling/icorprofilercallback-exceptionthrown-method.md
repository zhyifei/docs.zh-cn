---
title: "ICorProfilerCallback::ExceptionThrown 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionThrown
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionThrown
helpviewer_keywords:
- ExceptionThrown method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionThrown method [.NET Framework profiling]
ms.assetid: f1a23f3b-ac21-4905-8abf-8ea59f15af53
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3986ca8205297a36bb54825a7af72aeb9821f75b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="eb9d0-102">ICorProfilerCallback::ExceptionThrown 方法</span><span class="sxs-lookup"><span data-stu-id="eb9d0-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="eb9d0-103">通知探查器已引发异常。</span><span class="sxs-lookup"><span data-stu-id="eb9d0-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb9d0-104">仅当异常到达托管的代码调用此函数。</span><span class="sxs-lookup"><span data-stu-id="eb9d0-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb9d0-105">语法</span><span class="sxs-lookup"><span data-stu-id="eb9d0-105">Syntax</span></span>  
  
```  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb9d0-106">参数</span><span class="sxs-lookup"><span data-stu-id="eb9d0-106">Parameters</span></span>  
 `thrownObjectId`  
 <span data-ttu-id="eb9d0-107">[in]导致引发异常的对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="eb9d0-107">[in] The ID of the object that caused the exception to be thrown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb9d0-108">备注</span><span class="sxs-lookup"><span data-stu-id="eb9d0-108">Remarks</span></span>  
 <span data-ttu-id="eb9d0-109">探查器不应在其实现此方法阻止因为堆栈可能未处于允许垃圾回收的状态，因此无法启用 preemptive 垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="eb9d0-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="eb9d0-110">如果探查器进行阻止并尝试执行垃圾回收，运行时将阻塞，直到此回调返回。</span><span class="sxs-lookup"><span data-stu-id="eb9d0-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="eb9d0-111">进入托管代码或以任何方式导致托管内存分配，不应调用此方法的探查器的实现。</span><span class="sxs-lookup"><span data-stu-id="eb9d0-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb9d0-112">要求</span><span class="sxs-lookup"><span data-stu-id="eb9d0-112">Requirements</span></span>  
 <span data-ttu-id="eb9d0-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eb9d0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb9d0-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eb9d0-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eb9d0-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb9d0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb9d0-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb9d0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb9d0-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb9d0-117">See Also</span></span>  
 [<span data-ttu-id="eb9d0-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="eb9d0-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
