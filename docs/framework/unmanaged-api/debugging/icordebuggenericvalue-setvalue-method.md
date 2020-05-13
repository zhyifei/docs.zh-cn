---
title: ICorDebugGenericValue::SetValue 方法
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::SetValue
helpviewer_keywords:
- ICorDebugGenericValue::SetValue method [.NET Framework debugging]
- SetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: ed4c6458-0435-44fc-8e78-8ba00be362f2
topic_type:
- apiref
ms.openlocfilehash: 972a981188c36236b81f3da17c09abeeb1e32857
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212186"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="66b87-102">ICorDebugGenericValue::SetValue 方法</span><span class="sxs-lookup"><span data-stu-id="66b87-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="66b87-103">从指定的缓冲区复制新值。</span><span class="sxs-lookup"><span data-stu-id="66b87-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66b87-104">语法</span><span class="sxs-lookup"><span data-stu-id="66b87-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66b87-105">参数</span><span class="sxs-lookup"><span data-stu-id="66b87-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="66b87-106">中指向要从中复制值的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="66b87-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66b87-107">备注</span><span class="sxs-lookup"><span data-stu-id="66b87-107">Remarks</span></span>  
 <span data-ttu-id="66b87-108">对于引用类型，该值是引用，而不是内容。</span><span class="sxs-lookup"><span data-stu-id="66b87-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66b87-109">要求</span><span class="sxs-lookup"><span data-stu-id="66b87-109">Requirements</span></span>  
 <span data-ttu-id="66b87-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="66b87-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66b87-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66b87-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66b87-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66b87-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66b87-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66b87-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
