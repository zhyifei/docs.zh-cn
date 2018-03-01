---
title: "ICorProfilerInfo::SetILFunctionBody 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c44fa89ba66a306792f1ffed162447a6305a0347
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a><span data-ttu-id="1c766-102">ICorProfilerInfo::SetILFunctionBody 方法</span><span class="sxs-lookup"><span data-stu-id="1c766-102">ICorProfilerInfo::SetILFunctionBody Method</span></span>
<span data-ttu-id="1c766-103">替换指定模块中指定的函数的主体。</span><span class="sxs-lookup"><span data-stu-id="1c766-103">Replaces the body of the specified function in the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c766-104">语法</span><span class="sxs-lookup"><span data-stu-id="1c766-104">Syntax</span></span>  
  
```  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c766-105">参数</span><span class="sxs-lookup"><span data-stu-id="1c766-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="1c766-106">[in]函数所在模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="1c766-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodid`  
 <span data-ttu-id="1c766-107">[in]若要替换主体的函数的标记。</span><span class="sxs-lookup"><span data-stu-id="1c766-107">[in] The token of the function for which to replace the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="1c766-108">[in]新的标头的函数。</span><span class="sxs-lookup"><span data-stu-id="1c766-108">[in] The new header for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c766-109">备注</span><span class="sxs-lookup"><span data-stu-id="1c766-109">Remarks</span></span>  
 <span data-ttu-id="1c766-110">`SetILFunctionBody`方法，使其指向新的函数体中，并调整任何所需的内部数据结构，则会在元数据函数的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="1c766-110">The `SetILFunctionBody` method replaces the relative virtual address of the function in the metadata so that it points to the new function body, and adjusts any internal data structures as required.</span></span>  
  
 <span data-ttu-id="1c766-111">`SetILFunctionBody`可以对那些永远不会由实时 (JIT) 编译器编译的函数调用方法。</span><span class="sxs-lookup"><span data-stu-id="1c766-111">The `SetILFunctionBody` method can be called on only those functions that have never been compiled by a just-in-time (JIT) compiler.</span></span>  
  
 <span data-ttu-id="1c766-112">使用[icorprofilerinfo:: Getilfunctionbodyallocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)方法，以分配新的方法，以确保缓冲区是兼容的空间。</span><span class="sxs-lookup"><span data-stu-id="1c766-112">Use the [ICorProfilerInfo::GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) method to allocate space for the new method to ensure that the buffer is compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c766-113">惠?</span><span class="sxs-lookup"><span data-stu-id="1c766-113">Requirements</span></span>  
 <span data-ttu-id="1c766-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1c766-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c766-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1c766-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1c766-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c766-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c766-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c766-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c766-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c766-118">See Also</span></span>  
 [<span data-ttu-id="1c766-119">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="1c766-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
