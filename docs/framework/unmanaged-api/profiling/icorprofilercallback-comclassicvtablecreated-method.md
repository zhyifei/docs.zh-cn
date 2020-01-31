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
ms.openlocfilehash: 808c26f53c4089248420280a43c88a1b3af0dad9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866541"
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="244ad-102">ICorProfilerCallback::COMClassicVTableCreated 方法</span><span class="sxs-lookup"><span data-stu-id="244ad-102">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>
<span data-ttu-id="244ad-103">通知探查器已创建指定 IID 和类的 COM 互操作 vtable。</span><span class="sxs-lookup"><span data-stu-id="244ad-103">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="244ad-104">语法</span><span class="sxs-lookup"><span data-stu-id="244ad-104">Syntax</span></span>  
  
```cpp  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
## <a name="parameters"></a><span data-ttu-id="244ad-105">参数</span><span class="sxs-lookup"><span data-stu-id="244ad-105">Parameters</span></span>

- `wrappedClasId`

  <span data-ttu-id="244ad-106">\[中] 已为其创建 vtable 的类的 ID。</span><span class="sxs-lookup"><span data-stu-id="244ad-106">\[in] The ID of the class for which the vtable has been created.</span></span>

- `implementedIID`

  <span data-ttu-id="244ad-107">\[中] 类实现的接口的 ID。</span><span class="sxs-lookup"><span data-stu-id="244ad-107">\[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="244ad-108">如果接口仅限内部接口，此值可能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="244ad-108">This value may be NULL if the interface is internal only.</span></span>

- `pVTable`

  <span data-ttu-id="244ad-109">\[中的] 指向 vtable 开头的指针。</span><span class="sxs-lookup"><span data-stu-id="244ad-109">\[in] A pointer to the start of the vtable.</span></span>

- `cSlots`

  <span data-ttu-id="244ad-110">\[] vtable 中的槽数。</span><span class="sxs-lookup"><span data-stu-id="244ad-110">\[in] The number of slots that are in the vtable.</span></span>

## <a name="remarks"></a><span data-ttu-id="244ad-111">备注</span><span class="sxs-lookup"><span data-stu-id="244ad-111">Remarks</span></span>  
 <span data-ttu-id="244ad-112">探查器不应在此方法的实现中被阻止，因为堆栈可能不处于允许垃圾回收的状态，因此无法启用抢先垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="244ad-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="244ad-113">如果探查器在此处阻止并且试图进行垃圾回收，则运行时将被阻止，直到此回调返回。</span><span class="sxs-lookup"><span data-stu-id="244ad-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="244ad-114">探查器的此方法的实现不应调入托管代码或以任何方式导致托管内存分配。</span><span class="sxs-lookup"><span data-stu-id="244ad-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="244ad-115">需求</span><span class="sxs-lookup"><span data-stu-id="244ad-115">Requirements</span></span>  
 <span data-ttu-id="244ad-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="244ad-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="244ad-117">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="244ad-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="244ad-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="244ad-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="244ad-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="244ad-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="244ad-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="244ad-120">See also</span></span>

- [<span data-ttu-id="244ad-121">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="244ad-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="244ad-122">COMClassicVTableDestroyed 方法</span><span class="sxs-lookup"><span data-stu-id="244ad-122">COMClassicVTableDestroyed Method</span></span>](icorprofilercallback-comclassicvtabledestroyed-method.md)
