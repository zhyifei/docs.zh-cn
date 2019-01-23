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
ms.openlocfilehash: 0d403fe24f368a5cd05358cd589023a4c8710a37
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587409"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="d65ef-102">ICorDebugObjectValue::GetClass 方法</span><span class="sxs-lookup"><span data-stu-id="d65ef-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="d65ef-103">获取此对象值的类。</span><span class="sxs-lookup"><span data-stu-id="d65ef-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d65ef-104">语法</span><span class="sxs-lookup"><span data-stu-id="d65ef-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d65ef-105">参数</span><span class="sxs-lookup"><span data-stu-id="d65ef-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="d65ef-106">[out]指向表示此"ICorDebugObjectValue"对象所表示的对象值的类的"ICorDebugClass"对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="d65ef-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d65ef-107">备注</span><span class="sxs-lookup"><span data-stu-id="d65ef-107">Remarks</span></span>  
 <span data-ttu-id="d65ef-108">`GetClass`并[icordebugvalue:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)方法均返回一个值的类型有关的信息; 它们所取代的识别泛型[ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="d65ef-108">The `GetClass` and [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d65ef-109">要求</span><span class="sxs-lookup"><span data-stu-id="d65ef-109">Requirements</span></span>  
 <span data-ttu-id="d65ef-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d65ef-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d65ef-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d65ef-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d65ef-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d65ef-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d65ef-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d65ef-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d65ef-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d65ef-114">See also</span></span>


