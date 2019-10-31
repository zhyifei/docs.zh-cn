---
title: ICorDebugType::GetFirstTypeParameter 方法
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetFirstTypeParameter
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetFirstTypeParameter
helpviewer_keywords:
- ICorDebugType::GetFirstTypeParameter method [.NET Framework debugging]
- GetFirstTypeParameter method [.NET Framework debugging]
ms.assetid: 35bb594f-af6a-4349-83fe-e98702674e03
topic_type:
- apiref
ms.openlocfilehash: 4dbc042143e68dc962eb21b2bf741cbaefc1977e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122356"
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a><span data-ttu-id="4444d-102">ICorDebugType::GetFirstTypeParameter 方法</span><span class="sxs-lookup"><span data-stu-id="4444d-102">ICorDebugType::GetFirstTypeParameter Method</span></span>
<span data-ttu-id="4444d-103">获取一个接口指针，该指针指向表示此 `ICorDebugType`所表示的类型的第一个 <xref:System.Type> 参数的 ICorDebugType。</span><span class="sxs-lookup"><span data-stu-id="4444d-103">Gets an interface pointer to an ICorDebugType that represents the first <xref:System.Type> parameter of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4444d-104">语法</span><span class="sxs-lookup"><span data-stu-id="4444d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4444d-105">参数</span><span class="sxs-lookup"><span data-stu-id="4444d-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="4444d-106">弄指向表示第一个参数的 `ICorDebugType` 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="4444d-106">[out] A pointer to the address of an `ICorDebugType` object that represents the first parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4444d-107">备注</span><span class="sxs-lookup"><span data-stu-id="4444d-107">Remarks</span></span>  
 <span data-ttu-id="4444d-108">如果有关类型的附加信息最多涉及一个类型参数，则可以调用 `GetFirstTypeParameter`。</span><span class="sxs-lookup"><span data-stu-id="4444d-108">`GetFirstTypeParameter` can be called in cases where the additional information about the type involves, at most, one type parameter.</span></span> <span data-ttu-id="4444d-109">特别是，如果类型是 ELEMENT_TYPE_ARRAY、ELEMENT_TYPE_SZARRAY、ELEMENT_TYPE_BYREF 或 ELEMENT_TYPE_PTR （如[ICorDebugType：： GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)方法所示），则可以使用此方法。</span><span class="sxs-lookup"><span data-stu-id="4444d-109">In particular, it can be used if the type is an ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4444d-110">要求</span><span class="sxs-lookup"><span data-stu-id="4444d-110">Requirements</span></span>  
 <span data-ttu-id="4444d-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4444d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4444d-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4444d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4444d-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4444d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4444d-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4444d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
