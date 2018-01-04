---
title: "ICorProfilerInfo2::GetArrayObjectInfo 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetArrayObjectInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetArrayObjectInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo method [.NET Framework profiling]
- GetArrayObjectInfo method [.NET Framework profiling]
ms.assetid: bda75017-739f-4ce5-9000-f3b526e8473c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b20530081f7c9ad32f4702099abacc78e052ebd9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a><span data-ttu-id="aa12c-102">ICorProfilerInfo2::GetArrayObjectInfo 方法</span><span class="sxs-lookup"><span data-stu-id="aa12c-102">ICorProfilerInfo2::GetArrayObjectInfo Method</span></span>
<span data-ttu-id="aa12c-103">获取一个数组对象的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="aa12c-103">Gets detailed information about an array object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa12c-104">语法</span><span class="sxs-lookup"><span data-stu-id="aa12c-104">Syntax</span></span>  
  
```  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa12c-105">参数</span><span class="sxs-lookup"><span data-stu-id="aa12c-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="aa12c-106">[in]有效的数组对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="aa12c-106">[in] The ID of a valid array object.</span></span>  
  
 `cDimensions`  
 <span data-ttu-id="aa12c-107">[in]数组的秩 （维数）。</span><span class="sxs-lookup"><span data-stu-id="aa12c-107">[in] The rank (number of dimensions) of the array.</span></span>  
  
 `pDimensionSizes`  
 <span data-ttu-id="aa12c-108">[out]一个数组，包含整数，每个表示数组的维度的大小。</span><span class="sxs-lookup"><span data-stu-id="aa12c-108">[out] An array that contains integers, each representing the size of a dimension of the array.</span></span>  
  
 `pDimensionLowerBounds`  
 <span data-ttu-id="aa12c-109">[out]包含整数的数组，表示较低的每个绑定的数组的维度。</span><span class="sxs-lookup"><span data-stu-id="aa12c-109">[out] An array that contains integers, each representing the lower bound of a dimension of the array.</span></span>  
  
 `ppData`  
 <span data-ttu-id="aa12c-110">[out]指向数组，它根据 c + + 约定布局的原始缓冲区的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="aa12c-110">[out] A pointer to the address of the raw buffer for the array, which is laid out according to the C++ convention.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa12c-111">备注</span><span class="sxs-lookup"><span data-stu-id="aa12c-111">Remarks</span></span>  
 <span data-ttu-id="aa12c-112">`pDimensionSizes`和`pDimensionLowerBounds`是并行数组，因此位于每个数组中的相同索引处的元素是相同的实体的特征。</span><span class="sxs-lookup"><span data-stu-id="aa12c-112">The `pDimensionSizes` and `pDimensionLowerBounds` are parallel arrays, so the elements located at the same index in each array are characteristics of the same entity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa12c-113">惠?</span><span class="sxs-lookup"><span data-stu-id="aa12c-113">Requirements</span></span>  
 <span data-ttu-id="aa12c-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aa12c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa12c-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aa12c-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aa12c-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa12c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa12c-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa12c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa12c-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa12c-118">See Also</span></span>  
 [<span data-ttu-id="aa12c-119">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="aa12c-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="aa12c-120">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="aa12c-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
