---
title: "ICorDebugType::GetFirstTypeParameter 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetFirstTypeParameter
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetFirstTypeParameter
helpviewer_keywords:
- ICorDebugType::GetFirstTypeParameter method [.NET Framework debugging]
- GetFirstTypeParameter method [.NET Framework debugging]
ms.assetid: 35bb594f-af6a-4349-83fe-e98702674e03
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e963553bfeac2d659de8fc460a938d2d523b53e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a><span data-ttu-id="4b851-102">ICorDebugType::GetFirstTypeParameter 方法</span><span class="sxs-lookup"><span data-stu-id="4b851-102">ICorDebugType::GetFirstTypeParameter Method</span></span>
<span data-ttu-id="4b851-103">获取的接口指针指向表示第一个 ICorDebugType<xref:System.Type>表示此类型的参数`ICorDebugType`。</span><span class="sxs-lookup"><span data-stu-id="4b851-103">Gets an interface pointer to an ICorDebugType that represents the first <xref:System.Type> parameter of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b851-104">语法</span><span class="sxs-lookup"><span data-stu-id="4b851-104">Syntax</span></span>  
  
```  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b851-105">参数</span><span class="sxs-lookup"><span data-stu-id="4b851-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="4b851-106">[out]指向的地址的指针`ICorDebugType`表示第一个参数的对象。</span><span class="sxs-lookup"><span data-stu-id="4b851-106">[out] A pointer to the address of an `ICorDebugType` object that represents the first parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b851-107">备注</span><span class="sxs-lookup"><span data-stu-id="4b851-107">Remarks</span></span>  
 <span data-ttu-id="4b851-108">`GetFirstTypeParameter`可以调用在类型有关的附加信息的涉及其中，最多的情况下一个类型参数。</span><span class="sxs-lookup"><span data-stu-id="4b851-108">`GetFirstTypeParameter` can be called in cases where the additional information about the type involves, at most, one type parameter.</span></span> <span data-ttu-id="4b851-109">具体而言，如果，则可以使用该类型是 ELEMENT_TYPE_ARRAY、 ELEMENT_TYPE_SZARRAY、 ELEMENT_TYPE_BYREF，还是 ELEMENT_TYPE_PTR，所述[icordebugtype:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="4b851-109">In particular, it can be used if the type is an ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b851-110">惠?</span><span class="sxs-lookup"><span data-stu-id="4b851-110">Requirements</span></span>  
 <span data-ttu-id="4b851-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4b851-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b851-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b851-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b851-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b851-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b851-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b851-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
