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
ms.openlocfilehash: b8ff07c483ef1bcbf9d5141b7180cea08454ebef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417094"
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="ac501-102">ICorDebugValueBreakpoint::GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="ac501-102">ICorDebugValueBreakpoint::GetValue Method</span></span>
<span data-ttu-id="ac501-103">获取一个表示在其设置断点的对象的值的"ICorDebugValue"对象的接口指针。</span><span class="sxs-lookup"><span data-stu-id="ac501-103">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac501-104">语法</span><span class="sxs-lookup"><span data-stu-id="ac501-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac501-105">参数</span><span class="sxs-lookup"><span data-stu-id="ac501-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="ac501-106">[out]指向的地址的指针`ICorDebugValue`对象。</span><span class="sxs-lookup"><span data-stu-id="ac501-106">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac501-107">要求</span><span class="sxs-lookup"><span data-stu-id="ac501-107">Requirements</span></span>  
 <span data-ttu-id="ac501-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ac501-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac501-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac501-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac501-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac501-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac501-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac501-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac501-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac501-112">See Also</span></span>  
 
