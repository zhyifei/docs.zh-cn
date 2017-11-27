---
title: "ICorProfilerInfo2::GetContextStaticAddress 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetContextStaticAddress
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetContextStaticAddress
helpviewer_keywords:
- GetContextStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetContextStaticAddress method [.NET Framework profiling]
ms.assetid: 2b374116-0972-416a-8cf5-79213129be9a
topic_type: apiref
caps.latest.revision: "23"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2d206ca90b2d89ead67f419f0f4511d19d8ce110
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a><span data-ttu-id="b53e6-102">ICorProfilerInfo2::GetContextStaticAddress 方法</span><span class="sxs-lookup"><span data-stu-id="b53e6-102">ICorProfilerInfo2::GetContextStaticAddress Method</span></span>
<span data-ttu-id="b53e6-103">获取为指定的上下文范围内的指定上下文的静态字段的地址。</span><span class="sxs-lookup"><span data-stu-id="b53e6-103">Gets the address for the specified context-static field that is in the scope of the specified context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b53e6-104">语法</span><span class="sxs-lookup"><span data-stu-id="b53e6-104">Syntax</span></span>  
  
```  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b53e6-105">参数</span><span class="sxs-lookup"><span data-stu-id="b53e6-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="b53e6-106">[in]包含请求的上下文静态字段的类 ID。</span><span class="sxs-lookup"><span data-stu-id="b53e6-106">[in] The ID of the class that contains the requested context-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="b53e6-107">[in]请求的上下文静态字段的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="b53e6-107">[in] The metadata token for the requested context-static field.</span></span>  
  
 `contextId`  
 <span data-ttu-id="b53e6-108">[in]与请求的上下文静态字段的作用域的上下文 ID。</span><span class="sxs-lookup"><span data-stu-id="b53e6-108">[in] The ID of the context that is the scope for the requested context-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="b53e6-109">[out]指向在指定的上下文内的静态字段的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="b53e6-109">[out] A pointer to the address of the static field that is within the specified context.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b53e6-110">备注</span><span class="sxs-lookup"><span data-stu-id="b53e6-110">Remarks</span></span>  
 <span data-ttu-id="b53e6-111">`GetContextStaticAddress`方法可能会返回以下项之一：</span><span class="sxs-lookup"><span data-stu-id="b53e6-111">The `GetContextStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="b53e6-112">如果尚未分配为给定的静态字段指定的上下文中的地址 CORPROF_E_DATAINCOMPLETE HRESULT。</span><span class="sxs-lookup"><span data-stu-id="b53e6-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="b53e6-113">可能会在垃圾回收堆中的对象的地址。</span><span class="sxs-lookup"><span data-stu-id="b53e6-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="b53e6-114">这些地址可能会变得无效垃圾回收后，以便垃圾回收后，探查器不应假定它们有效。</span><span class="sxs-lookup"><span data-stu-id="b53e6-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="b53e6-115">完成的类的类构造函数之前，`GetContextStaticAddress`将返回 CORPROF_E_DATAINCOMPLETE 对于所有其静态字段，尽管可能已初始化的静态字段的一些和定位垃圾回收对象。</span><span class="sxs-lookup"><span data-stu-id="b53e6-115">Before a class’s class constructor is completed, `GetContextStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b53e6-116">要求</span><span class="sxs-lookup"><span data-stu-id="b53e6-116">Requirements</span></span>  
 <span data-ttu-id="b53e6-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b53e6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b53e6-118">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b53e6-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b53e6-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b53e6-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b53e6-120">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b53e6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b53e6-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b53e6-121">See Also</span></span>  
 [<span data-ttu-id="b53e6-122">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="b53e6-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="b53e6-123">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="b53e6-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
