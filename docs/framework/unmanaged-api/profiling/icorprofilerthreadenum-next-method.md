---
title: ICorProfilerThreadEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Next
helpviewer_keywords:
- ICorProfilerThreadEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: f3535279-3c63-41a2-ab0e-a129dc5a01e8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 25a6baea0cdd92d6d214ab8a697b0c00c44c42bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664572"
---
# <a name="icorprofilerthreadenumnext-method"></a><span data-ttu-id="6d9d4-102">ICorProfilerThreadEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="6d9d4-102">ICorProfilerThreadEnum::Next Method</span></span>
<span data-ttu-id="6d9d4-103">从线程的序列集合获取指定的连续线程数，从序列中枚举器的当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="6d9d4-103">Gets the specified number of contiguous threads from a sequential collection of threads, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d9d4-104">语法</span><span class="sxs-lookup"><span data-stu-id="6d9d4-104">Syntax</span></span>  
  
```  
HRESULT Next (    [in]  ULONG      celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                    ThreadID ids[],  
    [out] ULONG *   pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d9d4-105">参数</span><span class="sxs-lookup"><span data-stu-id="6d9d4-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="6d9d4-106">[in] 要检索的线程数。</span><span class="sxs-lookup"><span data-stu-id="6d9d4-106">[in] The number of threads to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="6d9d4-107">[out] `ThreadID` 值的数组，其中每个值表示检索的线程。</span><span class="sxs-lookup"><span data-stu-id="6d9d4-107">[out] An array of `ThreadID` values, each of which represents a retrieved thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="6d9d4-108">[out] 指向 `ids` 数组中实际返回的线程数的指针。</span><span class="sxs-lookup"><span data-stu-id="6d9d4-108">[out] A pointer to the number of threads actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d9d4-109">返回值</span><span class="sxs-lookup"><span data-stu-id="6d9d4-109">Return Value</span></span>  
 <span data-ttu-id="6d9d4-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="6d9d4-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6d9d4-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6d9d4-111">HRESULT</span></span>|<span data-ttu-id="6d9d4-112">描述</span><span class="sxs-lookup"><span data-stu-id="6d9d4-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6d9d4-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="6d9d4-113">S_OK</span></span>|<span data-ttu-id="6d9d4-114">已返回 `celt` 元素。</span><span class="sxs-lookup"><span data-stu-id="6d9d4-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="6d9d4-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="6d9d4-115">S_FALSE</span></span>|<span data-ttu-id="6d9d4-116">返回的元素少于 `celt` 个，表示枚举已完成。</span><span class="sxs-lookup"><span data-stu-id="6d9d4-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6d9d4-117">要求</span><span class="sxs-lookup"><span data-stu-id="6d9d4-117">Requirements</span></span>  
 <span data-ttu-id="6d9d4-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6d9d4-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d9d4-119">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6d9d4-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6d9d4-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d9d4-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d9d4-121">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d9d4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d9d4-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d9d4-122">See also</span></span>
- [<span data-ttu-id="6d9d4-123">ICorProfilerThreadEnum 接口</span><span class="sxs-lookup"><span data-stu-id="6d9d4-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="6d9d4-124">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="6d9d4-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
