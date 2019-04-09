---
title: ICorProfilerFunctionEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Next Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Next
helpviewer_keywords:
- ICorProfilerFunctionEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 5ed4aa83-ce56-4b9f-9237-5da7587787fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 62e70a2fe421651aac9a4921ca885c53c864c4f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101798"
---
# <a name="icorprofilerfunctionenumnext-method"></a><span data-ttu-id="b2488-102">ICorProfilerFunctionEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="b2488-102">ICorProfilerFunctionEnum::Next Method</span></span>
<span data-ttu-id="b2488-103">从一个函数的顺序集合中获取指定数量的连续函数（从枚举器在序列中的当前位置开始）。</span><span class="sxs-lookup"><span data-stu-id="b2488-103">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2488-104">语法</span><span class="sxs-lookup"><span data-stu-id="b2488-104">Syntax</span></span>  
  
```  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    COR_PRF_FUNCTION ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2488-105">参数</span><span class="sxs-lookup"><span data-stu-id="b2488-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="b2488-106">[in]要检索的函数数量。</span><span class="sxs-lookup"><span data-stu-id="b2488-106">[in] The number of functions to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="b2488-107">[out] `COR_PRF_FUNCTION` 值的数组，其中每个数组表示检索的函数。</span><span class="sxs-lookup"><span data-stu-id="b2488-107">[out] An array of `COR_PRF_FUNCTION` values, each of which represents a retrieved function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b2488-108">[out] 指向 `ids` 数组中实际返回的函数量的指针。</span><span class="sxs-lookup"><span data-stu-id="b2488-108">[out] A pointer to the number of functions actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2488-109">返回值</span><span class="sxs-lookup"><span data-stu-id="b2488-109">Return Value</span></span>  
 <span data-ttu-id="b2488-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="b2488-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b2488-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2488-111">HRESULT</span></span>|<span data-ttu-id="b2488-112">描述</span><span class="sxs-lookup"><span data-stu-id="b2488-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b2488-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2488-113">S_OK</span></span>|`celt` <span data-ttu-id="b2488-114">返回的元素。</span><span class="sxs-lookup"><span data-stu-id="b2488-114">elements were returned.</span></span>|  
|<span data-ttu-id="b2488-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b2488-115">S_FALSE</span></span>|<span data-ttu-id="b2488-116">返回的元素少于 `celt` 个，表示枚举已完成。</span><span class="sxs-lookup"><span data-stu-id="b2488-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2488-117">要求</span><span class="sxs-lookup"><span data-stu-id="b2488-117">Requirements</span></span>  
 <span data-ttu-id="b2488-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b2488-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2488-119">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b2488-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b2488-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2488-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b2488-121">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="b2488-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b2488-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2488-122">See also</span></span>

- [<span data-ttu-id="b2488-123">ICorProfilerFunctionEnum 接口</span><span class="sxs-lookup"><span data-stu-id="b2488-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="b2488-124">分析接口</span><span class="sxs-lookup"><span data-stu-id="b2488-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
