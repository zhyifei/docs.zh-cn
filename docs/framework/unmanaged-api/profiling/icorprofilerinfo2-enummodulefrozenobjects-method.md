---
title: "ICorProfilerInfo2::EnumModuleFrozenObjects 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.EnumModuleFrozenObjects
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::EnumModuleFrozenObjects
helpviewer_keywords:
- EnumModuleFrozenObjects method [.NET Framework profiling]
- ICorProfilerInfo2::EnumModuleFrozenObjects method [.NET Framework profiling]
ms.assetid: 920b6483-7064-4d64-8613-fcc38ccf9b1e
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3866d91d28258eaee78e6025175628796a369f88
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="a9d1c-102">ICorProfilerInfo2::EnumModuleFrozenObjects 方法</span><span class="sxs-lookup"><span data-stu-id="a9d1c-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="a9d1c-103">获取允许迭代通过指定模块中的已冻结对象的枚举器。此方法已过时。</span><span class="sxs-lookup"><span data-stu-id="a9d1c-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9d1c-104">语法</span><span class="sxs-lookup"><span data-stu-id="a9d1c-104">Syntax</span></span>  
  
```  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9d1c-105">参数</span><span class="sxs-lookup"><span data-stu-id="a9d1c-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="a9d1c-106">[in]包含要枚举的冻结的对象模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="a9d1c-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="a9d1c-107">[out]指向的地址的指针[ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)接口，该枚举的冻结的对象接口。</span><span class="sxs-lookup"><span data-stu-id="a9d1c-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9d1c-108">惠?</span><span class="sxs-lookup"><span data-stu-id="a9d1c-108">Requirements</span></span>  
 <span data-ttu-id="a9d1c-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a9d1c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9d1c-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a9d1c-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a9d1c-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9d1c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9d1c-112">**.NET framework 版本：** 3.5、 3.0 SP1、 3.0、 2.0 SP1、 2.0</span><span class="sxs-lookup"><span data-stu-id="a9d1c-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9d1c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9d1c-113">See Also</span></span>  
 [<span data-ttu-id="a9d1c-114">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="a9d1c-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="a9d1c-115">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="a9d1c-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
