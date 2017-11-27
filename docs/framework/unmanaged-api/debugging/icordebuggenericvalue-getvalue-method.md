---
title: "ICorDebugGenericValue::GetValue 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGenericValue.GetValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGenericValue::GetValue
helpviewer_keywords:
- ICorDebugGenericValue::GetValue method [.NET Framework debugging]
- GetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: 4e95d7cb-144d-4ccf-8a69-d605f4744be2
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2432d79c6f17c7374d2beb400e93ae4088a8b1ae
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="3f0d6-102">ICorDebugGenericValue::GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="3f0d6-102">ICorDebugGenericValue::GetValue Method</span></span>
<span data-ttu-id="3f0d6-103">将此泛型值复制到指定的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="3f0d6-103">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f0d6-104">语法</span><span class="sxs-lookup"><span data-stu-id="3f0d6-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f0d6-105">参数</span><span class="sxs-lookup"><span data-stu-id="3f0d6-105">Parameters</span></span>  
 `pTo`  
 <span data-ttu-id="3f0d6-106">[out]指向此 ICorDebugGenericValue 对象表示的值的指针。</span><span class="sxs-lookup"><span data-stu-id="3f0d6-106">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="3f0d6-107">值可以是简单类型或引用类型 （即，指针）。</span><span class="sxs-lookup"><span data-stu-id="3f0d6-107">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f0d6-108">要求</span><span class="sxs-lookup"><span data-stu-id="3f0d6-108">Requirements</span></span>  
 <span data-ttu-id="3f0d6-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3f0d6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f0d6-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f0d6-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f0d6-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f0d6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f0d6-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f0d6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
