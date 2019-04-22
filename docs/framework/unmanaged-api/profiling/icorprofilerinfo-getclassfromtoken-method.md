---
title: ICorProfilerInfo::GetClassFromToken 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 580c554c968819ba4ef2ba52edeb5e754d33ac1b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59185261"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="0874f-102">ICorProfilerInfo::GetClassFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="0874f-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="0874f-103">获取给定元数据标记的类的 ID。</span><span class="sxs-lookup"><span data-stu-id="0874f-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="0874f-104">此方法是在.NET Framework 2.0 版中已过时。</span><span class="sxs-lookup"><span data-stu-id="0874f-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="0874f-105">使用[ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)相反。</span><span class="sxs-lookup"><span data-stu-id="0874f-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0874f-106">语法</span><span class="sxs-lookup"><span data-stu-id="0874f-106">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0874f-107">参数</span><span class="sxs-lookup"><span data-stu-id="0874f-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="0874f-108">[in]包含的类模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="0874f-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="0874f-109">[in]`mdTypeDef`元数据标记所引用的类。</span><span class="sxs-lookup"><span data-stu-id="0874f-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="0874f-110">[out]指向类 id。</span><span class="sxs-lookup"><span data-stu-id="0874f-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0874f-111">备注</span><span class="sxs-lookup"><span data-stu-id="0874f-111">Remarks</span></span>  
 <span data-ttu-id="0874f-112">此方法已过时;请改用`ICorProfilerInfo2::GetClassFromTokenAndTypeArgs`对于所有类型。</span><span class="sxs-lookup"><span data-stu-id="0874f-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0874f-113">要求</span><span class="sxs-lookup"><span data-stu-id="0874f-113">Requirements</span></span>  
 <span data-ttu-id="0874f-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0874f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0874f-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0874f-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0874f-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0874f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0874f-117">**.NET framework 版本：** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="0874f-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0874f-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="0874f-118">See also</span></span>

- [<span data-ttu-id="0874f-119">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="0874f-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
