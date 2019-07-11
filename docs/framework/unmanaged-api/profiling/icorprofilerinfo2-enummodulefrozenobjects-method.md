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
ms.openlocfilehash: 3e044a9dedf96025981c1a77471c6abedfc26420
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762383"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="68952-102">ICorProfilerInfo2::EnumModuleFrozenObjects 方法</span><span class="sxs-lookup"><span data-stu-id="68952-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="68952-103">获取指定模块中的冻结对象允许迭代的枚举器。此方法已过时。</span><span class="sxs-lookup"><span data-stu-id="68952-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68952-104">语法</span><span class="sxs-lookup"><span data-stu-id="68952-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68952-105">参数</span><span class="sxs-lookup"><span data-stu-id="68952-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="68952-106">[in]包含要枚举的冻结的对象的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="68952-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="68952-107">[out]指向的地址的指针[ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)接口，该枚举的冻结的对象接口。</span><span class="sxs-lookup"><span data-stu-id="68952-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68952-108">要求</span><span class="sxs-lookup"><span data-stu-id="68952-108">Requirements</span></span>  
 <span data-ttu-id="68952-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="68952-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68952-110">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="68952-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="68952-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68952-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68952-112">**.NET framework 版本：** 3.5、 3.0 SP1，3.0，2.0 SP1，2.0</span><span class="sxs-lookup"><span data-stu-id="68952-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68952-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="68952-113">See also</span></span>

- [<span data-ttu-id="68952-114">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="68952-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="68952-115">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="68952-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
