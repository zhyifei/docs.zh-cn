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
ms.openlocfilehash: 12524de994264d83abf5b5338654e89a0964adff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667695"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="98702-102">ICorProfilerInfo::GetClassFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="98702-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="98702-103">获取给定元数据标记的类的 ID。</span><span class="sxs-lookup"><span data-stu-id="98702-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="98702-104">此方法是在.NET Framework 2.0 版中已过时。</span><span class="sxs-lookup"><span data-stu-id="98702-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="98702-105">使用[ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)相反。</span><span class="sxs-lookup"><span data-stu-id="98702-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98702-106">语法</span><span class="sxs-lookup"><span data-stu-id="98702-106">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="98702-107">参数</span><span class="sxs-lookup"><span data-stu-id="98702-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="98702-108">[in]包含的类模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="98702-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="98702-109">[in]`mdTypeDef`元数据标记所引用的类。</span><span class="sxs-lookup"><span data-stu-id="98702-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="98702-110">[out]指向类 id。</span><span class="sxs-lookup"><span data-stu-id="98702-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98702-111">备注</span><span class="sxs-lookup"><span data-stu-id="98702-111">Remarks</span></span>  
 <span data-ttu-id="98702-112">此方法已过时;请改用`ICorProfilerInfo2::GetClassFromTokenAndTypeArgs`对于所有类型。</span><span class="sxs-lookup"><span data-stu-id="98702-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98702-113">要求</span><span class="sxs-lookup"><span data-stu-id="98702-113">Requirements</span></span>  
 <span data-ttu-id="98702-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="98702-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98702-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="98702-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="98702-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98702-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98702-117">**.NET framework 版本：** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="98702-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98702-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="98702-118">See also</span></span>
- [<span data-ttu-id="98702-119">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="98702-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
