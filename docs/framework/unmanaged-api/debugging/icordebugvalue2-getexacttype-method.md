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
ms.openlocfilehash: f1f8292a6964a6b25e228fcd07ab21a7ee5f5a04
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423327"
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="c167a-102">ICorDebugValue2::GetExactType 方法</span><span class="sxs-lookup"><span data-stu-id="c167a-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="c167a-103">获取一个表示"ICorDebugType"对象的接口指针<xref:System.Type>的此值。</span><span class="sxs-lookup"><span data-stu-id="c167a-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c167a-104">语法</span><span class="sxs-lookup"><span data-stu-id="c167a-104">Syntax</span></span>  
  
```  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c167a-105">参数</span><span class="sxs-lookup"><span data-stu-id="c167a-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="c167a-106">[out]指向的地址的指针`ICorDebugType`对象，表示<xref:System.Type>此"ICorDebugValue2"对象所表示的值。</span><span class="sxs-lookup"><span data-stu-id="c167a-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c167a-107">备注</span><span class="sxs-lookup"><span data-stu-id="c167a-107">Remarks</span></span>  
 <span data-ttu-id="c167a-108">识别泛型`GetExactType`方法取代同时[icordebugobjectvalue:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)和[icordebugvalue:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)方法，每个的返回值的类型信息.</span><span class="sxs-lookup"><span data-stu-id="c167a-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c167a-109">要求</span><span class="sxs-lookup"><span data-stu-id="c167a-109">Requirements</span></span>  
 <span data-ttu-id="c167a-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c167a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c167a-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c167a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c167a-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c167a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c167a-113">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c167a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c167a-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c167a-114">See Also</span></span>  
 
