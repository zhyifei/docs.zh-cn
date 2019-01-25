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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 982af81f8f3886ae26b56114cc36374279c07593
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656344"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="c84ab-102">ICorDebugValue2::GetExactType 方法</span><span class="sxs-lookup"><span data-stu-id="c84ab-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="c84ab-103">获取表示"ICorDebugType"对象的接口指针<xref:System.Type>的此值。</span><span class="sxs-lookup"><span data-stu-id="c84ab-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c84ab-104">语法</span><span class="sxs-lookup"><span data-stu-id="c84ab-104">Syntax</span></span>  
  
```  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c84ab-105">参数</span><span class="sxs-lookup"><span data-stu-id="c84ab-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="c84ab-106">[out]指向的地址的指针`ICorDebugType`对象，表示<xref:System.Type>由此"ICorDebugValue2"对象的值。</span><span class="sxs-lookup"><span data-stu-id="c84ab-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c84ab-107">备注</span><span class="sxs-lookup"><span data-stu-id="c84ab-107">Remarks</span></span>  
 <span data-ttu-id="c84ab-108">识别泛型`GetExactType`方法取代了这两[icordebugobjectvalue:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)并且[icordebugvalue:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)方法，每个的返回值的类型有关的信息.</span><span class="sxs-lookup"><span data-stu-id="c84ab-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c84ab-109">要求</span><span class="sxs-lookup"><span data-stu-id="c84ab-109">Requirements</span></span>  
 <span data-ttu-id="c84ab-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c84ab-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c84ab-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c84ab-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c84ab-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c84ab-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c84ab-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c84ab-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c84ab-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c84ab-114">See also</span></span>

