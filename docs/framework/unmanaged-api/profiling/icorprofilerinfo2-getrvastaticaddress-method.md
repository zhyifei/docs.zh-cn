---
title: ICorProfilerInfo2::GetRVAStaticAddress 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetRVAStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d3749c600d54671071efbec8322e050cde446c27
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158596"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="b03b2-102">ICorProfilerInfo2::GetRVAStaticAddress 方法</span><span class="sxs-lookup"><span data-stu-id="b03b2-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>
<span data-ttu-id="b03b2-103">获取指定的相对虚拟地址 (RVA) 的静态字段的地址。</span><span class="sxs-lookup"><span data-stu-id="b03b2-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b03b2-104">语法</span><span class="sxs-lookup"><span data-stu-id="b03b2-104">Syntax</span></span>  
  
```  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b03b2-105">参数</span><span class="sxs-lookup"><span data-stu-id="b03b2-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="b03b2-106">[in]包含请求的 RVA 静态字段的类的 ID。</span><span class="sxs-lookup"><span data-stu-id="b03b2-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="b03b2-107">[in]请求的 RVA 静态字段的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="b03b2-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="b03b2-108">[out]指向 RVA 静态字段的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="b03b2-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b03b2-109">备注</span><span class="sxs-lookup"><span data-stu-id="b03b2-109">Remarks</span></span>  
 <span data-ttu-id="b03b2-110">`GetRVAStaticAddress`方法可能会返回以下值之一：</span><span class="sxs-lookup"><span data-stu-id="b03b2-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="b03b2-111">如果尚未分配给定的静态字段中指定的上下文的地址 CORPROF_E_DATAINCOMPLETE HRESULT。</span><span class="sxs-lookup"><span data-stu-id="b03b2-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="b03b2-112">可能在垃圾回收堆的对象的地址。</span><span class="sxs-lookup"><span data-stu-id="b03b2-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="b03b2-113">使垃圾回收后，探查器不应假定它们是有效，则这些地址可能会回收后无效。</span><span class="sxs-lookup"><span data-stu-id="b03b2-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="b03b2-114">类的类构造函数完成之前，`GetRVAStaticAddress`将返回 CORPROF_E_DATAINCOMPLETE 对于所有其静态字段，虽然一些静态字段可能已初始化，并且可能根垃圾回收对象。</span><span class="sxs-lookup"><span data-stu-id="b03b2-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b03b2-115">要求</span><span class="sxs-lookup"><span data-stu-id="b03b2-115">Requirements</span></span>  
 <span data-ttu-id="b03b2-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b03b2-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b03b2-117">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b03b2-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b03b2-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b03b2-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b03b2-119">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="b03b2-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b03b2-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="b03b2-120">See also</span></span>

- [<span data-ttu-id="b03b2-121">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="b03b2-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="b03b2-122">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="b03b2-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
