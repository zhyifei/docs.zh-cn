---
title: "ICorDebugObjectValue::GetClass 方法"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6135dd3806d72b59ce858fab9d0a0b6c3b1f11b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="c4180-102">ICorDebugObjectValue::GetClass 方法</span><span class="sxs-lookup"><span data-stu-id="c4180-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="c4180-103">获取此对象值的类。</span><span class="sxs-lookup"><span data-stu-id="c4180-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4180-104">语法</span><span class="sxs-lookup"><span data-stu-id="c4180-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c4180-105">参数</span><span class="sxs-lookup"><span data-stu-id="c4180-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="c4180-106">[out]指向"ICorDebugClass"对象，表示此"ICorDebugObjectValue"对象所表示的对象值的类地址的指针。</span><span class="sxs-lookup"><span data-stu-id="c4180-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4180-107">备注</span><span class="sxs-lookup"><span data-stu-id="c4180-107">Remarks</span></span>  
 <span data-ttu-id="c4180-108">`GetClass`和[icordebugvalue:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)方法均返回有关值的类型信息; 它们会取代通过识别泛型[icordebugvalue2:: Getexacttype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="c4180-108">The `GetClass` and [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4180-109">惠?</span><span class="sxs-lookup"><span data-stu-id="c4180-109">Requirements</span></span>  
 <span data-ttu-id="c4180-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c4180-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4180-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4180-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4180-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4180-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4180-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4180-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4180-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4180-114">See Also</span></span>  
    
 
