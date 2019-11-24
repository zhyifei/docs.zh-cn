---
title: ICorProfilerInfo9::GetNativeCodeStartAddresses
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetNativeCodeStartAddresses
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 7593e8873c2714df85146903c0052a9909a95ccd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444713"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a><span data-ttu-id="c6dc3-102">ICorProfilerInfo9::GetNativeCodeStartAddresses Method</span><span class="sxs-lookup"><span data-stu-id="c6dc3-102">ICorProfilerInfo9::GetNativeCodeStartAddresses Method</span></span>

<span data-ttu-id="c6dc3-103">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span><span class="sxs-lookup"><span data-stu-id="c6dc3-103">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span>

## <a name="syntax"></a><span data-ttu-id="c6dc3-104">语法</span><span class="sxs-lookup"><span data-stu-id="c6dc3-104">Syntax</span></span>

```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```

#### <a name="parameters"></a><span data-ttu-id="c6dc3-105">参数</span><span class="sxs-lookup"><span data-stu-id="c6dc3-105">Parameters</span></span>

`functionId` \
<span data-ttu-id="c6dc3-106">[in] The ID of the function whose native code start addresses should be returned.</span><span class="sxs-lookup"><span data-stu-id="c6dc3-106">[in] The ID of the function whose native code start addresses should be returned.</span></span>

`reJitId` \
<span data-ttu-id="c6dc3-107">[in] JIT 重新编译的函数的标识。</span><span class="sxs-lookup"><span data-stu-id="c6dc3-107">[in] The identity of the JIT-recompiled function.</span></span>

`cCodeStartAddresses` \
<span data-ttu-id="c6dc3-108">[in] `codeStartAddresses` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="c6dc3-108">[in] The maximum size of the `codeStartAddresses` array.</span></span>

`pcCodeStartAddresses` \
<span data-ttu-id="c6dc3-109">[out] The number of available addresses.</span><span class="sxs-lookup"><span data-stu-id="c6dc3-109">[out] The number of available addresses.</span></span>

`codeStartAddresses` \
<span data-ttu-id="c6dc3-110">[out] An array of `UINT_PTR`, each one of which is the start address for a native body for the specified function.</span><span class="sxs-lookup"><span data-stu-id="c6dc3-110">[out] An array of `UINT_PTR`, each one of which is the start address for a native body for the specified function.</span></span>

## <a name="remarks"></a><span data-ttu-id="c6dc3-111">备注</span><span class="sxs-lookup"><span data-stu-id="c6dc3-111">Remarks</span></span>

<span data-ttu-id="c6dc3-112">When tiered compilation is enabled, a function may have more than one native code body.</span><span class="sxs-lookup"><span data-stu-id="c6dc3-112">When tiered compilation is enabled, a function may have more than one native code body.</span></span>

## <a name="requirements"></a><span data-ttu-id="c6dc3-113">要求</span><span class="sxs-lookup"><span data-stu-id="c6dc3-113">Requirements</span></span>

<span data-ttu-id="c6dc3-114">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="c6dc3-114">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="c6dc3-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c6dc3-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="c6dc3-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6dc3-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c6dc3-117">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6dc3-117">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c6dc3-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6dc3-118">See also</span></span>

- [<span data-ttu-id="c6dc3-119">ICorProfilerInfo9 Interface</span><span class="sxs-lookup"><span data-stu-id="c6dc3-119">ICorProfilerInfo9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)
