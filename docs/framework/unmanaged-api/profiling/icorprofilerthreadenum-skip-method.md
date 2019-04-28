---
title: ICorProfilerThreadEnum::Skip 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Skip method [.NET Framework profiling]
ms.assetid: acb8b029-4a96-4ed7-ae3c-310204e5ceea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cce96e8c6d046beba9e45c7121bf68444fd51c95
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597950"
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="c8cd1-102">ICorProfilerThreadEnum::Skip 方法</span><span class="sxs-lookup"><span data-stu-id="c8cd1-102">ICorProfilerThreadEnum::Skip Method</span></span>
<span data-ttu-id="c8cd1-103">从当前位置前移枚举器的光标，以便跳过指定的元素数量。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8cd1-104">语法</span><span class="sxs-lookup"><span data-stu-id="c8cd1-104">Syntax</span></span>  
  
```  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8cd1-105">参数</span><span class="sxs-lookup"><span data-stu-id="c8cd1-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c8cd1-106">[in]要跳过的元素数。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8cd1-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c8cd1-107">Return Value</span></span>  
 <span data-ttu-id="c8cd1-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c8cd1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c8cd1-109">HRESULT</span></span>|<span data-ttu-id="c8cd1-110">描述</span><span class="sxs-lookup"><span data-stu-id="c8cd1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c8cd1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c8cd1-111">S_OK</span></span>|<span data-ttu-id="c8cd1-112">`celt` 跳过的元素。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="c8cd1-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c8cd1-113">S_FALSE</span></span>|<span data-ttu-id="c8cd1-114">少于`celt`跳过的元素，指示没有更多元素。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8cd1-115">备注</span><span class="sxs-lookup"><span data-stu-id="c8cd1-115">Remarks</span></span>  
 <span data-ttu-id="c8cd1-116">此枚举器的光标的新位置是 （当前的位置） + `celt`。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8cd1-117">要求</span><span class="sxs-lookup"><span data-stu-id="c8cd1-117">Requirements</span></span>  
 <span data-ttu-id="c8cd1-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c8cd1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8cd1-119">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c8cd1-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c8cd1-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8cd1-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8cd1-121">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8cd1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8cd1-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8cd1-122">See also</span></span>

- [<span data-ttu-id="c8cd1-123">ICorProfilerThreadEnum 接口</span><span class="sxs-lookup"><span data-stu-id="c8cd1-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="c8cd1-124">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="c8cd1-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
