---
title: "ICorDebugValue2::GetExactType 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue2.GetExactType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e061e0cd1d467a556c7dd1bd6298784d015aa94
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvalue2getexacttype-method"></a><span data-ttu-id="a0b44-102">ICorDebugValue2::GetExactType 方法</span><span class="sxs-lookup"><span data-stu-id="a0b44-102">ICorDebugValue2::GetExactType Method</span></span>
<span data-ttu-id="a0b44-103">获取一个表示"ICorDebugType"对象的接口指针<xref:System.Type>的此值。</span><span class="sxs-lookup"><span data-stu-id="a0b44-103">Gets an interface pointer to an "ICorDebugType" object that represents the <xref:System.Type> of this value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0b44-104">语法</span><span class="sxs-lookup"><span data-stu-id="a0b44-104">Syntax</span></span>  
  
```  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0b44-105">参数</span><span class="sxs-lookup"><span data-stu-id="a0b44-105">Parameters</span></span>  
 `ppType`  
 <span data-ttu-id="a0b44-106">[out]指向的地址的指针`ICorDebugType`对象，表示<xref:System.Type>此"ICorDebugValue2"对象所表示的值。</span><span class="sxs-lookup"><span data-stu-id="a0b44-106">[out] A pointer to the address of an `ICorDebugType` object that represents the <xref:System.Type> of the value represented by this "ICorDebugValue2" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0b44-107">备注</span><span class="sxs-lookup"><span data-stu-id="a0b44-107">Remarks</span></span>  
 <span data-ttu-id="a0b44-108">识别泛型`GetExactType`方法取代同时[icordebugobjectvalue:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)和[icordebugvalue:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)方法，每个的返回值的类型信息.</span><span class="sxs-lookup"><span data-stu-id="a0b44-108">The generics-aware `GetExactType` method supersedes both the [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) and the [ICorDebugValue::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) methods, each of which return information about the type of a value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0b44-109">要求</span><span class="sxs-lookup"><span data-stu-id="a0b44-109">Requirements</span></span>  
 <span data-ttu-id="a0b44-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a0b44-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0b44-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0b44-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0b44-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0b44-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0b44-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0b44-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0b44-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0b44-114">See Also</span></span>  
 
