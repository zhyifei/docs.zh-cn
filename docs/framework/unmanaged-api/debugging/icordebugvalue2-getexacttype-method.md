---
title: ICorDebugValue2::GetExactType 方法
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
ms.openlocfilehash: 441d225dadbbca09ab27c8ccd70debe32f4c12da
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140265"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="45b73-102">ICorDebugValue2::GetExactType 方法</span><span class="sxs-lookup"><span data-stu-id="45b73-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="45b73-103">获取一个接口指针，该指针指向表示此值 <xref:System.Type> 的 "ICorDebugType" 对象。</span><span class="sxs-lookup"><span data-stu-id="45b73-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45b73-104">语法</span><span class="sxs-lookup"><span data-stu-id="45b73-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45b73-105">参数</span><span class="sxs-lookup"><span data-stu-id="45b73-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="45b73-106">弄指向 `ICorDebugType` 对象的地址的指针，该对象表示此 "ICorDebugValue2" 对象表示的值的 <xref:System.Type>。</span><span class="sxs-lookup"><span data-stu-id="45b73-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45b73-107">备注</span><span class="sxs-lookup"><span data-stu-id="45b73-107">Remarks</span></span>  
 <span data-ttu-id="45b73-108">泛型感知 `GetExactType` 方法取代了[ICorDebugObjectValue：： GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)和[ICorDebugValue：： GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)方法，其中每个方法都返回值类型的相关信息。</span><span class="sxs-lookup"><span data-stu-id="45b73-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45b73-109">要求</span><span class="sxs-lookup"><span data-stu-id="45b73-109">Requirements</span></span>  
 <span data-ttu-id="45b73-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="45b73-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45b73-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45b73-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45b73-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45b73-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45b73-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45b73-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45b73-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="45b73-114">See also</span></span>
