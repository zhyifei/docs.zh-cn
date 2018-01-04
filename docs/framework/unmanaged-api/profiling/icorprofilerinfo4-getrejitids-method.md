---
title: "ICorProfilerInfo4::GetReJITIDs 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.GetReJITIDs
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fb1e507bea6f52e4959f241f1507807a76c0ec5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="8bf13-102">ICorProfilerInfo4::GetReJITIDs 方法</span><span class="sxs-lookup"><span data-stu-id="8bf13-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="8bf13-103">返回一个标识 JIT 重新编译的所有版本的指定的函数仍分配的 Id 数组。</span><span class="sxs-lookup"><span data-stu-id="8bf13-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="8bf13-104">这包括已随后还原但尚未释放 （例如，应用程序域时包含已还原的函数仍在使用） 的函数的 JIT 重新编译的版本。</span><span class="sxs-lookup"><span data-stu-id="8bf13-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bf13-105">语法</span><span class="sxs-lookup"><span data-stu-id="8bf13-105">Syntax</span></span>  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8bf13-106">参数</span><span class="sxs-lookup"><span data-stu-id="8bf13-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="8bf13-107">[in]`FunctionID`的枚举版本的函数实例。</span><span class="sxs-lookup"><span data-stu-id="8bf13-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="8bf13-108">[in]在中分配的 JIT 重新编译的 Id 数`reJitIds`数组。</span><span class="sxs-lookup"><span data-stu-id="8bf13-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="8bf13-109">[out]JIT 重新编译的 Id 的实际数。</span><span class="sxs-lookup"><span data-stu-id="8bf13-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="8bf13-110">[out]调用方分配的数组将包含指定的函数的 JIT 重新编译 Id。</span><span class="sxs-lookup"><span data-stu-id="8bf13-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bf13-111">备注</span><span class="sxs-lookup"><span data-stu-id="8bf13-111">Remarks</span></span>  
 <span data-ttu-id="8bf13-112">`GetReJITIDs`枚举给定的函数实例的活动的 JIT 重新编译 Id。</span><span class="sxs-lookup"><span data-stu-id="8bf13-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="8bf13-113">它遵循相同的使用情况模式与其他`ICorProfilerInfo`接受调用方分配的缓冲区的函数。</span><span class="sxs-lookup"><span data-stu-id="8bf13-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bf13-114">惠?</span><span class="sxs-lookup"><span data-stu-id="8bf13-114">Requirements</span></span>  
 <span data-ttu-id="8bf13-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8bf13-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bf13-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8bf13-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8bf13-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bf13-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bf13-118">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bf13-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bf13-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="8bf13-119">See Also</span></span>  
 [<span data-ttu-id="8bf13-120">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="8bf13-120">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="8bf13-121">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="8bf13-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="8bf13-122">分析</span><span class="sxs-lookup"><span data-stu-id="8bf13-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
