---
title: ICorProfilerInfo10::GetLOHObjectSizeThreshold
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.GetLOHObjectSizeThreshold
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 7a38ee4ae74ca5b96dd082e752fc733eb85fca3f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427019"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="a1383-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span><span class="sxs-lookup"><span data-stu-id="a1383-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="a1383-103">Gets the value of the configured large object heap (LOH) threshold.</span><span class="sxs-lookup"><span data-stu-id="a1383-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="a1383-104">语法</span><span class="sxs-lookup"><span data-stu-id="a1383-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

#### <a name="parameters"></a><span data-ttu-id="a1383-105">参数</span><span class="sxs-lookup"><span data-stu-id="a1383-105">Parameters</span></span>

`pThreshold` \
<span data-ttu-id="a1383-106">[out] The large object heap threshold in bytes.</span><span class="sxs-lookup"><span data-stu-id="a1383-106">[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="a1383-107">备注</span><span class="sxs-lookup"><span data-stu-id="a1383-107">Remarks</span></span>

<span data-ttu-id="a1383-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span><span class="sxs-lookup"><span data-stu-id="a1383-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="a1383-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span><span class="sxs-lookup"><span data-stu-id="a1383-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="a1383-110">要求</span><span class="sxs-lookup"><span data-stu-id="a1383-110">Requirements</span></span>

<span data-ttu-id="a1383-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="a1383-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="a1383-112">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a1383-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="a1383-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1383-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="a1383-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1383-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a1383-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1383-115">See also</span></span>

- [<span data-ttu-id="a1383-116">ICorProfilerInfo10 Interface</span><span class="sxs-lookup"><span data-stu-id="a1383-116">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
