---
title: "ICorProfilerCallback::COMClassicVTableDestroyed 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.COMClassicVTableDestroyed
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::COMClassicVTableDestroyed
helpviewer_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed method [.NET Framework profiling]
- COMClassicVTableDestroyed method [.NET Framework profiling]
ms.assetid: 29da20ca-bf39-4356-8099-d9c3ac3423a9
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 74ee3f0ca092710342b48b8adbaa5f5cf7e8b980
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a><span data-ttu-id="e6db7-102">ICorProfilerCallback::COMClassicVTableDestroyed 方法</span><span class="sxs-lookup"><span data-stu-id="e6db7-102">ICorProfilerCallback::COMClassicVTableDestroyed Method</span></span>
<span data-ttu-id="e6db7-103">通知探查器 COM 互操作 vtable 被销毁。</span><span class="sxs-lookup"><span data-stu-id="e6db7-103">Notifies the profiler that a COM interop vtable is being destroyed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6db7-104">此回调很可能会永远不会发生，因为 vtable 析构发生非常接近关闭。</span><span class="sxs-lookup"><span data-stu-id="e6db7-104">This callback is likely never to occur, because the destruction of vtables occurs very close to shutdown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6db7-105">语法</span><span class="sxs-lookup"><span data-stu-id="e6db7-105">Syntax</span></span>  
  
```  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6db7-106">参数</span><span class="sxs-lookup"><span data-stu-id="e6db7-106">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="e6db7-107">[in]为其创建此 vtable 类的 ID。</span><span class="sxs-lookup"><span data-stu-id="e6db7-107">[in] The ID of the class for which this vtable was created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="e6db7-108">[in]由类实现的接口 ID。</span><span class="sxs-lookup"><span data-stu-id="e6db7-108">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="e6db7-109">如果接口仅供内部，此值可能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e6db7-109">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="e6db7-110">[in]指向 vtable 的开头的指针。</span><span class="sxs-lookup"><span data-stu-id="e6db7-110">[in] A pointer to the start of the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6db7-111">备注</span><span class="sxs-lookup"><span data-stu-id="e6db7-111">Remarks</span></span>  
 <span data-ttu-id="e6db7-112">探查器不应在其实现此方法阻止因为堆栈可能未处于允许垃圾回收的状态，因此无法启用 preemptive 垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="e6db7-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="e6db7-113">如果探查器进行阻止并尝试执行垃圾回收，运行时将阻塞，直到此回调返回。</span><span class="sxs-lookup"><span data-stu-id="e6db7-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="e6db7-114">进入托管代码或以任何方式导致托管内存分配，不应调用此方法的探查器的实现。</span><span class="sxs-lookup"><span data-stu-id="e6db7-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6db7-115">惠?</span><span class="sxs-lookup"><span data-stu-id="e6db7-115">Requirements</span></span>  
 <span data-ttu-id="e6db7-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e6db7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6db7-117">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e6db7-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e6db7-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6db7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6db7-119">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6db7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6db7-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6db7-120">See Also</span></span>  
 [<span data-ttu-id="e6db7-121">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="e6db7-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="e6db7-122">COMClassicVTableCreated 方法</span><span class="sxs-lookup"><span data-stu-id="e6db7-122">COMClassicVTableCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)
