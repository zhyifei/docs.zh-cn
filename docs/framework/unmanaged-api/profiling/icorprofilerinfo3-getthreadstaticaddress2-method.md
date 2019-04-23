---
title: ICorProfilerInfo3::GetThreadStaticAddress2 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetThreadStaticAddress2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2
helpviewer_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2 method [.NET Framework profiling]
- GetThreadStaticAddress2 method [.NET Framework profiling]
ms.assetid: a9608861-ae64-4467-8a73-be05ad34beac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f62dadf4f21022f8f425596cf5957891ed39effe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189178"
---
# <a name="icorprofilerinfo3getthreadstaticaddress2-method"></a><span data-ttu-id="fa0ae-102">ICorProfilerInfo3::GetThreadStaticAddress2 方法</span><span class="sxs-lookup"><span data-stu-id="fa0ae-102">ICorProfilerInfo3::GetThreadStaticAddress2 Method</span></span>
<span data-ttu-id="fa0ae-103">获取指定线程和应用程序域范围内的指定线程静态字段的地址。</span><span class="sxs-lookup"><span data-stu-id="fa0ae-103">Gets the address of the specified thread-static field that is in the scope of the specified thread and application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa0ae-104">语法</span><span class="sxs-lookup"><span data-stu-id="fa0ae-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStaticAddress2(  
                [in] ClassID classId,  
                [in] mdFieldDef fieldToken,  
                [in] AppDomainID appDomainId,  
                [in] ThreadID threadId,  
                [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa0ae-105">参数</span><span class="sxs-lookup"><span data-stu-id="fa0ae-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="fa0ae-106">[in]包含请求的线程静态字段的类的 ID。</span><span class="sxs-lookup"><span data-stu-id="fa0ae-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="fa0ae-107">[in]请求的线程静态字段元数据标记。</span><span class="sxs-lookup"><span data-stu-id="fa0ae-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="fa0ae-108">[in] 应用程序域的 ID。</span><span class="sxs-lookup"><span data-stu-id="fa0ae-108">[in] The ID of the application domain.</span></span>  
  
 `threadId`  
 <span data-ttu-id="fa0ae-109">[in]请求的静态字段的作用域的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="fa0ae-109">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="fa0ae-110">[out]指向位于指定线程静态字段的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="fa0ae-110">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa0ae-111">备注</span><span class="sxs-lookup"><span data-stu-id="fa0ae-111">Remarks</span></span>  
 <span data-ttu-id="fa0ae-112">`GetThreadStaticAddress2`方法可能会返回以下值之一：</span><span class="sxs-lookup"><span data-stu-id="fa0ae-112">The `GetThreadStaticAddress2` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="fa0ae-113">如果尚未分配给定的静态字段中指定的上下文的地址 CORPROF_E_DATAINCOMPLETE HRESULT。</span><span class="sxs-lookup"><span data-stu-id="fa0ae-113">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="fa0ae-114">可能在垃圾回收堆的对象的地址。</span><span class="sxs-lookup"><span data-stu-id="fa0ae-114">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="fa0ae-115">使垃圾回收后，探查器不应假定它们是有效，则这些地址可能会回收后无效。</span><span class="sxs-lookup"><span data-stu-id="fa0ae-115">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="fa0ae-116">类的类构造函数完成之前，`GetThreadStaticAddress2`将返回 CORPROF_E_DATAINCOMPLETE 对于所有其静态字段，尽管可能已初始化的一些静态字段和根垃圾回收对象。</span><span class="sxs-lookup"><span data-stu-id="fa0ae-116">Before a class’s class constructor is completed, `GetThreadStaticAddress2` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
 <span data-ttu-id="fa0ae-117">[ICorProfilerInfo2::GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md)方法是类似于`GetThreadStaticAddress2`方法，但不是接受这些应用程序域参数。</span><span class="sxs-lookup"><span data-stu-id="fa0ae-117">The [ICorProfilerInfo2::GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) method is similar to the `GetThreadStaticAddress2` method, but does not accept an application domain argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa0ae-118">要求</span><span class="sxs-lookup"><span data-stu-id="fa0ae-118">Requirements</span></span>  
 <span data-ttu-id="fa0ae-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fa0ae-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa0ae-120">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fa0ae-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fa0ae-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa0ae-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa0ae-122">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa0ae-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa0ae-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa0ae-123">See also</span></span>

- [<span data-ttu-id="fa0ae-124">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="fa0ae-124">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="fa0ae-125">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="fa0ae-125">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="fa0ae-126">分析</span><span class="sxs-lookup"><span data-stu-id="fa0ae-126">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
