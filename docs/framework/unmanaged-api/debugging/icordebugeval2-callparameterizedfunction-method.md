---
title: "ICorDebugEval2::CallParameterizedFunction 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.CallParameterizedFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 055ded7f3309ff1011d1ca390daf353cba870376
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval2callparameterizedfunction-method"></a><span data-ttu-id="18aa9-102">ICorDebugEval2::CallParameterizedFunction 方法</span><span class="sxs-lookup"><span data-stu-id="18aa9-102">ICorDebugEval2::CallParameterizedFunction Method</span></span>
<span data-ttu-id="18aa9-103">设置指定 ICorDebugFunction，可以嵌套在其构造函数采用类调用<xref:System.Type>参数或可以本身采取<xref:System.Type>参数。</span><span class="sxs-lookup"><span data-stu-id="18aa9-103">Sets up a call to the specified ICorDebugFunction, which can be nested inside a class whose constructor takes <xref:System.Type> parameters, or can itself take <xref:System.Type> parameters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18aa9-104">语法</span><span class="sxs-lookup"><span data-stu-id="18aa9-104">Syntax</span></span>  
  
```  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18aa9-105">参数</span><span class="sxs-lookup"><span data-stu-id="18aa9-105">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="18aa9-106">[in]指向的指针`ICorDebugFunction`表示被调用函数的对象。</span><span class="sxs-lookup"><span data-stu-id="18aa9-106">[in] A pointer to an `ICorDebugFunction` object that represents the function to be called.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="18aa9-107">[in]该函数采用的参数的数目。</span><span class="sxs-lookup"><span data-stu-id="18aa9-107">[in] The number of arguments that the function takes.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="18aa9-108">[in]一个指针数组，其中每个指向对象的表示的函数自变量。</span><span class="sxs-lookup"><span data-stu-id="18aa9-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a function argument.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="18aa9-109">[in]在函数中传递的值的数目。</span><span class="sxs-lookup"><span data-stu-id="18aa9-109">[in] The number of values passed in the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="18aa9-110">[in]函数参数中传递的指针，其中每个指向 ICorDebugValue 对象，表示值的数组。</span><span class="sxs-lookup"><span data-stu-id="18aa9-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents a value passed in a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18aa9-111">备注</span><span class="sxs-lookup"><span data-stu-id="18aa9-111">Remarks</span></span>  
 <span data-ttu-id="18aa9-112">`CallParameterizedFunction`就像[icordebugeval:: Callfunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md)只不过函数可能具有类型参数的类中，可能本身需要和 / 或类型参数。</span><span class="sxs-lookup"><span data-stu-id="18aa9-112">`CallParameterizedFunction` is like [ICorDebugEval::CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) except that the function may be inside a class with type parameters, may itself take type parameters, or both.</span></span> <span data-ttu-id="18aa9-113">对于类，然后为函数，应首先提供的类型自变量。</span><span class="sxs-lookup"><span data-stu-id="18aa9-113">The type arguments should be given first for the class, and then for the function.</span></span>  
  
 <span data-ttu-id="18aa9-114">如果该函数是在不同的应用程序域中，则将发生转换。</span><span class="sxs-lookup"><span data-stu-id="18aa9-114">If the function is in a different application domain, a transition will occur.</span></span> <span data-ttu-id="18aa9-115">但是，所有类型和值的自变量必须都是目标应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="18aa9-115">However, all type and value arguments must be in the target application domain.</span></span>  
  
 <span data-ttu-id="18aa9-116">仅在有限情况下，可以执行函数求值。</span><span class="sxs-lookup"><span data-stu-id="18aa9-116">Function evaluation can be performed only in limited scenarios.</span></span> <span data-ttu-id="18aa9-117">如果`CallParameterizedFunction`或`ICorDebugEval::CallFunction`失败，返回的 HRESULT 将指示失败的最常规的可能原因。</span><span class="sxs-lookup"><span data-stu-id="18aa9-117">If `CallParameterizedFunction` or `ICorDebugEval::CallFunction` fails, the returned HRESULT will indicate the most general possible reason for failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18aa9-118">惠?</span><span class="sxs-lookup"><span data-stu-id="18aa9-118">Requirements</span></span>  
 <span data-ttu-id="18aa9-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="18aa9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18aa9-120">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18aa9-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18aa9-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18aa9-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18aa9-122">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18aa9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
