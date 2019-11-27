---
title: ICorProfilerInfo2::GetArrayObjectInfo 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetArrayObjectInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo method [.NET Framework profiling]
- GetArrayObjectInfo method [.NET Framework profiling]
ms.assetid: bda75017-739f-4ce5-9000-f3b526e8473c
topic_type:
- apiref
ms.openlocfilehash: 97b127c9a6aac0a0fefe25faf294791dcd2c8e41
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436031"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a><span data-ttu-id="77ff2-102">ICorProfilerInfo2::GetArrayObjectInfo 方法</span><span class="sxs-lookup"><span data-stu-id="77ff2-102">ICorProfilerInfo2::GetArrayObjectInfo Method</span></span>
<span data-ttu-id="77ff2-103">获取有关数组对象的详细信息。</span><span class="sxs-lookup"><span data-stu-id="77ff2-103">Gets detailed information about an array object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77ff2-104">语法</span><span class="sxs-lookup"><span data-stu-id="77ff2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77ff2-105">参数</span><span class="sxs-lookup"><span data-stu-id="77ff2-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="77ff2-106">中有效数组对象的 ID。</span><span class="sxs-lookup"><span data-stu-id="77ff2-106">[in] The ID of a valid array object.</span></span>  
  
 `cDimensions`  
 <span data-ttu-id="77ff2-107">中数组的秩（维数）。</span><span class="sxs-lookup"><span data-stu-id="77ff2-107">[in] The rank (number of dimensions) of the array.</span></span>  
  
 `pDimensionSizes`  
 <span data-ttu-id="77ff2-108">弄一个包含整数的数组，每个整数表示数组维度的大小。</span><span class="sxs-lookup"><span data-stu-id="77ff2-108">[out] An array that contains integers, each representing the size of a dimension of the array.</span></span>  
  
 `pDimensionLowerBounds`  
 <span data-ttu-id="77ff2-109">弄一个包含整数的数组，其中每个整数表示数组维度的下限。</span><span class="sxs-lookup"><span data-stu-id="77ff2-109">[out] An array that contains integers, each representing the lower bound of a dimension of the array.</span></span>  
  
 `ppData`  
 <span data-ttu-id="77ff2-110">弄一个指针，它指向数组的原始缓冲区的地址，该地址根据C++约定进行布局。</span><span class="sxs-lookup"><span data-stu-id="77ff2-110">[out] A pointer to the address of the raw buffer for the array, which is laid out according to the C++ convention.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77ff2-111">备注</span><span class="sxs-lookup"><span data-stu-id="77ff2-111">Remarks</span></span>  
 <span data-ttu-id="77ff2-112">`pDimensionSizes` 和 `pDimensionLowerBounds` 是并行数组，因此位于每个数组中同一索引处的元素是同一实体的特征。</span><span class="sxs-lookup"><span data-stu-id="77ff2-112">The `pDimensionSizes` and `pDimensionLowerBounds` are parallel arrays, so the elements located at the same index in each array are characteristics of the same entity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77ff2-113">要求</span><span class="sxs-lookup"><span data-stu-id="77ff2-113">Requirements</span></span>  
 <span data-ttu-id="77ff2-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="77ff2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77ff2-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="77ff2-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="77ff2-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77ff2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77ff2-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77ff2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77ff2-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77ff2-118">See also</span></span>

- [<span data-ttu-id="77ff2-119">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="77ff2-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="77ff2-120">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="77ff2-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
