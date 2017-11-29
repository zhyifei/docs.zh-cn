---
title: "ICorDebugEval::CallFunction 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.CallFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 72713d81931b53e8d61fb39cee146fd30a59bfcc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="a8f56-102">ICorDebugEval::CallFunction 方法</span><span class="sxs-lookup"><span data-stu-id="a8f56-102">ICorDebugEval::CallFunction Method</span></span>
<span data-ttu-id="a8f56-103">设置了对指定函数的调用。</span><span class="sxs-lookup"><span data-stu-id="a8f56-103">Sets up a call to the specified function.</span></span>  
  
 <span data-ttu-id="a8f56-104">此方法是.NET Framework 2.0 版中过时。</span><span class="sxs-lookup"><span data-stu-id="a8f56-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="a8f56-105">使用[icordebugeval2:: Callparameterizedfunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)相反。</span><span class="sxs-lookup"><span data-stu-id="a8f56-105">Use [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8f56-106">语法</span><span class="sxs-lookup"><span data-stu-id="a8f56-106">Syntax</span></span>  
  
```  
HRESULT CallFunction (  
    [in] ICorDebugFunction  *pFunction,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8f56-107">参数</span><span class="sxs-lookup"><span data-stu-id="a8f56-107">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="a8f56-108">[in]指向 ICorDebugFunction 对象指定要调用的函数的指针。</span><span class="sxs-lookup"><span data-stu-id="a8f56-108">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="a8f56-109">[in]函数的参数的数目。</span><span class="sxs-lookup"><span data-stu-id="a8f56-109">[in] The number of arguments for the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="a8f56-110">[in]一个指针数组，其中每个指向 ICorDebugValue 对象，它指定要传递给函数的参数。</span><span class="sxs-lookup"><span data-stu-id="a8f56-110">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8f56-111">备注</span><span class="sxs-lookup"><span data-stu-id="a8f56-111">Remarks</span></span>  
 <span data-ttu-id="a8f56-112">如果该函数是虚拟的`CallFunction`将执行虚拟调度。</span><span class="sxs-lookup"><span data-stu-id="a8f56-112">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="a8f56-113">如果函数是在不同的应用程序域中，转换将发生，只要所有参数也都是该应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="a8f56-113">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8f56-114">要求</span><span class="sxs-lookup"><span data-stu-id="a8f56-114">Requirements</span></span>  
 <span data-ttu-id="a8f56-115">**平台：** WindowSee[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a8f56-115">**Platforms:** WindowSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8f56-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8f56-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8f56-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8f56-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8f56-118">**.NET framework 版本：** 1.1、 1.0</span><span class="sxs-lookup"><span data-stu-id="a8f56-118">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8f56-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8f56-119">See Also</span></span>  
 [<span data-ttu-id="a8f56-120">CallParameterizedFunction 方法</span><span class="sxs-lookup"><span data-stu-id="a8f56-120">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)
