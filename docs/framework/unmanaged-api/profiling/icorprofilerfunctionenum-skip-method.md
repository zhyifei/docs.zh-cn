---
title: ICorProfilerFunctionEnum::Skip 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
- ICorProfilerFunctionEnum::Skip method [.NET Framework profiling]
ms.assetid: 051465b9-e479-494a-804b-c880323b4cbe
topic_type:
- apiref
ms.openlocfilehash: d2a0bff0d3d93ab8542699cffd3d0ecc032246ad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448207"
---
# <a name="icorprofilerfunctionenumskip-method"></a><span data-ttu-id="a8dfa-102">ICorProfilerFunctionEnum::Skip 方法</span><span class="sxs-lookup"><span data-stu-id="a8dfa-102">ICorProfilerFunctionEnum::Skip Method</span></span>
<span data-ttu-id="a8dfa-103">将枚举器的游标从其当前位置前移，以便跳过指定数量的元素。</span><span class="sxs-lookup"><span data-stu-id="a8dfa-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8dfa-104">语法</span><span class="sxs-lookup"><span data-stu-id="a8dfa-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8dfa-105">参数</span><span class="sxs-lookup"><span data-stu-id="a8dfa-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a8dfa-106">[in] The number of elements to be skipped.</span><span class="sxs-lookup"><span data-stu-id="a8dfa-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8dfa-107">返回值</span><span class="sxs-lookup"><span data-stu-id="a8dfa-107">Return Value</span></span>  
 <span data-ttu-id="a8dfa-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="a8dfa-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a8dfa-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a8dfa-109">HRESULT</span></span>|<span data-ttu-id="a8dfa-110">描述</span><span class="sxs-lookup"><span data-stu-id="a8dfa-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a8dfa-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a8dfa-111">S_OK</span></span>|<span data-ttu-id="a8dfa-112">`celt` elements were skipped.</span><span class="sxs-lookup"><span data-stu-id="a8dfa-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="a8dfa-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a8dfa-113">S_FALSE</span></span>|<span data-ttu-id="a8dfa-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span><span class="sxs-lookup"><span data-stu-id="a8dfa-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8dfa-115">备注</span><span class="sxs-lookup"><span data-stu-id="a8dfa-115">Remarks</span></span>  
 <span data-ttu-id="a8dfa-116">The new position of this enumerator's cursor is (current position) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="a8dfa-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8dfa-117">要求</span><span class="sxs-lookup"><span data-stu-id="a8dfa-117">Requirements</span></span>  
 <span data-ttu-id="a8dfa-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a8dfa-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8dfa-119">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a8dfa-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a8dfa-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8dfa-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8dfa-121">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8dfa-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8dfa-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8dfa-122">See also</span></span>

- [<span data-ttu-id="a8dfa-123">ICorProfilerFunctionEnum 接口</span><span class="sxs-lookup"><span data-stu-id="a8dfa-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="a8dfa-124">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="a8dfa-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
