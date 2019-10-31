---
title: ICorDebugObjectValue::GetClass 方法
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetClass
helpviewer_keywords:
- ICorDebugObjectValue::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 5be25292-8357-445f-a09b-f997c0de761c
topic_type:
- apiref
ms.openlocfilehash: 4719f155957f04471d4ad2b8d71bec9c0f0d30c0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096089"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="9b5d6-102">ICorDebugObjectValue::GetClass 方法</span><span class="sxs-lookup"><span data-stu-id="9b5d6-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="9b5d6-103">获取此对象值的类。</span><span class="sxs-lookup"><span data-stu-id="9b5d6-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b5d6-104">语法</span><span class="sxs-lookup"><span data-stu-id="9b5d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b5d6-105">参数</span><span class="sxs-lookup"><span data-stu-id="9b5d6-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="9b5d6-106">弄一个指向 "ICorDebugClass" 对象地址的指针，该对象表示由此 "ICorDebugObjectValue" 对象表示的对象值的类。</span><span class="sxs-lookup"><span data-stu-id="9b5d6-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b5d6-107">备注</span><span class="sxs-lookup"><span data-stu-id="9b5d6-107">Remarks</span></span>  
 <span data-ttu-id="9b5d6-108">`GetClass` 和[ICorDebugValue：： GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)方法都返回有关值类型的信息;它们都由可感知泛型的[ICorDebugValue2：： GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)取代。</span><span class="sxs-lookup"><span data-stu-id="9b5d6-108">The `GetClass` and [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b5d6-109">要求</span><span class="sxs-lookup"><span data-stu-id="9b5d6-109">Requirements</span></span>  
 <span data-ttu-id="9b5d6-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9b5d6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b5d6-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b5d6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b5d6-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b5d6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b5d6-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b5d6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b5d6-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b5d6-114">See also</span></span>
