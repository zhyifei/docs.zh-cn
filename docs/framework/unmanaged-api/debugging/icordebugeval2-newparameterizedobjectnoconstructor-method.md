---
title: ICorDebugEval2::NewParameterizedObjectNoConstructor 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObjectNoConstructor
helpviewer_keywords:
- NewParameterizedObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObjectNoConstructor method [.NET Framework debugging]
ms.assetid: f15b5b78-94f4-4eb9-b3b3-a621272f357c
topic_type:
- apiref
ms.openlocfilehash: 90fce1710f97341fb49be1d07f7af2edf8cb848c
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976078"
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a><span data-ttu-id="ece18-102">ICorDebugEval2::NewParameterizedObjectNoConstructor 方法</span><span class="sxs-lookup"><span data-stu-id="ece18-102">ICorDebugEval2::NewParameterizedObjectNoConstructor Method</span></span>
<span data-ttu-id="ece18-103">实例化指定类的一个新参数化类型对象，而不尝试调用构造函数方法。</span><span class="sxs-lookup"><span data-stu-id="ece18-103">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ece18-104">语法</span><span class="sxs-lookup"><span data-stu-id="ece18-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ece18-105">参数</span><span class="sxs-lookup"><span data-stu-id="ece18-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="ece18-106">中指向 ICorDebugClass 对象的指针，该对象表示要实例化的对象的类。</span><span class="sxs-lookup"><span data-stu-id="ece18-106">[in] A pointer to an ICorDebugClass object that represents the class of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="ece18-107">中传递的类型参数的数目。</span><span class="sxs-lookup"><span data-stu-id="ece18-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="ece18-108">中指针的数组，其中每个都指向一个 ICorDebugType 对象，该对象表示要实例化的对象的类型参数。</span><span class="sxs-lookup"><span data-stu-id="ece18-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ece18-109">备注</span><span class="sxs-lookup"><span data-stu-id="ece18-109">Remarks</span></span>  
 <span data-ttu-id="ece18-110">如果`NewParameterizedObjectNoConstructor`传递的类型参数的数目不正确或类型参数的类型不正确，则方法将失败。</span><span class="sxs-lookup"><span data-stu-id="ece18-110">The `NewParameterizedObjectNoConstructor` method will fail if an incorrect number of type arguments or the wrong types of type arguments are passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ece18-111">要求</span><span class="sxs-lookup"><span data-stu-id="ece18-111">Requirements</span></span>  
 <span data-ttu-id="ece18-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ece18-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ece18-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ece18-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ece18-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ece18-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ece18-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ece18-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
