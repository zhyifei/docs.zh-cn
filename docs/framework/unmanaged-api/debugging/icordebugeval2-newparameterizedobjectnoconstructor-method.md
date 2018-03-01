---
title: "ICorDebugEval2::NewParameterizedObjectNoConstructor 方法"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 27e4693b39f9ce27ac18eb2fa542b5a0196f21cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a><span data-ttu-id="667f0-102">ICorDebugEval2::NewParameterizedObjectNoConstructor 方法</span><span class="sxs-lookup"><span data-stu-id="667f0-102">ICorDebugEval2::NewParameterizedObjectNoConstructor Method</span></span>
<span data-ttu-id="667f0-103">但不尝试调用构造函数方法实例化指定的类的新参数化的类型对象。</span><span class="sxs-lookup"><span data-stu-id="667f0-103">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="667f0-104">语法</span><span class="sxs-lookup"><span data-stu-id="667f0-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="667f0-105">参数</span><span class="sxs-lookup"><span data-stu-id="667f0-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="667f0-106">[in]指向一个 ICorDebugClass 对象，表示要进行实例化的对象类的指针。</span><span class="sxs-lookup"><span data-stu-id="667f0-106">[in] A pointer to an ICorDebugClass object that represents the class of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="667f0-107">[in]传递的类型自变量数目。</span><span class="sxs-lookup"><span data-stu-id="667f0-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="667f0-108">[in]一个指针数组，其中每个指向对象的表示进行实例化的对象的类型自变量。</span><span class="sxs-lookup"><span data-stu-id="667f0-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="667f0-109">备注</span><span class="sxs-lookup"><span data-stu-id="667f0-109">Remarks</span></span>  
 <span data-ttu-id="667f0-110">`NewParameterizedObjectNoConstructor`方法将失败，如果类型参数数目不正确或传递的类型参数的错误类型。</span><span class="sxs-lookup"><span data-stu-id="667f0-110">The `NewParameterizedObjectNoConstructor` method will fail if an incorrect number of type arguments or the wrong types of type arguments are passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="667f0-111">惠?</span><span class="sxs-lookup"><span data-stu-id="667f0-111">Requirements</span></span>  
 <span data-ttu-id="667f0-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="667f0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="667f0-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="667f0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="667f0-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="667f0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="667f0-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="667f0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
