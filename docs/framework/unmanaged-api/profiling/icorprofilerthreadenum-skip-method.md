---
title: "ICorProfilerThreadEnum::Skip 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerThreadEnum.Skip
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerThreadEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Skip method [.NET Framework profiling]
ms.assetid: acb8b029-4a96-4ed7-ae3c-310204e5ceea
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f492a455165f3b49994beb3220334e2932bf214c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="3e467-102">ICorProfilerThreadEnum::Skip 方法</span><span class="sxs-lookup"><span data-stu-id="3e467-102">ICorProfilerThreadEnum::Skip Method</span></span>
<span data-ttu-id="3e467-103">从当前位置前移枚举器的光标，以便跳过指定的元素数量。</span><span class="sxs-lookup"><span data-stu-id="3e467-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e467-104">语法</span><span class="sxs-lookup"><span data-stu-id="3e467-104">Syntax</span></span>  
  
```  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3e467-105">参数</span><span class="sxs-lookup"><span data-stu-id="3e467-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="3e467-106">[in]要跳过的元素数。</span><span class="sxs-lookup"><span data-stu-id="3e467-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e467-107">返回值</span><span class="sxs-lookup"><span data-stu-id="3e467-107">Return Value</span></span>  
 <span data-ttu-id="3e467-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="3e467-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3e467-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3e467-109">HRESULT</span></span>|<span data-ttu-id="3e467-110">描述</span><span class="sxs-lookup"><span data-stu-id="3e467-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3e467-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3e467-111">S_OK</span></span>|<span data-ttu-id="3e467-112">`celt`跳过的元素。</span><span class="sxs-lookup"><span data-stu-id="3e467-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="3e467-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3e467-113">S_FALSE</span></span>|<span data-ttu-id="3e467-114">少于`celt`跳过的元素，它指示是没有更多的元素。</span><span class="sxs-lookup"><span data-stu-id="3e467-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e467-115">备注</span><span class="sxs-lookup"><span data-stu-id="3e467-115">Remarks</span></span>  
 <span data-ttu-id="3e467-116">此枚举器的光标的新位置是 （当前位置） + `celt`。</span><span class="sxs-lookup"><span data-stu-id="3e467-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e467-117">要求</span><span class="sxs-lookup"><span data-stu-id="3e467-117">Requirements</span></span>  
 <span data-ttu-id="3e467-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3e467-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e467-119">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3e467-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3e467-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e467-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e467-121">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e467-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e467-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e467-122">See Also</span></span>  
 [<span data-ttu-id="3e467-123">ICorProfilerThreadEnum 接口</span><span class="sxs-lookup"><span data-stu-id="3e467-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="3e467-124">分析接口</span><span class="sxs-lookup"><span data-stu-id="3e467-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
