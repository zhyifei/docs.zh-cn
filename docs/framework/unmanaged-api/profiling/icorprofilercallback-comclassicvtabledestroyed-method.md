---
title: ICorProfilerCallback::COMClassicVTableDestroyed 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.COMClassicVTableDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed
helpviewer_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed method [.NET Framework profiling]
- COMClassicVTableDestroyed method [.NET Framework profiling]
ms.assetid: 29da20ca-bf39-4356-8099-d9c3ac3423a9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f60c4373410c46c5d1ea284b2cacd4b5c070ed9d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54682818"
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a><span data-ttu-id="a297f-102">ICorProfilerCallback::COMClassicVTableDestroyed 方法</span><span class="sxs-lookup"><span data-stu-id="a297f-102">ICorProfilerCallback::COMClassicVTableDestroyed Method</span></span>
<span data-ttu-id="a297f-103">通知探查器 COM 互操作 vtable 被销毁。</span><span class="sxs-lookup"><span data-stu-id="a297f-103">Notifies the profiler that a COM interop vtable is being destroyed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a297f-104">此回调是 vtable 的可能永远不会发生，因为进行销毁关闭时。</span><span class="sxs-lookup"><span data-stu-id="a297f-104">This callback is likely never to occur, because the destruction of vtables occurs very close to shutdown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a297f-105">语法</span><span class="sxs-lookup"><span data-stu-id="a297f-105">Syntax</span></span>  
  
```  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a297f-106">参数</span><span class="sxs-lookup"><span data-stu-id="a297f-106">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="a297f-107">[in]为其创建此 vtable 类的 ID。</span><span class="sxs-lookup"><span data-stu-id="a297f-107">[in] The ID of the class for which this vtable was created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="a297f-108">[in]由类实现的接口 ID。</span><span class="sxs-lookup"><span data-stu-id="a297f-108">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="a297f-109">如果接口仅供内部，此值可能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a297f-109">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="a297f-110">[in]指向 vtable 开头的指针。</span><span class="sxs-lookup"><span data-stu-id="a297f-110">[in] A pointer to the start of the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a297f-111">备注</span><span class="sxs-lookup"><span data-stu-id="a297f-111">Remarks</span></span>  
 <span data-ttu-id="a297f-112">探查器不应在其实现此方法阻止因为堆栈可能未处于允许垃圾回收的状态，因此不能启用抢先式垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="a297f-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="a297f-113">如果探查器进行阻止并尝试执行垃圾回收，运行时将阻塞，直到此回调返回。</span><span class="sxs-lookup"><span data-stu-id="a297f-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="a297f-114">为托管代码或以任何方式导致托管内存分配，不应调用此方法的探查器的实现。</span><span class="sxs-lookup"><span data-stu-id="a297f-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a297f-115">要求</span><span class="sxs-lookup"><span data-stu-id="a297f-115">Requirements</span></span>  
 <span data-ttu-id="a297f-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a297f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a297f-117">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a297f-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a297f-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a297f-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a297f-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a297f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a297f-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="a297f-120">See also</span></span>
- [<span data-ttu-id="a297f-121">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="a297f-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a297f-122">COMClassicVTableCreated 方法</span><span class="sxs-lookup"><span data-stu-id="a297f-122">COMClassicVTableCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)
