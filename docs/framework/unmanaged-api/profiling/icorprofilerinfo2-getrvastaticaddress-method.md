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
ms.openlocfilehash: db768c97a2d1a0fd5ee42ecfb121fb96d3092e79
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433023"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="4308e-102">ICorProfilerInfo2::GetRVAStaticAddress 方法</span><span class="sxs-lookup"><span data-stu-id="4308e-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>
<span data-ttu-id="4308e-103">Gets the address of the specified relative virtual address (RVA) static field.</span><span class="sxs-lookup"><span data-stu-id="4308e-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4308e-104">语法</span><span class="sxs-lookup"><span data-stu-id="4308e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4308e-105">参数</span><span class="sxs-lookup"><span data-stu-id="4308e-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="4308e-106">[in] The ID of the class that contains the requested RVA-static field.</span><span class="sxs-lookup"><span data-stu-id="4308e-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="4308e-107">[in] Metadata token for the requested RVA-static field.</span><span class="sxs-lookup"><span data-stu-id="4308e-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="4308e-108">[out] A pointer to the address of the RVA-static field.</span><span class="sxs-lookup"><span data-stu-id="4308e-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4308e-109">备注</span><span class="sxs-lookup"><span data-stu-id="4308e-109">Remarks</span></span>  
 <span data-ttu-id="4308e-110">The `GetRVAStaticAddress` method may return one of the following:</span><span class="sxs-lookup"><span data-stu-id="4308e-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="4308e-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span><span class="sxs-lookup"><span data-stu-id="4308e-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="4308e-112">The addresses of objects that may be in the garbage collection heap.</span><span class="sxs-lookup"><span data-stu-id="4308e-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="4308e-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span><span class="sxs-lookup"><span data-stu-id="4308e-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="4308e-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span><span class="sxs-lookup"><span data-stu-id="4308e-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4308e-115">要求</span><span class="sxs-lookup"><span data-stu-id="4308e-115">Requirements</span></span>  
 <span data-ttu-id="4308e-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4308e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4308e-117">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4308e-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4308e-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4308e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4308e-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4308e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4308e-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="4308e-120">See also</span></span>

- [<span data-ttu-id="4308e-121">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="4308e-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="4308e-122">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="4308e-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
