---
title: ICorProfilerInfo2::EnumModuleFrozenObjects 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.EnumModuleFrozenObjects
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::EnumModuleFrozenObjects
helpviewer_keywords:
- EnumModuleFrozenObjects method [.NET Framework profiling]
- ICorProfilerInfo2::EnumModuleFrozenObjects method [.NET Framework profiling]
ms.assetid: 920b6483-7064-4d64-8613-fcc38ccf9b1e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a325c3e1aa9c08e00dc2cc38e3f7833fa9f99897
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472572"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="6f2c8-102">ICorProfilerInfo2::EnumModuleFrozenObjects 方法</span><span class="sxs-lookup"><span data-stu-id="6f2c8-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="6f2c8-103">获取指定模块中的冻结对象允许迭代的枚举器。此方法已过时。</span><span class="sxs-lookup"><span data-stu-id="6f2c8-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f2c8-104">语法</span><span class="sxs-lookup"><span data-stu-id="6f2c8-104">Syntax</span></span>  
  
```  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f2c8-105">参数</span><span class="sxs-lookup"><span data-stu-id="6f2c8-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="6f2c8-106">[in]包含要枚举的冻结的对象的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="6f2c8-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="6f2c8-107">[out]指向的地址的指针[ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)接口，该枚举的冻结的对象接口。</span><span class="sxs-lookup"><span data-stu-id="6f2c8-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f2c8-108">要求</span><span class="sxs-lookup"><span data-stu-id="6f2c8-108">Requirements</span></span>  
 <span data-ttu-id="6f2c8-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6f2c8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f2c8-110">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6f2c8-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6f2c8-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f2c8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f2c8-112">**.NET framework 版本：** 3.5、 3.0 SP1，3.0，2.0 SP1，2.0</span><span class="sxs-lookup"><span data-stu-id="6f2c8-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f2c8-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f2c8-113">See also</span></span>
- [<span data-ttu-id="6f2c8-114">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="6f2c8-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="6f2c8-115">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="6f2c8-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
