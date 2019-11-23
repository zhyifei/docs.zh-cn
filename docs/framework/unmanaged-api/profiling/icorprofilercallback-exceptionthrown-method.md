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
ms.openlocfilehash: 4ecbe0ef3c3021c5633b9380da2eb31cf22aa4b1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445324"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="05f55-102">ICorProfilerCallback::ExceptionThrown 方法</span><span class="sxs-lookup"><span data-stu-id="05f55-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="05f55-103">Notifies the profiler that an exception has been thrown.</span><span class="sxs-lookup"><span data-stu-id="05f55-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="05f55-104">This function is called only if the exception reaches managed code.</span><span class="sxs-lookup"><span data-stu-id="05f55-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05f55-105">语法</span><span class="sxs-lookup"><span data-stu-id="05f55-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05f55-106">参数</span><span class="sxs-lookup"><span data-stu-id="05f55-106">Parameters</span></span>  
 `thrownObjectId`  
 <span data-ttu-id="05f55-107">[in] The ID of the object that caused the exception to be thrown.</span><span class="sxs-lookup"><span data-stu-id="05f55-107">[in] The ID of the object that caused the exception to be thrown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05f55-108">备注</span><span class="sxs-lookup"><span data-stu-id="05f55-108">Remarks</span></span>  
 <span data-ttu-id="05f55-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span><span class="sxs-lookup"><span data-stu-id="05f55-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="05f55-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span><span class="sxs-lookup"><span data-stu-id="05f55-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="05f55-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span><span class="sxs-lookup"><span data-stu-id="05f55-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05f55-112">要求</span><span class="sxs-lookup"><span data-stu-id="05f55-112">Requirements</span></span>  
 <span data-ttu-id="05f55-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="05f55-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05f55-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="05f55-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="05f55-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05f55-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05f55-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05f55-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05f55-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="05f55-117">See also</span></span>

- [<span data-ttu-id="05f55-118">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="05f55-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
