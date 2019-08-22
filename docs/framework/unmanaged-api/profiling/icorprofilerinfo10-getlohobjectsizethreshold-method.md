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
ms.openlocfilehash: 8c9a85e9f00027f597795eea55a9bbb0364790f8
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661243"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="1b8a9-102">ICorProfilerInfo10:: GetLOHObjectSizeThreshold 方法</span><span class="sxs-lookup"><span data-stu-id="1b8a9-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="1b8a9-103">获取已配置的大型对象堆 (LOH) 阈值的值。</span><span class="sxs-lookup"><span data-stu-id="1b8a9-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="1b8a9-104">语法</span><span class="sxs-lookup"><span data-stu-id="1b8a9-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

#### <a name="parameters"></a><span data-ttu-id="1b8a9-105">参数</span><span class="sxs-lookup"><span data-stu-id="1b8a9-105">Parameters</span></span>

`pThreshold` \
<span data-ttu-id="1b8a9-106">弄大型对象堆阈值 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="1b8a9-106">[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b8a9-107">备注</span><span class="sxs-lookup"><span data-stu-id="1b8a9-107">Remarks</span></span>

<span data-ttu-id="1b8a9-108">大于大型对象堆阈值的对象将在大型对象堆上分配。</span><span class="sxs-lookup"><span data-stu-id="1b8a9-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="1b8a9-109">从 .net Core 3.0 开始, 大型对象堆阈值是可配置`pThreshold`的, 将包含活动的大型对象堆阈值大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="1b8a9-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="1b8a9-110">要求</span><span class="sxs-lookup"><span data-stu-id="1b8a9-110">Requirements</span></span>

<span data-ttu-id="1b8a9-111">**适用**请参阅[支持 .Net Core 的操作系统](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)。</span><span class="sxs-lookup"><span data-stu-id="1b8a9-111">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="1b8a9-112">**标头：** Corprof.idl, Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="1b8a9-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="1b8a9-113">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b8a9-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="1b8a9-114">**.Net 版本:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b8a9-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1b8a9-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b8a9-115">See also</span></span>

- [<span data-ttu-id="1b8a9-116">ICorProfilerInfo10 接口</span><span class="sxs-lookup"><span data-stu-id="1b8a9-116">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
