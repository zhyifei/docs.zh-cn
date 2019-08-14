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
ms.openlocfilehash: 79a1c80f1c7582bd0751c43dea1d35a4d4d1c661
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973977"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a><span data-ttu-id="ea535-102">ICorProfilerInfo10:: RequestReJITWithInliners 方法</span><span class="sxs-lookup"><span data-stu-id="ea535-102">ICorProfilerInfo10::RequestReJITWithInliners Method</span></span>
  
<span data-ttu-id="ea535-103">ReJITs 请求的方法, 以及所请求的方法的任何 inliners。</span><span class="sxs-lookup"><span data-stu-id="ea535-103">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="ea535-104">语法</span><span class="sxs-lookup"><span data-stu-id="ea535-104">Syntax</span></span>  
  
```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea535-105">参数</span><span class="sxs-lookup"><span data-stu-id="ea535-105">Parameters</span></span>  
 
 `dwRejitFlags` \
 <span data-ttu-id="ea535-106">中[COR_PRF_REJIT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-rejit-flags-enumeration.md)的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ea535-106">[in] A bitmask of [COR_PRF_REJIT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-rejit-flags-enumeration.md).</span></span>
 
 `cFunctions`  
 <span data-ttu-id="ea535-107">[in] 要重新编译的函数数目。</span><span class="sxs-lookup"><span data-stu-id="ea535-107">[in] The number of functions to recompile.</span></span>  
  
 `moduleIds`  
 <span data-ttu-id="ea535-108">[in] 指定（`module`、`methodDef`）对的 `moduleId` 部分，它标识要重新编译的函数。</span><span class="sxs-lookup"><span data-stu-id="ea535-108">[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>  
  
 `methodIds`  
 <span data-ttu-id="ea535-109">[in] 指定（`module`、`methodDef`）对的 `methodId` 部分，它标识要重新编译的函数。</span><span class="sxs-lookup"><span data-stu-id="ea535-109">[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>  

## <a name="remarks"></a><span data-ttu-id="ea535-110">备注</span><span class="sxs-lookup"><span data-stu-id="ea535-110">Remarks</span></span>  
  <span data-ttu-id="ea535-111">[RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)不会对内联方法进行任何跟踪。</span><span class="sxs-lookup"><span data-stu-id="ea535-111">[RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) does not do any tracking of inlined methods.</span></span> <span data-ttu-id="ea535-112">探查器应阻止内联或跟踪内联, 并为所有 inliners `RequestReJIT`调用以确保内联方法的每个实例都已 ReJITted。</span><span class="sxs-lookup"><span data-stu-id="ea535-112">The profiler was expected to either block inlining or track inlining and call `RequestReJIT` for all inliners to make sure every instance of an inlined method was ReJITted.</span></span> <span data-ttu-id="ea535-113">这会在附加上出现 ReJIT 问题, 因为探查器不会监视内联。</span><span class="sxs-lookup"><span data-stu-id="ea535-113">This poses a problem with ReJIT on attach, since the profiler is not present to monitor inlining.</span></span> <span data-ttu-id="ea535-114">可以调用此方法来保证完整的 inliners 集也会 ReJITted。</span><span class="sxs-lookup"><span data-stu-id="ea535-114">This method can be called to guarantee that the full set of inliners will be ReJITted as well.</span></span>  

## <a name="requirements"></a><span data-ttu-id="ea535-115">要求</span><span class="sxs-lookup"><span data-stu-id="ea535-115">Requirements</span></span>  
 <span data-ttu-id="ea535-116">**适用**请参阅[支持 .Net Core 的操作系统](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)。</span><span class="sxs-lookup"><span data-stu-id="ea535-116">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="ea535-117">**标头：** Corprof.idl, Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="ea535-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ea535-118">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea535-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea535-119">**.Net 版本:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea535-119">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ea535-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea535-120">See also</span></span>
- [<span data-ttu-id="ea535-121">ICorProfilerInfo10 接口</span><span class="sxs-lookup"><span data-stu-id="ea535-121">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

