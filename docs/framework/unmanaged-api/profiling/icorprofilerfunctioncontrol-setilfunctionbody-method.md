---
title: ICorProfilerFunctionControl::SetILFunctionBody 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2d3b01deedd5cd7225c9e54b59ed82a708bad937
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513174"
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a><span data-ttu-id="99ca5-102">ICorProfilerFunctionControl::SetILFunctionBody 方法</span><span class="sxs-lookup"><span data-stu-id="99ca5-102">ICorProfilerFunctionControl::SetILFunctionBody Method</span></span>
<span data-ttu-id="99ca5-103">替换方法的公共中间语言 (CIL) 主体。</span><span class="sxs-lookup"><span data-stu-id="99ca5-103">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99ca5-104">语法</span><span class="sxs-lookup"><span data-stu-id="99ca5-104">Syntax</span></span>  
  
```  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99ca5-105">参数</span><span class="sxs-lookup"><span data-stu-id="99ca5-105">Parameters</span></span>  
 `cbNewILMethodHeader`  
 <span data-ttu-id="99ca5-106">[in] 新 CIL 的总体大小，包括标头和主体之后的任何结构。</span><span class="sxs-lookup"><span data-stu-id="99ca5-106">[in] The total size of the new CIL, including the header and any structures that come after the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="99ca5-107">[in] 一个指向新 CIL 的标头的指针。</span><span class="sxs-lookup"><span data-stu-id="99ca5-107">[in] A pointer to the new CIL header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99ca5-108">返回值</span><span class="sxs-lookup"><span data-stu-id="99ca5-108">Return Value</span></span>  
 <span data-ttu-id="99ca5-109">此方法会返回以下特定的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="99ca5-109">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="99ca5-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="99ca5-110">HRESULT</span></span>|<span data-ttu-id="99ca5-111">描述</span><span class="sxs-lookup"><span data-stu-id="99ca5-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="99ca5-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="99ca5-112">S_OK</span></span>|<span data-ttu-id="99ca5-113">替换成功。</span><span class="sxs-lookup"><span data-stu-id="99ca5-113">The replacement was successful.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99ca5-114">备注</span><span class="sxs-lookup"><span data-stu-id="99ca5-114">Remarks</span></span>  
 <span data-ttu-id="99ca5-115">与不同[icorprofilerinfo:: Setilfunctionbody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)方法，`SetILFunctionBody`方法管理新 CIL 的主体所需的内存。</span><span class="sxs-lookup"><span data-stu-id="99ca5-115">Unlike the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body.</span></span> <span data-ttu-id="99ca5-116">这意味着探查器提供的 CIL 主体不必使用分配[IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)接口或分配特定范围内。</span><span class="sxs-lookup"><span data-stu-id="99ca5-116">This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface or allocated within a particular range.</span></span> <span data-ttu-id="99ca5-117">它可在任何堆上进行分配。</span><span class="sxs-lookup"><span data-stu-id="99ca5-117">It can be allocated on any heap.</span></span> <span data-ttu-id="99ca5-118">探查器可以释放用于其 CIL 主体之后的内存`SetILFunctionBody`返回。</span><span class="sxs-lookup"><span data-stu-id="99ca5-118">The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99ca5-119">要求</span><span class="sxs-lookup"><span data-stu-id="99ca5-119">Requirements</span></span>  
 <span data-ttu-id="99ca5-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="99ca5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99ca5-121">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="99ca5-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="99ca5-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99ca5-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99ca5-123">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99ca5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99ca5-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="99ca5-124">See also</span></span>
- [<span data-ttu-id="99ca5-125">ICorProfilerFunctionControl 接口</span><span class="sxs-lookup"><span data-stu-id="99ca5-125">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
