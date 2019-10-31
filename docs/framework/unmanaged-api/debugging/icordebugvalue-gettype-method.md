---
title: ICorDebugValue::GetType 方法
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
ms.openlocfilehash: 284a74823b01305f8c6e025f70bb9209c8607b7b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137078"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="ca0f6-102">ICorDebugValue::GetType 方法</span><span class="sxs-lookup"><span data-stu-id="ca0f6-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="ca0f6-103">获取此 "ICorDebugValue" 对象的基元类型。</span><span class="sxs-lookup"><span data-stu-id="ca0f6-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca0f6-104">语法</span><span class="sxs-lookup"><span data-stu-id="ca0f6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca0f6-105">参数</span><span class="sxs-lookup"><span data-stu-id="ca0f6-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="ca0f6-106">弄一个指针，指向 "CorElementType" 枚举的值，该值指示值的类型。</span><span class="sxs-lookup"><span data-stu-id="ca0f6-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca0f6-107">备注</span><span class="sxs-lookup"><span data-stu-id="ca0f6-107">Remarks</span></span>  
 <span data-ttu-id="ca0f6-108">如果对象是复杂的运行时类型，则可以通过 `ICorDebugValue` 接口的相应子类检查该类型。</span><span class="sxs-lookup"><span data-stu-id="ca0f6-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="ca0f6-109">例如，从 `ICorDebugValue`继承的 "ICorDebugObjectValue" 表示复杂类型。</span><span class="sxs-lookup"><span data-stu-id="ca0f6-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="ca0f6-110">`GetType` 和[ICorDebugObjectValue：： GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)方法都返回有关值类型的信息。</span><span class="sxs-lookup"><span data-stu-id="ca0f6-110">The `GetType` and [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="ca0f6-111">它们都是由识别泛型的[ICorDebugValue2：： GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)方法取代的。</span><span class="sxs-lookup"><span data-stu-id="ca0f6-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca0f6-112">要求</span><span class="sxs-lookup"><span data-stu-id="ca0f6-112">Requirements</span></span>  
 <span data-ttu-id="ca0f6-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ca0f6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca0f6-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca0f6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca0f6-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca0f6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca0f6-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca0f6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca0f6-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca0f6-117">See also</span></span>
