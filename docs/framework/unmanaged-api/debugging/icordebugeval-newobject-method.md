---
title: ICorDebugEval::NewObject 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObject
helpviewer_keywords:
- NewObject method [.NET Framework debugging]
- ICorDebugEval::NewObject method [.NET Framework debugging]
ms.assetid: ce3025e8-defa-4c5e-8298-f49d71fa5736
topic_type:
- apiref
ms.openlocfilehash: e9570d3c916123093f69e7f26d3778f1c7184b1f
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976182"
---
# <a name="icordebugevalnewobject-method"></a><span data-ttu-id="01089-102">ICorDebugEval::NewObject 方法</span><span class="sxs-lookup"><span data-stu-id="01089-102">ICorDebugEval::NewObject Method</span></span>
<span data-ttu-id="01089-103">分配一个新的对象实例，并调用指定的构造函数方法。</span><span class="sxs-lookup"><span data-stu-id="01089-103">Allocates a new object instance and calls the specified constructor method.</span></span>  
  
 <span data-ttu-id="01089-104">此方法在 .NET Framework 版本2.0 中已过时。</span><span class="sxs-lookup"><span data-stu-id="01089-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="01089-105">改[为使用 ICorDebugEval2：： NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md) 。</span><span class="sxs-lookup"><span data-stu-id="01089-105">Use [ICorDebugEval2::NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01089-106">语法</span><span class="sxs-lookup"><span data-stu-id="01089-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01089-107">参数</span><span class="sxs-lookup"><span data-stu-id="01089-107">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="01089-108">中要调用的构造函数。</span><span class="sxs-lookup"><span data-stu-id="01089-108">[in] The constructor to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="01089-109">[in] `ppArgs` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="01089-109">[in] The size of the `ppArgs` array.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="01089-110">中ICorDebugValue 对象的数组，其中每个对象都表示要传递给构造函数的参数。</span><span class="sxs-lookup"><span data-stu-id="01089-110">[in] An array of ICorDebugValue objects, each of which represents an argument to be passed to the constructor.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01089-111">要求</span><span class="sxs-lookup"><span data-stu-id="01089-111">Requirements</span></span>  
 <span data-ttu-id="01089-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="01089-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01089-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01089-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01089-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01089-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01089-115">**.NET Framework 版本：** 1.1、1。0</span><span class="sxs-lookup"><span data-stu-id="01089-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01089-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01089-116">See also</span></span>

- [<span data-ttu-id="01089-117">NewParameterizedObject 方法</span><span class="sxs-lookup"><span data-stu-id="01089-117">NewParameterizedObject Method</span></span>](icordebugeval2-newparameterizedobject-method.md)
