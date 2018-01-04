---
title: "ICorDebugReferenceValue::IsNull 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugReferenceValue.IsNull
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugReferenceValue::IsNull
helpviewer_keywords:
- IsNull method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::IsNull method [.NET Framework debugging]
ms.assetid: 99e8c8d7-a1c0-47c8-9dbd-03e0b2bcb4d5
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 53eaa411dc405142461de99bc787eba7a5d52db6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugreferencevalueisnull-method"></a><span data-ttu-id="11214-102">ICorDebugReferenceValue::IsNull 方法</span><span class="sxs-lookup"><span data-stu-id="11214-102">ICorDebugReferenceValue::IsNull Method</span></span>
<span data-ttu-id="11214-103">获取一个值，该值指示此 ICorDebugReferenceValue 是否为空值，在这种情况下`ICorDebugReferenceValue`不指向的对象。</span><span class="sxs-lookup"><span data-stu-id="11214-103">Gets a value that indicates whether this ICorDebugReferenceValue is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11214-104">语法</span><span class="sxs-lookup"><span data-stu-id="11214-104">Syntax</span></span>  
  
```  
HRESULT IsNull (  
    [out] BOOL   *pbNull  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11214-105">参数</span><span class="sxs-lookup"><span data-stu-id="11214-105">Parameters</span></span>  
 `pbNull`  
 <span data-ttu-id="11214-106">[out]一个布尔值，是一个指向`true`如果此`ICorDebugReferenceValue`对象为空; 否则为`pbNull`是`false`。</span><span class="sxs-lookup"><span data-stu-id="11214-106">[out] A pointer to a Boolean value that is `true` if this `ICorDebugReferenceValue` object is null; otherwise, `pbNull` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11214-107">惠?</span><span class="sxs-lookup"><span data-stu-id="11214-107">Requirements</span></span>  
 <span data-ttu-id="11214-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="11214-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11214-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11214-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11214-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11214-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11214-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11214-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
