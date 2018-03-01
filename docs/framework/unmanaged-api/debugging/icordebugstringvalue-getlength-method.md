---
title: "ICorDebugStringValue::GetLength 方法"
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
- ICorDebugStringValue.GetLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetLength
helpviewer_keywords:
- ICorDebugStringValue::GetLength method [.NET Framework debugging]
- GetLength method [.NET Framework debugging]
ms.assetid: a1ebfc69-46a6-4225-8788-b7cfb2f15e1d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 129998bc2e7530aefefb2655a83cb04a9aa4cc6c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="9310f-102">ICorDebugStringValue::GetLength 方法</span><span class="sxs-lookup"><span data-stu-id="9310f-102">ICorDebugStringValue::GetLength Method</span></span>
<span data-ttu-id="9310f-103">获取此 ICorDebugStringValue 引用字符串中的字符数。</span><span class="sxs-lookup"><span data-stu-id="9310f-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9310f-104">语法</span><span class="sxs-lookup"><span data-stu-id="9310f-104">Syntax</span></span>  
  
```  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9310f-105">参数</span><span class="sxs-lookup"><span data-stu-id="9310f-105">Parameters</span></span>  
 `pcchString`  
 <span data-ttu-id="9310f-106">[out]指向一个值，指定引用的字符串的长度的指针`ICorDebugStringValue`对象。</span><span class="sxs-lookup"><span data-stu-id="9310f-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9310f-107">惠?</span><span class="sxs-lookup"><span data-stu-id="9310f-107">Requirements</span></span>  
 <span data-ttu-id="9310f-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9310f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9310f-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9310f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9310f-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9310f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9310f-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9310f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
