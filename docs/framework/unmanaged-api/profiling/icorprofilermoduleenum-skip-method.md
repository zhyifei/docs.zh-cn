---
title: ICorProfilerModuleEnum::Skip 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Skip method [.NET Framework profiling]
ms.assetid: 8dc29c6a-e2ba-41d8-a1e0-0fdd21421e0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 397e8afcc176bcd9733e83dc6425fe49f385931e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078197"
---
# <a name="icorprofilermoduleenumskip-method"></a><span data-ttu-id="782f6-102">ICorProfilerModuleEnum::Skip 方法</span><span class="sxs-lookup"><span data-stu-id="782f6-102">ICorProfilerModuleEnum::Skip Method</span></span>
<span data-ttu-id="782f6-103">将枚举器的游标从其当前位置前移，以便跳过指定数量的元素。</span><span class="sxs-lookup"><span data-stu-id="782f6-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="782f6-104">语法</span><span class="sxs-lookup"><span data-stu-id="782f6-104">Syntax</span></span>  
  
```  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="782f6-105">参数</span><span class="sxs-lookup"><span data-stu-id="782f6-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="782f6-106">[in]要跳过的元素数。</span><span class="sxs-lookup"><span data-stu-id="782f6-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="782f6-107">返回值</span><span class="sxs-lookup"><span data-stu-id="782f6-107">Return Value</span></span>  
 <span data-ttu-id="782f6-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="782f6-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="782f6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="782f6-109">HRESULT</span></span>|<span data-ttu-id="782f6-110">描述</span><span class="sxs-lookup"><span data-stu-id="782f6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="782f6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="782f6-111">S_OK</span></span>|<span data-ttu-id="782f6-112">`celt` 跳过的元素。</span><span class="sxs-lookup"><span data-stu-id="782f6-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="782f6-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="782f6-113">S_FALSE</span></span>|<span data-ttu-id="782f6-114">少于`celt`跳过的元素，指示没有更多元素。</span><span class="sxs-lookup"><span data-stu-id="782f6-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="782f6-115">备注</span><span class="sxs-lookup"><span data-stu-id="782f6-115">Remarks</span></span>  
 <span data-ttu-id="782f6-116">此枚举器的光标的新位置是 （当前的位置） + `celt`。</span><span class="sxs-lookup"><span data-stu-id="782f6-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="782f6-117">要求</span><span class="sxs-lookup"><span data-stu-id="782f6-117">Requirements</span></span>  
 <span data-ttu-id="782f6-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="782f6-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="782f6-119">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="782f6-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="782f6-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="782f6-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="782f6-121">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="782f6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="782f6-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="782f6-122">See also</span></span>

- [<span data-ttu-id="782f6-123">ICorProfilerModuleEnum 接口</span><span class="sxs-lookup"><span data-stu-id="782f6-123">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="782f6-124">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="782f6-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
