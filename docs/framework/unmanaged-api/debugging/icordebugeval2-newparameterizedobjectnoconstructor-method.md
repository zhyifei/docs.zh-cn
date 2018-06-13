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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aad5a285fc2280dc062b0f4cbb69977a7e605e9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412764"
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a><span data-ttu-id="975d6-102">ICorDebugEval2::NewParameterizedObjectNoConstructor 方法</span><span class="sxs-lookup"><span data-stu-id="975d6-102">ICorDebugEval2::NewParameterizedObjectNoConstructor Method</span></span>
<span data-ttu-id="975d6-103">但不尝试调用构造函数方法实例化指定的类的新参数化的类型对象。</span><span class="sxs-lookup"><span data-stu-id="975d6-103">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="975d6-104">语法</span><span class="sxs-lookup"><span data-stu-id="975d6-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="975d6-105">参数</span><span class="sxs-lookup"><span data-stu-id="975d6-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="975d6-106">[in]指向一个 ICorDebugClass 对象，表示要进行实例化的对象类的指针。</span><span class="sxs-lookup"><span data-stu-id="975d6-106">[in] A pointer to an ICorDebugClass object that represents the class of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="975d6-107">[in]传递的类型自变量数目。</span><span class="sxs-lookup"><span data-stu-id="975d6-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="975d6-108">[in]一个指针数组，其中每个指向对象的表示进行实例化的对象的类型自变量。</span><span class="sxs-lookup"><span data-stu-id="975d6-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="975d6-109">备注</span><span class="sxs-lookup"><span data-stu-id="975d6-109">Remarks</span></span>  
 <span data-ttu-id="975d6-110">`NewParameterizedObjectNoConstructor`方法将失败，如果类型参数数目不正确或传递的类型参数的错误类型。</span><span class="sxs-lookup"><span data-stu-id="975d6-110">The `NewParameterizedObjectNoConstructor` method will fail if an incorrect number of type arguments or the wrong types of type arguments are passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="975d6-111">要求</span><span class="sxs-lookup"><span data-stu-id="975d6-111">Requirements</span></span>  
 <span data-ttu-id="975d6-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="975d6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="975d6-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="975d6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="975d6-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="975d6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="975d6-115">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="975d6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
