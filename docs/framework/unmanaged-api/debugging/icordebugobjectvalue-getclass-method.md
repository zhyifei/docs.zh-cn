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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a20ab7a7ecb5d01351d0c912e08955f44b26d5f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756996"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="28daf-102">ICorDebugObjectValue::GetClass 方法</span><span class="sxs-lookup"><span data-stu-id="28daf-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="28daf-103">获取此对象值的类。</span><span class="sxs-lookup"><span data-stu-id="28daf-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28daf-104">语法</span><span class="sxs-lookup"><span data-stu-id="28daf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28daf-105">参数</span><span class="sxs-lookup"><span data-stu-id="28daf-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="28daf-106">[out]指向表示此"ICorDebugObjectValue"对象所表示的对象值的类的"ICorDebugClass"对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="28daf-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28daf-107">备注</span><span class="sxs-lookup"><span data-stu-id="28daf-107">Remarks</span></span>  
 <span data-ttu-id="28daf-108">`GetClass`并[icordebugvalue:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)方法均返回一个值的类型有关的信息; 它们所取代的识别泛型[ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="28daf-108">The `GetClass` and [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28daf-109">要求</span><span class="sxs-lookup"><span data-stu-id="28daf-109">Requirements</span></span>  
 <span data-ttu-id="28daf-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="28daf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28daf-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28daf-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28daf-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28daf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28daf-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28daf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28daf-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="28daf-114">See also</span></span>
