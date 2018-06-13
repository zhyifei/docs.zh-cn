---
title: ICorProfilerInfo::GetILFunctionBodyAllocator 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBodyAllocator
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 00a3afab4d5f6151bcd0efd2b658d4cd7fa8f1e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462197"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a><span data-ttu-id="35db4-102">ICorProfilerInfo::GetILFunctionBodyAllocator 方法</span><span class="sxs-lookup"><span data-stu-id="35db4-102">ICorProfilerInfo::GetILFunctionBodyAllocator Method</span></span>
<span data-ttu-id="35db4-103">获取提供的方法来分配内存来用于换出的 Microsoft 中间语言 (MSIL) 代码中的方法体的接口。</span><span class="sxs-lookup"><span data-stu-id="35db4-103">Gets an interface that provides a method to allocate memory to be used for swapping out the body of a method in Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35db4-104">语法</span><span class="sxs-lookup"><span data-stu-id="35db4-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35db4-105">参数</span><span class="sxs-lookup"><span data-stu-id="35db4-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="35db4-106">[in]方法所在的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="35db4-106">[in] The ID of the module in which the method resides.</span></span>  
  
 `ppMalloc`  
 <span data-ttu-id="35db4-107">[out]指向的指针[IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)提供的方法来分配内存的接口。</span><span class="sxs-lookup"><span data-stu-id="35db4-107">[out] A pointer to an [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface that provides a method to allocate the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35db4-108">备注</span><span class="sxs-lookup"><span data-stu-id="35db4-108">Remarks</span></span>  
 <span data-ttu-id="35db4-109">方法体中 MSIL 代码必须位于为相对虚拟地址 (RVA)，相对于加载的模块，这意味着，它遵循中 4 GB 的模块。</span><span class="sxs-lookup"><span data-stu-id="35db4-109">A method body in MSIL code must be located as a relative virtual address (RVA), relative to the loaded module, which means that it follows the module within 4 GB.</span></span> <span data-ttu-id="35db4-110">为了简化工具替换方法的正文`GetILFunctionBodyAllocator`方法可确保该内存分配该范围内。</span><span class="sxs-lookup"><span data-stu-id="35db4-110">To make it easier for a tool to swap out the body of a method, the `GetILFunctionBodyAllocator` method ensures that memory is allocated within that range.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35db4-111">要求</span><span class="sxs-lookup"><span data-stu-id="35db4-111">Requirements</span></span>  
 <span data-ttu-id="35db4-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="35db4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35db4-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="35db4-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="35db4-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35db4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35db4-115">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35db4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35db4-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="35db4-116">See Also</span></span>  
 [<span data-ttu-id="35db4-117">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="35db4-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
