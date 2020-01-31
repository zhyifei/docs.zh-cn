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
ms.openlocfilehash: 27b3037459ac4f995e37515f6e96c28449c80a4f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862940"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="82a7a-102">ICorProfilerInfo2::EnumModuleFrozenObjects 方法</span><span class="sxs-lookup"><span data-stu-id="82a7a-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="82a7a-103">获取一个枚举器，该枚举数允许对指定模块中的冻结对象进行迭代。此方法已过时。</span><span class="sxs-lookup"><span data-stu-id="82a7a-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82a7a-104">语法</span><span class="sxs-lookup"><span data-stu-id="82a7a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82a7a-105">参数</span><span class="sxs-lookup"><span data-stu-id="82a7a-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="82a7a-106">中包含要枚举的冻结对象的模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="82a7a-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="82a7a-107">弄一个指针，指向用于枚举冻结对象的[ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md)接口的地址。</span><span class="sxs-lookup"><span data-stu-id="82a7a-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82a7a-108">需求</span><span class="sxs-lookup"><span data-stu-id="82a7a-108">Requirements</span></span>  
 <span data-ttu-id="82a7a-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="82a7a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82a7a-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="82a7a-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="82a7a-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82a7a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82a7a-112">**.NET Framework 版本：** 3.5、3.0 SP1、3.0、2.0 SP1、2.0</span><span class="sxs-lookup"><span data-stu-id="82a7a-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a7a-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82a7a-113">See also</span></span>

- [<span data-ttu-id="82a7a-114">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="82a7a-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="82a7a-115">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="82a7a-115">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
