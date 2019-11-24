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
ms.openlocfilehash: f6e2cfe47bdd212e39549544b06bf5b11033a956
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429883"
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a><span data-ttu-id="04d52-102">ICorProfilerFunctionControl::SetILFunctionBody 方法</span><span class="sxs-lookup"><span data-stu-id="04d52-102">ICorProfilerFunctionControl::SetILFunctionBody Method</span></span>
<span data-ttu-id="04d52-103">替换方法的公共中间语言 (CIL) 主体。</span><span class="sxs-lookup"><span data-stu-id="04d52-103">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04d52-104">语法</span><span class="sxs-lookup"><span data-stu-id="04d52-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04d52-105">参数</span><span class="sxs-lookup"><span data-stu-id="04d52-105">Parameters</span></span>  
 `cbNewILMethodHeader`  
 <span data-ttu-id="04d52-106">[in] 新 CIL 的总体大小，包括标头和主体之后的任何结构。</span><span class="sxs-lookup"><span data-stu-id="04d52-106">[in] The total size of the new CIL, including the header and any structures that come after the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="04d52-107">[in] 一个指向新 CIL 的标头的指针。</span><span class="sxs-lookup"><span data-stu-id="04d52-107">[in] A pointer to the new CIL header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04d52-108">返回值</span><span class="sxs-lookup"><span data-stu-id="04d52-108">Return Value</span></span>  
 <span data-ttu-id="04d52-109">此方法会返回以下特定的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="04d52-109">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="04d52-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="04d52-110">HRESULT</span></span>|<span data-ttu-id="04d52-111">描述</span><span class="sxs-lookup"><span data-stu-id="04d52-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="04d52-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="04d52-112">S_OK</span></span>|<span data-ttu-id="04d52-113">替换成功。</span><span class="sxs-lookup"><span data-stu-id="04d52-113">The replacement was successful.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04d52-114">备注</span><span class="sxs-lookup"><span data-stu-id="04d52-114">Remarks</span></span>  
 <span data-ttu-id="04d52-115">Unlike the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body.</span><span class="sxs-lookup"><span data-stu-id="04d52-115">Unlike the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body.</span></span> <span data-ttu-id="04d52-116">This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface or allocated within a particular range.</span><span class="sxs-lookup"><span data-stu-id="04d52-116">This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface or allocated within a particular range.</span></span> <span data-ttu-id="04d52-117">它可在任何堆上进行分配。</span><span class="sxs-lookup"><span data-stu-id="04d52-117">It can be allocated on any heap.</span></span> <span data-ttu-id="04d52-118">The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.</span><span class="sxs-lookup"><span data-stu-id="04d52-118">The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04d52-119">要求</span><span class="sxs-lookup"><span data-stu-id="04d52-119">Requirements</span></span>  
 <span data-ttu-id="04d52-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="04d52-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04d52-121">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="04d52-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="04d52-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04d52-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04d52-123">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04d52-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04d52-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="04d52-124">See also</span></span>

- [<span data-ttu-id="04d52-125">ICorProfilerFunctionControl 接口</span><span class="sxs-lookup"><span data-stu-id="04d52-125">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
