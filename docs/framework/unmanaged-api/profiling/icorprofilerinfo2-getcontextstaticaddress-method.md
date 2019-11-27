---
title: ICorProfilerInfo2::GetContextStaticAddress 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetContextStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetContextStaticAddress
helpviewer_keywords:
- GetContextStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetContextStaticAddress method [.NET Framework profiling]
ms.assetid: 2b374116-0972-416a-8cf5-79213129be9a
topic_type:
- apiref
ms.openlocfilehash: d5d7da343148d5f1c2aa9b2b639b094f8269199b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433200"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a><span data-ttu-id="36661-102">ICorProfilerInfo2::GetContextStaticAddress 方法</span><span class="sxs-lookup"><span data-stu-id="36661-102">ICorProfilerInfo2::GetContextStaticAddress Method</span></span>
<span data-ttu-id="36661-103">获取指定上下文的范围内的指定上下文静态字段的地址。</span><span class="sxs-lookup"><span data-stu-id="36661-103">Gets the address for the specified context-static field that is in the scope of the specified context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36661-104">语法</span><span class="sxs-lookup"><span data-stu-id="36661-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36661-105">参数</span><span class="sxs-lookup"><span data-stu-id="36661-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="36661-106">中包含请求的上下文静态字段的类的 ID。</span><span class="sxs-lookup"><span data-stu-id="36661-106">[in] The ID of the class that contains the requested context-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="36661-107">中请求的上下文静态字段的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="36661-107">[in] The metadata token for the requested context-static field.</span></span>  
  
 `contextId`  
 <span data-ttu-id="36661-108">中作为所请求的上下文静态字段的作用域的上下文的 ID。</span><span class="sxs-lookup"><span data-stu-id="36661-108">[in] The ID of the context that is the scope for the requested context-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="36661-109">弄指向指定上下文内的静态字段的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="36661-109">[out] A pointer to the address of the static field that is within the specified context.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36661-110">备注</span><span class="sxs-lookup"><span data-stu-id="36661-110">Remarks</span></span>  
 <span data-ttu-id="36661-111">`GetContextStaticAddress` 方法可能会返回以下内容之一：</span><span class="sxs-lookup"><span data-stu-id="36661-111">The `GetContextStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="36661-112">如果未在指定的上下文中为给定的静态字段分配地址，则 CORPROF_E_DATAINCOMPLETE HRESULT。</span><span class="sxs-lookup"><span data-stu-id="36661-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="36661-113">可能位于垃圾回收堆中的对象的地址。</span><span class="sxs-lookup"><span data-stu-id="36661-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="36661-114">这些地址可能会在垃圾回收后失效，因此，在垃圾回收后，探查器不应假定它们是有效的。</span><span class="sxs-lookup"><span data-stu-id="36661-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="36661-115">在类的类构造函数完成之前，尽管某些静态字段可能已经初始化并为垃圾回收对象提供了根，`GetContextStaticAddress` 仍将返回其所有静态字段的 CORPROF_E_DATAINCOMPLETE。</span><span class="sxs-lookup"><span data-stu-id="36661-115">Before a class’s class constructor is completed, `GetContextStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36661-116">要求</span><span class="sxs-lookup"><span data-stu-id="36661-116">Requirements</span></span>  
 <span data-ttu-id="36661-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="36661-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36661-118">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="36661-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="36661-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36661-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36661-120">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36661-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36661-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36661-121">See also</span></span>

- [<span data-ttu-id="36661-122">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="36661-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="36661-123">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="36661-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
