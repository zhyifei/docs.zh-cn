---
title: "ICorProfilerThreadEnum::Next 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerThreadEnum.Next
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerThreadEnum::Next
helpviewer_keywords:
- ICorProfilerThreadEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: f3535279-3c63-41a2-ab0e-a129dc5a01e8
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3295f3dc9af50fb62a2008f59819a51a6032a48b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerthreadenumnext-method"></a><span data-ttu-id="7205d-102">ICorProfilerThreadEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="7205d-102">ICorProfilerThreadEnum::Next Method</span></span>
<span data-ttu-id="7205d-103">从线程的序列集合获取指定的连续线程数，从序列中枚举器的当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="7205d-103">Gets the specified number of contiguous threads from a sequential collection of threads, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7205d-104">语法</span><span class="sxs-lookup"><span data-stu-id="7205d-104">Syntax</span></span>  
  
```  
HRESULT Next (    [in]  ULONG      celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                    ThreadID ids[],  
    [out] ULONG *   pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7205d-105">参数</span><span class="sxs-lookup"><span data-stu-id="7205d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="7205d-106">[in] 要检索的线程数。</span><span class="sxs-lookup"><span data-stu-id="7205d-106">[in] The number of threads to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="7205d-107">[out] `ThreadID` 值的数组，其中每个值表示检索的线程。</span><span class="sxs-lookup"><span data-stu-id="7205d-107">[out] An array of `ThreadID` values, each of which represents a retrieved thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="7205d-108">[out] 指向 `ids` 数组中实际返回的线程数的指针。</span><span class="sxs-lookup"><span data-stu-id="7205d-108">[out] A pointer to the number of threads actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7205d-109">返回值</span><span class="sxs-lookup"><span data-stu-id="7205d-109">Return Value</span></span>  
 <span data-ttu-id="7205d-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="7205d-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7205d-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7205d-111">HRESULT</span></span>|<span data-ttu-id="7205d-112">描述</span><span class="sxs-lookup"><span data-stu-id="7205d-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7205d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="7205d-113">S_OK</span></span>|<span data-ttu-id="7205d-114">已返回 `celt` 元素。</span><span class="sxs-lookup"><span data-stu-id="7205d-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="7205d-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="7205d-115">S_FALSE</span></span>|<span data-ttu-id="7205d-116">返回的元素少于 `celt` 个，表示枚举已完成。</span><span class="sxs-lookup"><span data-stu-id="7205d-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7205d-117">要求</span><span class="sxs-lookup"><span data-stu-id="7205d-117">Requirements</span></span>  
 <span data-ttu-id="7205d-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7205d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7205d-119">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7205d-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7205d-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7205d-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7205d-121">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7205d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7205d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7205d-122">See Also</span></span>  
 [<span data-ttu-id="7205d-123">ICorProfilerThreadEnum 接口</span><span class="sxs-lookup"><span data-stu-id="7205d-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="7205d-124">分析接口</span><span class="sxs-lookup"><span data-stu-id="7205d-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
