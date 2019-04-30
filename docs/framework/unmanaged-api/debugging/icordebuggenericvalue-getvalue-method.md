---
title: ICorDebugGenericValue::GetValue 方法
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::GetValue
helpviewer_keywords:
- ICorDebugGenericValue::GetValue method [.NET Framework debugging]
- GetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: 4e95d7cb-144d-4ccf-8a69-d605f4744be2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53db4dcb13303c9e7bdd77a46b3c9526364bac06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995639"
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="521ed-102">ICorDebugGenericValue::GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="521ed-102">ICorDebugGenericValue::GetValue Method</span></span>
<span data-ttu-id="521ed-103">将此泛型值复制到指定的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="521ed-103">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="521ed-104">语法</span><span class="sxs-lookup"><span data-stu-id="521ed-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="521ed-105">参数</span><span class="sxs-lookup"><span data-stu-id="521ed-105">Parameters</span></span>  
 `pTo`  
 <span data-ttu-id="521ed-106">[out]指向由此 ICorDebugGenericValue 对象的值的指针。</span><span class="sxs-lookup"><span data-stu-id="521ed-106">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="521ed-107">值可能是简单类型或引用类型 （即，指针）。</span><span class="sxs-lookup"><span data-stu-id="521ed-107">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="521ed-108">要求</span><span class="sxs-lookup"><span data-stu-id="521ed-108">Requirements</span></span>  
 <span data-ttu-id="521ed-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="521ed-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="521ed-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="521ed-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="521ed-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="521ed-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="521ed-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="521ed-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
