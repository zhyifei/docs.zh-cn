---
title: "ICorProfilerInfo::GetILFunctionBodyAllocator 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetILFunctionBodyAllocator
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1feec20f0ddc4f6029490e06d4729b3fdaa7fa8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a><span data-ttu-id="5e43d-102">ICorProfilerInfo::GetILFunctionBodyAllocator 方法</span><span class="sxs-lookup"><span data-stu-id="5e43d-102">ICorProfilerInfo::GetILFunctionBodyAllocator Method</span></span>
<span data-ttu-id="5e43d-103">获取提供的方法来分配内存来用于换出的 Microsoft 中间语言 (MSIL) 代码中的方法体的接口。</span><span class="sxs-lookup"><span data-stu-id="5e43d-103">Gets an interface that provides a method to allocate memory to be used for swapping out the body of a method in Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e43d-104">语法</span><span class="sxs-lookup"><span data-stu-id="5e43d-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5e43d-105">参数</span><span class="sxs-lookup"><span data-stu-id="5e43d-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="5e43d-106">[in]方法所在的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="5e43d-106">[in] The ID of the module in which the method resides.</span></span>  
  
 `ppMalloc`  
 <span data-ttu-id="5e43d-107">[out]指向的指针[IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)提供的方法来分配内存的接口。</span><span class="sxs-lookup"><span data-stu-id="5e43d-107">[out] A pointer to an [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface that provides a method to allocate the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e43d-108">备注</span><span class="sxs-lookup"><span data-stu-id="5e43d-108">Remarks</span></span>  
 <span data-ttu-id="5e43d-109">方法体中 MSIL 代码必须位于为相对虚拟地址 (RVA)，相对于加载的模块，这意味着，它遵循中 4 GB 的模块。</span><span class="sxs-lookup"><span data-stu-id="5e43d-109">A method body in MSIL code must be located as a relative virtual address (RVA), relative to the loaded module, which means that it follows the module within 4 GB.</span></span> <span data-ttu-id="5e43d-110">为了简化工具替换方法的正文`GetILFunctionBodyAllocator`方法可确保该内存分配该范围内。</span><span class="sxs-lookup"><span data-stu-id="5e43d-110">To make it easier for a tool to swap out the body of a method, the `GetILFunctionBodyAllocator` method ensures that memory is allocated within that range.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e43d-111">惠?</span><span class="sxs-lookup"><span data-stu-id="5e43d-111">Requirements</span></span>  
 <span data-ttu-id="5e43d-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5e43d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e43d-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5e43d-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5e43d-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e43d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e43d-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e43d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e43d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e43d-116">See Also</span></span>  
 [<span data-ttu-id="5e43d-117">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="5e43d-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
