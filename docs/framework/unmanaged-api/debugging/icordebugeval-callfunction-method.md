---
title: ICorDebugEval::CallFunction 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66e51dc15f7d44ede26634571fa04c58e9735694
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364146"
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="2da0e-102">ICorDebugEval::CallFunction 方法</span><span class="sxs-lookup"><span data-stu-id="2da0e-102">ICorDebugEval::CallFunction Method</span></span>

<span data-ttu-id="2da0e-103">设置了对指定函数的调用。</span><span class="sxs-lookup"><span data-stu-id="2da0e-103">Sets up a call to the specified function.</span></span>

<span data-ttu-id="2da0e-104">此方法是在.NET Framework 2.0 版中已过时。</span><span class="sxs-lookup"><span data-stu-id="2da0e-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="2da0e-105">使用[ICorDebugEval2::CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md)相反。</span><span class="sxs-lookup"><span data-stu-id="2da0e-105">Use [ICorDebugEval2::CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="2da0e-106">语法</span><span class="sxs-lookup"><span data-stu-id="2da0e-106">Syntax</span></span>

```cpp
HRESULT CallFunction (
    [in] ICorDebugFunction  *pFunction,
    [in] ULONG32            nArgs,
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]
);
```

## <a name="parameters"></a><span data-ttu-id="2da0e-107">参数</span><span class="sxs-lookup"><span data-stu-id="2da0e-107">Parameters</span></span>

`pFunction`\
<span data-ttu-id="2da0e-108">[in]指向一个 ICorDebugFunction 对象，指定要调用的函数指针。</span><span class="sxs-lookup"><span data-stu-id="2da0e-108">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>

`nArgs`\
<span data-ttu-id="2da0e-109">[in]函数的参数数目。</span><span class="sxs-lookup"><span data-stu-id="2da0e-109">[in] The number of arguments for the function.</span></span>

`ppArgs`\
<span data-ttu-id="2da0e-110">[in]一个指针数组，其中每个指向一个 ICorDebugValue 对象，指定要传递给函数的参数。</span><span class="sxs-lookup"><span data-stu-id="2da0e-110">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="2da0e-111">备注</span><span class="sxs-lookup"><span data-stu-id="2da0e-111">Remarks</span></span>

<span data-ttu-id="2da0e-112">如果该函数是虚拟的`CallFunction`将执行虚拟调度。</span><span class="sxs-lookup"><span data-stu-id="2da0e-112">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="2da0e-113">如果函数是在不同的应用程序域中，将发生转换，前提是所有参数也都是该应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="2da0e-113">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>

## <a name="requirements"></a><span data-ttu-id="2da0e-114">要求</span><span class="sxs-lookup"><span data-stu-id="2da0e-114">Requirements</span></span>

<span data-ttu-id="2da0e-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2da0e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="2da0e-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2da0e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="2da0e-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2da0e-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="2da0e-118">**.NET framework 版本：** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="2da0e-118">**.NET Framework Versions:** 1.1, 1.0</span></span>

## <a name="see-also"></a><span data-ttu-id="2da0e-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="2da0e-119">See also</span></span>

- [<span data-ttu-id="2da0e-120">CallParameterizedFunction 方法</span><span class="sxs-lookup"><span data-stu-id="2da0e-120">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)