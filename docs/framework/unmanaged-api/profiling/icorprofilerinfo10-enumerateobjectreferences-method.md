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
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="5c651-102">ICorProfilerInfo10：： EnumerateObjectReferences 方法</span><span class="sxs-lookup"><span data-stu-id="5c651-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>

<span data-ttu-id="5c651-103">给定 ObjectID、callback 和 clientData，枚举每个对象引用（如果有）。</span><span class="sxs-lookup"><span data-stu-id="5c651-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>

## <a name="syntax"></a><span data-ttu-id="5c651-104">语法</span><span class="sxs-lookup"><span data-stu-id="5c651-104">Syntax</span></span>

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

#### <a name="parameters"></a><span data-ttu-id="5c651-105">参数</span><span class="sxs-lookup"><span data-stu-id="5c651-105">Parameters</span></span>

`objectId` \
<span data-ttu-id="5c651-106">中要在其上枚举引用的对象。</span><span class="sxs-lookup"><span data-stu-id="5c651-106">[in] The object to enumerate references on.</span></span>

`callback` \
<span data-ttu-id="5c651-107">中将用对象的引用调用的函数。</span><span class="sxs-lookup"><span data-stu-id="5c651-107">[in] The function that will be called with the references for the object.</span></span>

`clientData` \
<span data-ttu-id="5c651-108">中探查器提供的要传递到 `callback` 函数的数据。</span><span class="sxs-lookup"><span data-stu-id="5c651-108">[in] Profiler-provided data to pass to the `callback` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="5c651-109">备注</span><span class="sxs-lookup"><span data-stu-id="5c651-109">Remarks</span></span>

<span data-ttu-id="5c651-110">`EnumerateObjectReferences` 方法类似于[ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)，只不过它会按需对探查器进行引用，而不是预先分配用于存储引用的数组。</span><span class="sxs-lookup"><span data-stu-id="5c651-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>

## <a name="requirements"></a><span data-ttu-id="5c651-111">要求</span><span class="sxs-lookup"><span data-stu-id="5c651-111">Requirements</span></span>

<span data-ttu-id="5c651-112">**平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)。</span><span class="sxs-lookup"><span data-stu-id="5c651-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="5c651-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5c651-113">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="5c651-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c651-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="5c651-115">**.Net 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c651-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5c651-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c651-116">See also</span></span>

- [<span data-ttu-id="5c651-117">ICorProfilerInfo10 接口</span><span class="sxs-lookup"><span data-stu-id="5c651-117">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
