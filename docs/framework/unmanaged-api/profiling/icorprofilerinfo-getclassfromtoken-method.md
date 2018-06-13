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
ms.openlocfilehash: b4b6b7b7b0dbb36724ff5eee2f3f78a3a7422cb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453328"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="c5d38-102">ICorProfilerInfo::GetClassFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="c5d38-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="c5d38-103">获取给定元数据标记的类 ID。</span><span class="sxs-lookup"><span data-stu-id="c5d38-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="c5d38-104">此方法是.NET Framework 2.0 版中过时。</span><span class="sxs-lookup"><span data-stu-id="c5d38-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="c5d38-105">使用[icorprofilerinfo2:: Getclassfromtokenandtypeargs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)相反。</span><span class="sxs-lookup"><span data-stu-id="c5d38-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5d38-106">语法</span><span class="sxs-lookup"><span data-stu-id="c5d38-106">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5d38-107">参数</span><span class="sxs-lookup"><span data-stu-id="c5d38-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="c5d38-108">[in]包含的类模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="c5d38-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="c5d38-109">[in]`mdTypeDef`引用类的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="c5d38-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="c5d38-110">[out]指向类 id。</span><span class="sxs-lookup"><span data-stu-id="c5d38-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5d38-111">备注</span><span class="sxs-lookup"><span data-stu-id="c5d38-111">Remarks</span></span>  
 <span data-ttu-id="c5d38-112">此方法已过时;请改用`ICorProfilerInfo2::GetClassFromTokenAndTypeArgs`对于所有类型。</span><span class="sxs-lookup"><span data-stu-id="c5d38-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5d38-113">要求</span><span class="sxs-lookup"><span data-stu-id="c5d38-113">Requirements</span></span>  
 <span data-ttu-id="c5d38-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c5d38-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5d38-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c5d38-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c5d38-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5d38-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5d38-117">**.NET framework 版本：** 1.0、 1.1</span><span class="sxs-lookup"><span data-stu-id="c5d38-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5d38-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5d38-118">See Also</span></span>  
 [<span data-ttu-id="c5d38-119">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="c5d38-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
