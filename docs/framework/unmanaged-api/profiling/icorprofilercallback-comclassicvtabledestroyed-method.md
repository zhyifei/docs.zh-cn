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
ms.openlocfilehash: 30d1e80d05344448c19c9f8f2d261442e4041487
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451712"
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a><span data-ttu-id="37b7e-102">ICorProfilerCallback::COMClassicVTableDestroyed 方法</span><span class="sxs-lookup"><span data-stu-id="37b7e-102">ICorProfilerCallback::COMClassicVTableDestroyed Method</span></span>
<span data-ttu-id="37b7e-103">通知探查器 COM 互操作 vtable 被销毁。</span><span class="sxs-lookup"><span data-stu-id="37b7e-103">Notifies the profiler that a COM interop vtable is being destroyed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37b7e-104">此回调很可能会永远不会发生，因为 vtable 析构发生非常接近关闭。</span><span class="sxs-lookup"><span data-stu-id="37b7e-104">This callback is likely never to occur, because the destruction of vtables occurs very close to shutdown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37b7e-105">语法</span><span class="sxs-lookup"><span data-stu-id="37b7e-105">Syntax</span></span>  
  
```  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="37b7e-106">参数</span><span class="sxs-lookup"><span data-stu-id="37b7e-106">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="37b7e-107">[in]为其创建此 vtable 类的 ID。</span><span class="sxs-lookup"><span data-stu-id="37b7e-107">[in] The ID of the class for which this vtable was created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="37b7e-108">[in]由类实现的接口 ID。</span><span class="sxs-lookup"><span data-stu-id="37b7e-108">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="37b7e-109">如果接口仅供内部，此值可能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="37b7e-109">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="37b7e-110">[in]指向 vtable 的开头的指针。</span><span class="sxs-lookup"><span data-stu-id="37b7e-110">[in] A pointer to the start of the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37b7e-111">备注</span><span class="sxs-lookup"><span data-stu-id="37b7e-111">Remarks</span></span>  
 <span data-ttu-id="37b7e-112">探查器不应在其实现此方法阻止因为堆栈可能未处于允许垃圾回收的状态，因此无法启用 preemptive 垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="37b7e-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="37b7e-113">如果探查器进行阻止并尝试执行垃圾回收，运行时将阻塞，直到此回调返回。</span><span class="sxs-lookup"><span data-stu-id="37b7e-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="37b7e-114">进入托管代码或以任何方式导致托管内存分配，不应调用此方法的探查器的实现。</span><span class="sxs-lookup"><span data-stu-id="37b7e-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37b7e-115">要求</span><span class="sxs-lookup"><span data-stu-id="37b7e-115">Requirements</span></span>  
 <span data-ttu-id="37b7e-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="37b7e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37b7e-117">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="37b7e-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="37b7e-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37b7e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37b7e-119">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37b7e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37b7e-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="37b7e-120">See Also</span></span>  
 [<span data-ttu-id="37b7e-121">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="37b7e-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="37b7e-122">COMClassicVTableCreated 方法</span><span class="sxs-lookup"><span data-stu-id="37b7e-122">COMClassicVTableCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)
