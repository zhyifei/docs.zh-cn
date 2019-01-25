---
title: ICorProfilerInfo::GetFunctionFromToken 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionFromToken method [.NET Framework profiling]
- GetFunctionFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0eed759f-cce8-405d-88dc-9ee293a38928
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 12f76059387f00316888cbe6d839bece33e3eef9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520255"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="67104-102">ICorProfilerInfo::GetFunctionFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="67104-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="67104-103">获取函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="67104-103">Gets the ID of a function.</span></span> <span data-ttu-id="67104-104">此方法是在.NET Framework 2.0 版中已过时。</span><span class="sxs-lookup"><span data-stu-id="67104-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="67104-105">使用[ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="67104-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67104-106">语法</span><span class="sxs-lookup"><span data-stu-id="67104-106">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="67104-107">备注</span><span class="sxs-lookup"><span data-stu-id="67104-107">Remarks</span></span>  
 <span data-ttu-id="67104-108">`GetFunctionFromToken`方法不适用于泛型函数或泛型类型中的函数; 现已过时。</span><span class="sxs-lookup"><span data-stu-id="67104-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="67104-109">使用`ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs`之外的所有函数。</span><span class="sxs-lookup"><span data-stu-id="67104-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67104-110">要求</span><span class="sxs-lookup"><span data-stu-id="67104-110">Requirements</span></span>  
 <span data-ttu-id="67104-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="67104-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67104-112">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="67104-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="67104-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67104-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67104-114">**.NET framework 版本：** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="67104-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67104-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="67104-115">See also</span></span>
- [<span data-ttu-id="67104-116">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="67104-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
