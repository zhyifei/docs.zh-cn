---
title: ICorProfilerInfo4::GetReJITIDs 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetReJITIDs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 805ceb60d2ac122df2382656b95b7bf5e7509bfc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855937"
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="9c791-102">ICorProfilerInfo4::GetReJITIDs 方法</span><span class="sxs-lookup"><span data-stu-id="9c791-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="9c791-103">返回 Id 的数组，这些 Id 标识仍分配的指定函数的所有 JIT 重新编译版本。</span><span class="sxs-lookup"><span data-stu-id="9c791-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="9c791-104">这包括 JIT 重新编译的函数版本，这些版本已进行了还原但尚未释放（例如，当包含还原函数的应用程序域仍在使用时）。</span><span class="sxs-lookup"><span data-stu-id="9c791-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c791-105">语法</span><span class="sxs-lookup"><span data-stu-id="9c791-105">Syntax</span></span>  
  
```cpp
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c791-106">参数</span><span class="sxs-lookup"><span data-stu-id="9c791-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="9c791-107">中`FunctionID`要枚举其版本的函数实例的。</span><span class="sxs-lookup"><span data-stu-id="9c791-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="9c791-108">中在`reJitIds`数组中分配的 JIT 重新编译的 id 的数目。</span><span class="sxs-lookup"><span data-stu-id="9c791-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="9c791-109">弄JIT 重新编译的 Id 的实际数目。</span><span class="sxs-lookup"><span data-stu-id="9c791-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="9c791-110">弄调用方分配的数组，其中包含指定函数的 JIT 重新编译的 Id。</span><span class="sxs-lookup"><span data-stu-id="9c791-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c791-111">备注</span><span class="sxs-lookup"><span data-stu-id="9c791-111">Remarks</span></span>  
 <span data-ttu-id="9c791-112">`GetReJITIDs`枚举给定函数实例的活动 JIT 重新编译的 Id。</span><span class="sxs-lookup"><span data-stu-id="9c791-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="9c791-113">它遵循与接受调用方分配的`ICorProfilerInfo`缓冲区的其他函数相同的使用模式。</span><span class="sxs-lookup"><span data-stu-id="9c791-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c791-114">要求</span><span class="sxs-lookup"><span data-stu-id="9c791-114">Requirements</span></span>  
 <span data-ttu-id="9c791-115">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9c791-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c791-116">**标头：** Corprof.idl，Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="9c791-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9c791-117">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c791-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c791-118">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c791-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c791-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c791-119">See also</span></span>

- [<span data-ttu-id="9c791-120">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="9c791-120">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="9c791-121">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="9c791-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="9c791-122">分析</span><span class="sxs-lookup"><span data-stu-id="9c791-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
