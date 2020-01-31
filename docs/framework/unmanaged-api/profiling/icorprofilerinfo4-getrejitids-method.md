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
ms.openlocfilehash: 9069498a4f62f4d9dbb50a7075323b14c3cc5ab9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868442"
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="61520-102">ICorProfilerInfo4::GetReJITIDs 方法</span><span class="sxs-lookup"><span data-stu-id="61520-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="61520-103">返回 Id 的数组，这些 Id 标识仍分配的指定函数的所有 JIT 重新编译版本。</span><span class="sxs-lookup"><span data-stu-id="61520-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="61520-104">这包括 JIT 重新编译的函数版本，这些版本已进行了还原但尚未释放（例如，当包含还原函数的应用程序域仍在使用时）。</span><span class="sxs-lookup"><span data-stu-id="61520-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61520-105">语法</span><span class="sxs-lookup"><span data-stu-id="61520-105">Syntax</span></span>  
  
```cpp
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61520-106">参数</span><span class="sxs-lookup"><span data-stu-id="61520-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="61520-107">中要枚举其版本的函数实例的 `FunctionID`。</span><span class="sxs-lookup"><span data-stu-id="61520-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="61520-108">中`reJitIds` 数组中分配的 JIT 重新编译 Id 的数目。</span><span class="sxs-lookup"><span data-stu-id="61520-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="61520-109">弄JIT 重新编译的 Id 的实际数目。</span><span class="sxs-lookup"><span data-stu-id="61520-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="61520-110">弄调用方分配的数组，其中包含指定函数的 JIT 重新编译的 Id。</span><span class="sxs-lookup"><span data-stu-id="61520-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61520-111">备注</span><span class="sxs-lookup"><span data-stu-id="61520-111">Remarks</span></span>  
 <span data-ttu-id="61520-112">`GetReJITIDs` 枚举给定函数实例的活动 JIT 重新编译的 Id。</span><span class="sxs-lookup"><span data-stu-id="61520-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="61520-113">它遵循的使用模式与接受调用方分配的缓冲区的其他 `ICorProfilerInfo` 函数相同。</span><span class="sxs-lookup"><span data-stu-id="61520-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61520-114">需求</span><span class="sxs-lookup"><span data-stu-id="61520-114">Requirements</span></span>  
 <span data-ttu-id="61520-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="61520-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61520-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="61520-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="61520-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61520-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61520-118">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61520-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61520-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61520-119">See also</span></span>

- [<span data-ttu-id="61520-120">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="61520-120">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="61520-121">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="61520-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="61520-122">分析</span><span class="sxs-lookup"><span data-stu-id="61520-122">Profiling</span></span>](index.md)
