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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4d2ba850ffc6e49cf330174dda9524c7bac4549
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709190"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="24d9c-102">ICorDebugValue::GetType 方法</span><span class="sxs-lookup"><span data-stu-id="24d9c-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="24d9c-103">获取此"ICorDebugValue"对象的基元类型。</span><span class="sxs-lookup"><span data-stu-id="24d9c-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24d9c-104">语法</span><span class="sxs-lookup"><span data-stu-id="24d9c-104">Syntax</span></span>  
  
```  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="24d9c-105">参数</span><span class="sxs-lookup"><span data-stu-id="24d9c-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="24d9c-106">[out]指向"CorElementType"枚举，指示值的类型的值的指针。</span><span class="sxs-lookup"><span data-stu-id="24d9c-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24d9c-107">备注</span><span class="sxs-lookup"><span data-stu-id="24d9c-107">Remarks</span></span>  
 <span data-ttu-id="24d9c-108">如果对象是复杂的运行时类型，该类型可能检查通过适当的子类`ICorDebugValue`接口。</span><span class="sxs-lookup"><span data-stu-id="24d9c-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="24d9c-109">例如，"ICorDebugObjectValue"，该类继承自`ICorDebugValue`，表示复杂类型。</span><span class="sxs-lookup"><span data-stu-id="24d9c-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="24d9c-110">`GetType`并[icordebugobjectvalue:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)方法均返回一个值的类型有关的信息。</span><span class="sxs-lookup"><span data-stu-id="24d9c-110">The `GetType` and [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="24d9c-111">它们所取代的识别泛型[ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="24d9c-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24d9c-112">要求</span><span class="sxs-lookup"><span data-stu-id="24d9c-112">Requirements</span></span>  
 <span data-ttu-id="24d9c-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="24d9c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24d9c-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24d9c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24d9c-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24d9c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24d9c-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24d9c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24d9c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="24d9c-117">See also</span></span>

