---
title: "ICorProfilerInfo::GetFunctionFromToken 方法"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0c90a63f075c392ca3ff02a47190f9c4dfe6aad5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="02177-102">ICorProfilerInfo::GetFunctionFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="02177-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="02177-103">获取函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="02177-103">Gets the ID of a function.</span></span> <span data-ttu-id="02177-104">此方法是.NET Framework 2.0 版中过时。</span><span class="sxs-lookup"><span data-stu-id="02177-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="02177-105">使用[icorprofilerinfo2:: Getfunctionfromtokenandtypeargs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="02177-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02177-106">语法</span><span class="sxs-lookup"><span data-stu-id="02177-106">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="02177-107">备注</span><span class="sxs-lookup"><span data-stu-id="02177-107">Remarks</span></span>  
 <span data-ttu-id="02177-108">`GetFunctionFromToken`方法将不能用于泛型函数或泛型类型中的函数; 现已过时。</span><span class="sxs-lookup"><span data-stu-id="02177-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="02177-109">使用`ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs`以外的所有函数。</span><span class="sxs-lookup"><span data-stu-id="02177-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02177-110">惠?</span><span class="sxs-lookup"><span data-stu-id="02177-110">Requirements</span></span>  
 <span data-ttu-id="02177-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="02177-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02177-112">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="02177-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="02177-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02177-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02177-114">**.NET framework 版本：** 1.1、 1.0</span><span class="sxs-lookup"><span data-stu-id="02177-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02177-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="02177-115">See Also</span></span>  
 [<span data-ttu-id="02177-116">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="02177-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
