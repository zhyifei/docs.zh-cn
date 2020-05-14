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
ms.openlocfilehash: dcec97bac2aefc8db1f9351f1dacb0f36fc0d2a0
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396801"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="1c0a0-102">ICorDebugValue2::GetExactType 方法</span><span class="sxs-lookup"><span data-stu-id="1c0a0-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="1c0a0-103">获取一个接口指针，该指针指向表示 <xref:System.Type> 此值的的 "ICorDebugType" 对象。</span><span class="sxs-lookup"><span data-stu-id="1c0a0-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c0a0-104">语法</span><span class="sxs-lookup"><span data-stu-id="1c0a0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c0a0-105">参数</span><span class="sxs-lookup"><span data-stu-id="1c0a0-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="1c0a0-106">弄指向对象地址的指针，该 `ICorDebugType` 对象表示 <xref:System.Type> 此 "ICorDebugValue2" 对象表示的值的。</span><span class="sxs-lookup"><span data-stu-id="1c0a0-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c0a0-107">备注</span><span class="sxs-lookup"><span data-stu-id="1c0a0-107">Remarks</span></span>  
 <span data-ttu-id="1c0a0-108">一般识别 `GetExactType` 方法取代了[ICorDebugObjectValue：： GetClass](icordebugobjectvalue-getclass-method.md)和[ICorDebugValue：： GetType](icordebugvalue-gettype-method.md)方法，其中每个方法都返回值类型的相关信息。</span><span class="sxs-lookup"><span data-stu-id="1c0a0-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c0a0-109">要求</span><span class="sxs-lookup"><span data-stu-id="1c0a0-109">Requirements</span></span>  
 <span data-ttu-id="1c0a0-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1c0a0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c0a0-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c0a0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c0a0-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c0a0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c0a0-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c0a0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c0a0-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c0a0-114">See also</span></span>
