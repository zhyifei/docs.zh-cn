---
title: ICorProfilerCallback::COMClassicVTableCreated 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.COMClassicVTableCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableCreated
helpviewer_keywords:
- COMClassicVTableCreated method [.NET Framework profiling]
- ICorProfilerCallback::COMClassicVTableCreated method [.NET Framework profiling]
ms.assetid: 6e1834ab-c359-498a-b10b-984ae23cdda4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 062b63776264ae553039a2db0fc99d4fb7bec476
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745335"
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="db762-102">ICorProfilerCallback::COMClassicVTableCreated 方法</span><span class="sxs-lookup"><span data-stu-id="db762-102">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>
<span data-ttu-id="db762-103">通知探查器已创建 COM 互操作 vtable 指定 IID 和类。</span><span class="sxs-lookup"><span data-stu-id="db762-103">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db762-104">语法</span><span class="sxs-lookup"><span data-stu-id="db762-104">Syntax</span></span>  
  
```cpp  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db762-105">参数</span><span class="sxs-lookup"><span data-stu-id="db762-105">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="db762-106">[in]为其创建 vtable 类的 ID。</span><span class="sxs-lookup"><span data-stu-id="db762-106">[in] The ID of the class for which the vtable has been created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="db762-107">[in]由类实现的接口 ID。</span><span class="sxs-lookup"><span data-stu-id="db762-107">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="db762-108">如果接口仅供内部，此值可能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="db762-108">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="db762-109">[in]指向 vtable 开头的指针。</span><span class="sxs-lookup"><span data-stu-id="db762-109">[in] A pointer to the start of the vtable.</span></span>  
  
 `cSlots`  
 <span data-ttu-id="db762-110">[in]Vtable 中的槽数。</span><span class="sxs-lookup"><span data-stu-id="db762-110">[in] The number of slots that are in the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db762-111">备注</span><span class="sxs-lookup"><span data-stu-id="db762-111">Remarks</span></span>  
 <span data-ttu-id="db762-112">探查器不应在其实现此方法阻止因为堆栈可能未处于允许垃圾回收的状态，因此不能启用抢先式垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="db762-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="db762-113">如果探查器进行阻止并尝试执行垃圾回收，运行时将阻塞，直到此回调返回。</span><span class="sxs-lookup"><span data-stu-id="db762-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="db762-114">为托管代码或以任何方式导致托管内存分配，不应调用此方法的探查器的实现。</span><span class="sxs-lookup"><span data-stu-id="db762-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db762-115">要求</span><span class="sxs-lookup"><span data-stu-id="db762-115">Requirements</span></span>  
 <span data-ttu-id="db762-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="db762-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db762-117">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="db762-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="db762-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db762-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db762-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db762-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db762-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="db762-120">See also</span></span>

- [<span data-ttu-id="db762-121">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="db762-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="db762-122">COMClassicVTableDestroyed 方法</span><span class="sxs-lookup"><span data-stu-id="db762-122">COMClassicVTableDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)
