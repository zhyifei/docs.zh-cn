---
title: ICorProfilerInfo10::EnumerateObjectReferences
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.EnumerateObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: d6518612c213d21c2dc7d80878121ccd3b7e2abb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449851"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="a7b69-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span><span class="sxs-lookup"><span data-stu-id="a7b69-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>

<span data-ttu-id="a7b69-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span><span class="sxs-lookup"><span data-stu-id="a7b69-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>

## <a name="syntax"></a><span data-ttu-id="a7b69-104">语法</span><span class="sxs-lookup"><span data-stu-id="a7b69-104">Syntax</span></span>

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

#### <a name="parameters"></a><span data-ttu-id="a7b69-105">参数</span><span class="sxs-lookup"><span data-stu-id="a7b69-105">Parameters</span></span>

`objectId` \
<span data-ttu-id="a7b69-106">[in] The object to enumerate references on.</span><span class="sxs-lookup"><span data-stu-id="a7b69-106">[in] The object to enumerate references on.</span></span>

`callback` \
<span data-ttu-id="a7b69-107">[in] The function that will be called with the references for the object.</span><span class="sxs-lookup"><span data-stu-id="a7b69-107">[in] The function that will be called with the references for the object.</span></span>

`clientData` \
<span data-ttu-id="a7b69-108">[in] Profiler-provided data to pass to the `callback` function.</span><span class="sxs-lookup"><span data-stu-id="a7b69-108">[in] Profiler-provided data to pass to the `callback` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="a7b69-109">备注</span><span class="sxs-lookup"><span data-stu-id="a7b69-109">Remarks</span></span>

<span data-ttu-id="a7b69-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span><span class="sxs-lookup"><span data-stu-id="a7b69-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>

## <a name="requirements"></a><span data-ttu-id="a7b69-111">要求</span><span class="sxs-lookup"><span data-stu-id="a7b69-111">Requirements</span></span>

<span data-ttu-id="a7b69-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="a7b69-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="a7b69-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7b69-113">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="a7b69-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7b69-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="a7b69-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7b69-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a7b69-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7b69-116">See also</span></span>

- [<span data-ttu-id="a7b69-117">ICorProfilerInfo10 Interface</span><span class="sxs-lookup"><span data-stu-id="a7b69-117">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
