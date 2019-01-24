---
title: ICorProfilerInfo2::GetThreadStaticAddress 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadStaticAddress
helpviewer_keywords:
- GetThreadStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetThreadStaticAddress method [.NET Framework profiling]
ms.assetid: 8e7dbf14-98a2-4384-a950-58a7640e59df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3574d7e889481931f40dbfb3158ad523c7e5637e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534990"
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a><span data-ttu-id="08d6a-102">ICorProfilerInfo2::GetThreadStaticAddress 方法</span><span class="sxs-lookup"><span data-stu-id="08d6a-102">ICorProfilerInfo2::GetThreadStaticAddress Method</span></span>
<span data-ttu-id="08d6a-103">获取指定在范围内的指定线程的线程静态字段的地址。</span><span class="sxs-lookup"><span data-stu-id="08d6a-103">Gets the address of the specified thread-static field that is in the scope of the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08d6a-104">语法</span><span class="sxs-lookup"><span data-stu-id="08d6a-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08d6a-105">参数</span><span class="sxs-lookup"><span data-stu-id="08d6a-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="08d6a-106">[in]包含请求的线程静态字段的类的 ID。</span><span class="sxs-lookup"><span data-stu-id="08d6a-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="08d6a-107">[in]请求的线程静态字段元数据标记。</span><span class="sxs-lookup"><span data-stu-id="08d6a-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `threadId`  
 <span data-ttu-id="08d6a-108">[in]请求的静态字段的作用域的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="08d6a-108">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="08d6a-109">[out]指向位于指定线程静态字段的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="08d6a-109">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08d6a-110">备注</span><span class="sxs-lookup"><span data-stu-id="08d6a-110">Remarks</span></span>  
 <span data-ttu-id="08d6a-111">`GetThreadStaticAddress`方法可能会返回以下值之一：</span><span class="sxs-lookup"><span data-stu-id="08d6a-111">The `GetThreadStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="08d6a-112">如果尚未分配给定的静态字段中指定的上下文的地址 CORPROF_E_DATAINCOMPLETE HRESULT。</span><span class="sxs-lookup"><span data-stu-id="08d6a-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="08d6a-113">可能在垃圾回收堆的对象的地址。</span><span class="sxs-lookup"><span data-stu-id="08d6a-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="08d6a-114">垃圾回收后，这些地址可能会变为无效操作后垃圾收集探查器不应假定其是否有效。</span><span class="sxs-lookup"><span data-stu-id="08d6a-114">These addresses may become invalid after garbage collection, so after garbage collection profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="08d6a-115">类的类构造函数完成之前，`GetThreadStaticAddress`将返回 CORPROF_E_DATAINCOMPLETE 对于所有其静态字段，尽管可能已初始化的一些静态字段和根垃圾回收对象。</span><span class="sxs-lookup"><span data-stu-id="08d6a-115">Before a class’s class constructor is completed, `GetThreadStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08d6a-116">要求</span><span class="sxs-lookup"><span data-stu-id="08d6a-116">Requirements</span></span>  
 <span data-ttu-id="08d6a-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="08d6a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08d6a-118">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="08d6a-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="08d6a-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08d6a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08d6a-120">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08d6a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08d6a-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="08d6a-121">See also</span></span>
- [<span data-ttu-id="08d6a-122">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="08d6a-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="08d6a-123">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="08d6a-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
