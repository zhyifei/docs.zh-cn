---
title: "ICorDebugReferenceValue::GetValue 方法"
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
- ICorDebugReferenceValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::GetValue method [.NET Framework debugging]
ms.assetid: 5da07f99-6c70-46ec-b997-5ab6fb7106cd
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6d7be70ec41b2044b4af10e102218ce487e4a5e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugreferencevaluegetvalue-method"></a><span data-ttu-id="b9026-102">ICorDebugReferenceValue::GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="b9026-102">ICorDebugReferenceValue::GetValue Method</span></span>
<span data-ttu-id="b9026-103">获取被引用的对象的当前内存地址。</span><span class="sxs-lookup"><span data-stu-id="b9026-103">Gets the current memory address of the referenced object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9026-104">语法</span><span class="sxs-lookup"><span data-stu-id="b9026-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] CORDB_ADDRESS   *pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9026-105">参数</span><span class="sxs-lookup"><span data-stu-id="b9026-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="b9026-106">[out]指向的指针`CORDB_ADDRESS`值，该值指定此 ICorDebugReferenceValue 对象所指向的对象的地址。</span><span class="sxs-lookup"><span data-stu-id="b9026-106">[out] A pointer to a `CORDB_ADDRESS` value that specifies the address of the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9026-107">惠?</span><span class="sxs-lookup"><span data-stu-id="b9026-107">Requirements</span></span>  
 <span data-ttu-id="b9026-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b9026-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9026-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9026-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9026-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9026-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9026-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9026-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
