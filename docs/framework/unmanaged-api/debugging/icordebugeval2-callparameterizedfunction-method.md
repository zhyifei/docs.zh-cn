---
title: ICorDebugEval2::CallParameterizedFunction 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CallParameterizedFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cba4eb2b76d7057a5ed66a35342a79615cb8539f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487715"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a><span data-ttu-id="52d4a-102">ICorDebugEval2::CallParameterizedFunction 方法</span><span class="sxs-lookup"><span data-stu-id="52d4a-102">ICorDebugEval2::CallParameterizedFunction Method</span></span>
<span data-ttu-id="52d4a-103">设置了对可以嵌套在其构造函数采用一个类内部指定 ICorDebugFunction<xref:System.Type>参数或可以本身采取<xref:System.Type>参数。</span><span class="sxs-lookup"><span data-stu-id="52d4a-103">Sets up a call to the specified ICorDebugFunction, which can be nested inside a class whose constructor takes <xref:System.Type> parameters, or can itself take <xref:System.Type> parameters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52d4a-104">语法</span><span class="sxs-lookup"><span data-stu-id="52d4a-104">Syntax</span></span>  
  
```  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52d4a-105">参数</span><span class="sxs-lookup"><span data-stu-id="52d4a-105">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="52d4a-106">[in]一个指向`ICorDebugFunction`对象，表示要调用的函数。</span><span class="sxs-lookup"><span data-stu-id="52d4a-106">[in] A pointer to an `ICorDebugFunction` object that represents the function to be called.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="52d4a-107">[in]该函数采用的参数数目。</span><span class="sxs-lookup"><span data-stu-id="52d4a-107">[in] The number of arguments that the function takes.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="52d4a-108">[in]一个指针数组，其中每个指向对象的表示函数的参数。</span><span class="sxs-lookup"><span data-stu-id="52d4a-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a function argument.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="52d4a-109">[in]在函数中传递的值的数目。</span><span class="sxs-lookup"><span data-stu-id="52d4a-109">[in] The number of values passed in the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="52d4a-110">[in]函数参数中传递的指针的数组，其中每个指向 ICorDebugValue 对象表示的值。</span><span class="sxs-lookup"><span data-stu-id="52d4a-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents a value passed in a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52d4a-111">备注</span><span class="sxs-lookup"><span data-stu-id="52d4a-111">Remarks</span></span>  
 <span data-ttu-id="52d4a-112">`CallParameterizedFunction` 就像[icordebugeval:: Callfunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md)只不过该函数可能使用的类型参数的类的内部，可能本身需要和 / 或类型参数。</span><span class="sxs-lookup"><span data-stu-id="52d4a-112">`CallParameterizedFunction` is like [ICorDebugEval::CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) except that the function may be inside a class with type parameters, may itself take type parameters, or both.</span></span> <span data-ttu-id="52d4a-113">对于类，然后为该函数，应首先提供的类型参数。</span><span class="sxs-lookup"><span data-stu-id="52d4a-113">The type arguments should be given first for the class, and then for the function.</span></span>  
  
 <span data-ttu-id="52d4a-114">如果该函数是在不同的应用程序域中，将发生转换。</span><span class="sxs-lookup"><span data-stu-id="52d4a-114">If the function is in a different application domain, a transition will occur.</span></span> <span data-ttu-id="52d4a-115">但是，所有类型和值参数都必须在目标应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="52d4a-115">However, all type and value arguments must be in the target application domain.</span></span>  
  
 <span data-ttu-id="52d4a-116">仅在有限情况下，可以执行函数求值。</span><span class="sxs-lookup"><span data-stu-id="52d4a-116">Function evaluation can be performed only in limited scenarios.</span></span> <span data-ttu-id="52d4a-117">如果`CallParameterizedFunction`或`ICorDebugEval::CallFunction`失败，返回的 HRESULT 会指示失败的最常规的可能原因。</span><span class="sxs-lookup"><span data-stu-id="52d4a-117">If `CallParameterizedFunction` or `ICorDebugEval::CallFunction` fails, the returned HRESULT will indicate the most general possible reason for failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52d4a-118">要求</span><span class="sxs-lookup"><span data-stu-id="52d4a-118">Requirements</span></span>  
 <span data-ttu-id="52d4a-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="52d4a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52d4a-120">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52d4a-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52d4a-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52d4a-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52d4a-122">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52d4a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
