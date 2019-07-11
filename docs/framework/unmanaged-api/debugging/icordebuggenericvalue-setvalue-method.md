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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b6907cdf78fc70c75ddd711cd8593427857b172
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756889"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="0e44f-102">ICorDebugGenericValue::SetValue 方法</span><span class="sxs-lookup"><span data-stu-id="0e44f-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="0e44f-103">从指定的缓冲区中复制新值。</span><span class="sxs-lookup"><span data-stu-id="0e44f-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e44f-104">语法</span><span class="sxs-lookup"><span data-stu-id="0e44f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e44f-105">参数</span><span class="sxs-lookup"><span data-stu-id="0e44f-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="0e44f-106">[in]要从其中复制值指向缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="0e44f-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e44f-107">备注</span><span class="sxs-lookup"><span data-stu-id="0e44f-107">Remarks</span></span>  
 <span data-ttu-id="0e44f-108">对于引用类型，值是引用，而不是内容。</span><span class="sxs-lookup"><span data-stu-id="0e44f-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e44f-109">要求</span><span class="sxs-lookup"><span data-stu-id="0e44f-109">Requirements</span></span>  
 <span data-ttu-id="0e44f-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0e44f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e44f-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e44f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e44f-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e44f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e44f-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e44f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
