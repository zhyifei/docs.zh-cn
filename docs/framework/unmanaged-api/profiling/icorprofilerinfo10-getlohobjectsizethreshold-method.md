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
ms.openlocfilehash: 95473a8ce8d5fd7540228ecd9767448e51b5b326
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868979"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="6318a-102">ICorProfilerInfo10：： GetLOHObjectSizeThreshold 方法</span><span class="sxs-lookup"><span data-stu-id="6318a-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="6318a-103">获取已配置的大型对象堆（LOH）阈值的值。</span><span class="sxs-lookup"><span data-stu-id="6318a-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="6318a-104">语法</span><span class="sxs-lookup"><span data-stu-id="6318a-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a><span data-ttu-id="6318a-105">参数</span><span class="sxs-lookup"><span data-stu-id="6318a-105">Parameters</span></span>

- `pThreshold`

  <span data-ttu-id="6318a-106">\[out] 大对象堆阈值（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="6318a-106">\[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="6318a-107">备注</span><span class="sxs-lookup"><span data-stu-id="6318a-107">Remarks</span></span>

<span data-ttu-id="6318a-108">大于大型对象堆阈值的对象将在大型对象堆上分配。</span><span class="sxs-lookup"><span data-stu-id="6318a-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="6318a-109">从 .NET Core 3.0 开始，可以配置大对象堆阈值，`pThreshold` 将包含活动的大型对象堆阈值大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="6318a-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="6318a-110">需求</span><span class="sxs-lookup"><span data-stu-id="6318a-110">Requirements</span></span>

<span data-ttu-id="6318a-111">**平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)。</span><span class="sxs-lookup"><span data-stu-id="6318a-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="6318a-112">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6318a-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="6318a-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6318a-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="6318a-114">**.Net 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6318a-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6318a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6318a-115">See also</span></span>

- [<span data-ttu-id="6318a-116">ICorProfilerInfo10 接口</span><span class="sxs-lookup"><span data-stu-id="6318a-116">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
