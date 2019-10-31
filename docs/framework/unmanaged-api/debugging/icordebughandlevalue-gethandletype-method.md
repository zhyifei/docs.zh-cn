---
title: ICorDebugHandleValue::GetHandleType 方法
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.GetHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::GetHandleType
helpviewer_keywords:
- GetHandleType method [.NET Framework debugging]
- ICorDebugHandleValue::GetHandleType method [.NET Framework debugging]
ms.assetid: d5e7b12d-835a-4e86-ae2f-d658d4f1c67c
topic_type:
- apiref
ms.openlocfilehash: bc7d99d0ddb443cba227b7bad0cd53edb94c9101
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138544"
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="7ed80-102">ICorDebugHandleValue::GetHandleType 方法</span><span class="sxs-lookup"><span data-stu-id="7ed80-102">ICorDebugHandleValue::GetHandleType Method</span></span>
<span data-ttu-id="7ed80-103">获取一个值，该值指示此 ICorDebugHandleValue 对象所引用的句柄的类型。</span><span class="sxs-lookup"><span data-stu-id="7ed80-103">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ed80-104">语法</span><span class="sxs-lookup"><span data-stu-id="7ed80-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ed80-105">参数</span><span class="sxs-lookup"><span data-stu-id="7ed80-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="7ed80-106">弄指向 CorDebugHandleType 枚举的值的指针，该枚举指示此句柄的类型。</span><span class="sxs-lookup"><span data-stu-id="7ed80-106">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ed80-107">要求</span><span class="sxs-lookup"><span data-stu-id="7ed80-107">Requirements</span></span>  
 <span data-ttu-id="7ed80-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7ed80-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ed80-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ed80-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ed80-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ed80-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ed80-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ed80-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
