---
title: ICorProfilerInfo10::RequestReJITWithInliners
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.RequestReJITWithInliners
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 5822136eb1a7f582bcfae901a99775950e586198
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863174"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a><span data-ttu-id="c820b-102">ICorProfilerInfo10：： RequestReJITWithInliners 方法</span><span class="sxs-lookup"><span data-stu-id="c820b-102">ICorProfilerInfo10::RequestReJITWithInliners Method</span></span>

<span data-ttu-id="c820b-103">ReJITs 请求的方法，以及所请求的方法的任何 inliners。</span><span class="sxs-lookup"><span data-stu-id="c820b-103">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>

## <a name="syntax"></a><span data-ttu-id="c820b-104">语法</span><span class="sxs-lookup"><span data-stu-id="c820b-104">Syntax</span></span>

```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```

## <a name="parameters"></a><span data-ttu-id="c820b-105">参数</span><span class="sxs-lookup"><span data-stu-id="c820b-105">Parameters</span></span>

- `dwRejitFlags`

  <span data-ttu-id="c820b-106">\[in] [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md)的位掩码。</span><span class="sxs-lookup"><span data-stu-id="c820b-106">\[in] A bitmask of [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md).</span></span>

- `cFunctions`

  <span data-ttu-id="c820b-107">\[] 要重新编译的函数的数目。</span><span class="sxs-lookup"><span data-stu-id="c820b-107">\[in] The number of functions to recompile.</span></span>

- `moduleIds`

  <span data-ttu-id="c820b-108">\[中的] 指定用于标识要重新编译的函数的（`module`，`methodDef`）对的 `moduleId` 部分。</span><span class="sxs-lookup"><span data-stu-id="c820b-108">\[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

- `methodIds`

  <span data-ttu-id="c820b-109">\[中的] 指定用于标识要重新编译的函数的（`module`，`methodDef`）对的 `methodId` 部分。</span><span class="sxs-lookup"><span data-stu-id="c820b-109">\[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>

## <a name="remarks"></a><span data-ttu-id="c820b-110">备注</span><span class="sxs-lookup"><span data-stu-id="c820b-110">Remarks</span></span>

<span data-ttu-id="c820b-111">[RequestReJIT](icorprofilerinfo4-requestrejit-method.md)不会对内联方法进行任何跟踪。</span><span class="sxs-lookup"><span data-stu-id="c820b-111">[RequestReJIT](icorprofilerinfo4-requestrejit-method.md) does not do any tracking of inlined methods.</span></span> <span data-ttu-id="c820b-112">探查器应阻止内联或跟踪内联，并为所有 inliners 调用 `RequestReJIT`，以确保内联方法的每个实例都已 ReJITted。</span><span class="sxs-lookup"><span data-stu-id="c820b-112">The profiler was expected to either block inlining or track inlining and call `RequestReJIT` for all inliners to make sure every instance of an inlined method was ReJITted.</span></span> <span data-ttu-id="c820b-113">这会在附加上出现 ReJIT 问题，因为探查器不会监视内联。</span><span class="sxs-lookup"><span data-stu-id="c820b-113">This poses a problem with ReJIT on attach, since the profiler is not present to monitor inlining.</span></span> <span data-ttu-id="c820b-114">可以调用此方法来保证完整的 inliners 集也会 ReJITted。</span><span class="sxs-lookup"><span data-stu-id="c820b-114">This method can be called to guarantee that the full set of inliners will be ReJITted as well.</span></span>

## <a name="requirements"></a><span data-ttu-id="c820b-115">需求</span><span class="sxs-lookup"><span data-stu-id="c820b-115">Requirements</span></span>

<span data-ttu-id="c820b-116">**平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)。</span><span class="sxs-lookup"><span data-stu-id="c820b-116">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="c820b-117">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c820b-117">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="c820b-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c820b-118">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c820b-119">**.Net 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c820b-119">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c820b-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c820b-120">See also</span></span>

- [<span data-ttu-id="c820b-121">ICorProfilerInfo10 接口</span><span class="sxs-lookup"><span data-stu-id="c820b-121">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
