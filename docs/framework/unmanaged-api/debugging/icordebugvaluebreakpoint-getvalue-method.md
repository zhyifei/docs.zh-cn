---
title: ICorDebugValueBreakpoint::GetValue 方法
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugValueBreakpoint interface [.NET Framework debugging]
- ICorDebugValueBreakpoint::GetValue method [.NET Framework debugging]
ms.assetid: 52a73654-bc47-48b6-b2b1-a4456b10140c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da23c7da7869c9190b8ce4ad94553a1cb8fc958d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495125"
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="e64b0-102">ICorDebugValueBreakpoint::GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="e64b0-102">ICorDebugValueBreakpoint::GetValue Method</span></span>
<span data-ttu-id="e64b0-103">获取表示在其设置断点的对象的值的"ICorDebugValue"对象的接口指针。</span><span class="sxs-lookup"><span data-stu-id="e64b0-103">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e64b0-104">语法</span><span class="sxs-lookup"><span data-stu-id="e64b0-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e64b0-105">参数</span><span class="sxs-lookup"><span data-stu-id="e64b0-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="e64b0-106">[out]指向的地址的指针`ICorDebugValue`对象。</span><span class="sxs-lookup"><span data-stu-id="e64b0-106">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e64b0-107">要求</span><span class="sxs-lookup"><span data-stu-id="e64b0-107">Requirements</span></span>  
 <span data-ttu-id="e64b0-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e64b0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e64b0-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e64b0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e64b0-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e64b0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e64b0-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e64b0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e64b0-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="e64b0-112">See also</span></span>

