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
ms.openlocfilehash: 646b2661148e38f3c918fc18fce5c9cd0b1134a1
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213018"
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="c3cfc-102">ICorDebugGenericValue::GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="c3cfc-102">ICorDebugGenericValue::GetValue Method</span></span>
<span data-ttu-id="c3cfc-103">将此泛型的值复制到指定的缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="c3cfc-103">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3cfc-104">语法</span><span class="sxs-lookup"><span data-stu-id="c3cfc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3cfc-105">参数</span><span class="sxs-lookup"><span data-stu-id="c3cfc-105">Parameters</span></span>  
 `pTo`  
 <span data-ttu-id="c3cfc-106">弄一个指针，指向由此 ICorDebugGenericValue 对象表示的值。</span><span class="sxs-lookup"><span data-stu-id="c3cfc-106">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="c3cfc-107">此值可以是简单类型或引用类型（即指针）。</span><span class="sxs-lookup"><span data-stu-id="c3cfc-107">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3cfc-108">要求</span><span class="sxs-lookup"><span data-stu-id="c3cfc-108">Requirements</span></span>  
 <span data-ttu-id="c3cfc-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c3cfc-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3cfc-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3cfc-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3cfc-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3cfc-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3cfc-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3cfc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
