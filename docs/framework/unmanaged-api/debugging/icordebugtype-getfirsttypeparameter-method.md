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
ms.openlocfilehash: 1a02190b595fb01bdc2df46182bfa64bfe638db4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791278"
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a><span data-ttu-id="2fa80-102">ICorDebugType::GetFirstTypeParameter 方法</span><span class="sxs-lookup"><span data-stu-id="2fa80-102">ICorDebugType::GetFirstTypeParameter Method</span></span>
<span data-ttu-id="2fa80-103">获取一个接口指针，该指针指向表示此 `ICorDebugType`所表示的类型的第一个 <xref:System.Type> 参数的 ICorDebugType。</span><span class="sxs-lookup"><span data-stu-id="2fa80-103">Gets an interface pointer to an ICorDebugType that represents the first <xref:System.Type> parameter of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fa80-104">语法</span><span class="sxs-lookup"><span data-stu-id="2fa80-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fa80-105">参数</span><span class="sxs-lookup"><span data-stu-id="2fa80-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="2fa80-106">弄指向表示第一个参数的 `ICorDebugType` 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="2fa80-106">[out] A pointer to the address of an `ICorDebugType` object that represents the first parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fa80-107">备注</span><span class="sxs-lookup"><span data-stu-id="2fa80-107">Remarks</span></span>  
 <span data-ttu-id="2fa80-108">如果有关类型的附加信息最多涉及一个类型参数，则可以调用 `GetFirstTypeParameter`。</span><span class="sxs-lookup"><span data-stu-id="2fa80-108">`GetFirstTypeParameter` can be called in cases where the additional information about the type involves, at most, one type parameter.</span></span> <span data-ttu-id="2fa80-109">特别是，如果类型是 ELEMENT_TYPE_ARRAY、ELEMENT_TYPE_SZARRAY、ELEMENT_TYPE_BYREF 或 ELEMENT_TYPE_PTR （如[ICorDebugType：： GetType](icordebugtype-gettype-method.md)方法所示），则可以使用此方法。</span><span class="sxs-lookup"><span data-stu-id="2fa80-109">In particular, it can be used if the type is an ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR, as indicated by the [ICorDebugType::GetType](icordebugtype-gettype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fa80-110">需求</span><span class="sxs-lookup"><span data-stu-id="2fa80-110">Requirements</span></span>  
 <span data-ttu-id="2fa80-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2fa80-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fa80-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2fa80-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2fa80-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fa80-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fa80-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fa80-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
