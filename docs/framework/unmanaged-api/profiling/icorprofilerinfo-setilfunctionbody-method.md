---
title: ICorProfilerInfo::SetILFunctionBody 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ff79f6e439f2bafd598d9d416cc6f7404f4c231d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547327"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a><span data-ttu-id="e3eda-102">ICorProfilerInfo::SetILFunctionBody 方法</span><span class="sxs-lookup"><span data-stu-id="e3eda-102">ICorProfilerInfo::SetILFunctionBody Method</span></span>
<span data-ttu-id="e3eda-103">替换指定的模块中的指定函数的正文。</span><span class="sxs-lookup"><span data-stu-id="e3eda-103">Replaces the body of the specified function in the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3eda-104">语法</span><span class="sxs-lookup"><span data-stu-id="e3eda-104">Syntax</span></span>  
  
```  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e3eda-105">参数</span><span class="sxs-lookup"><span data-stu-id="e3eda-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="e3eda-106">[in]该函数所在的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="e3eda-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodid`  
 <span data-ttu-id="e3eda-107">[in]要为其主体替换为函数的标记。</span><span class="sxs-lookup"><span data-stu-id="e3eda-107">[in] The token of the function for which to replace the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="e3eda-108">[in]函数的新标头。</span><span class="sxs-lookup"><span data-stu-id="e3eda-108">[in] The new header for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3eda-109">备注</span><span class="sxs-lookup"><span data-stu-id="e3eda-109">Remarks</span></span>  
 <span data-ttu-id="e3eda-110">`SetILFunctionBody`方法替换元数据中的函数的相对虚拟地址，使其指向新的函数体，并调整任何所需的内部数据结构。</span><span class="sxs-lookup"><span data-stu-id="e3eda-110">The `SetILFunctionBody` method replaces the relative virtual address of the function in the metadata so that it points to the new function body, and adjusts any internal data structures as required.</span></span>  
  
 <span data-ttu-id="e3eda-111">`SetILFunctionBody`永远不会由实时 (JIT) 编译器编译这些函数可以调用方法。</span><span class="sxs-lookup"><span data-stu-id="e3eda-111">The `SetILFunctionBody` method can be called on only those functions that have never been compiled by a just-in-time (JIT) compiler.</span></span>  
  
 <span data-ttu-id="e3eda-112">使用[icorprofilerinfo:: Getilfunctionbodyallocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)方法，以分配新的方法，以确保缓冲区是兼容的空间。</span><span class="sxs-lookup"><span data-stu-id="e3eda-112">Use the [ICorProfilerInfo::GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) method to allocate space for the new method to ensure that the buffer is compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3eda-113">要求</span><span class="sxs-lookup"><span data-stu-id="e3eda-113">Requirements</span></span>  
 <span data-ttu-id="e3eda-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e3eda-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3eda-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e3eda-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e3eda-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3eda-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3eda-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3eda-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3eda-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3eda-118">See also</span></span>
- [<span data-ttu-id="e3eda-119">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="e3eda-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
