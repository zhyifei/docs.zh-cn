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
ms.openlocfilehash: 5924a3914c7fe04413b4a6744bce263b56165d78
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140215"
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="99c05-102">ICorDebugValueBreakpoint::GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="99c05-102">ICorDebugValueBreakpoint::GetValue Method</span></span>
<span data-ttu-id="99c05-103">获取一个指向 "ICorDebugValue" 对象的接口指针，该对象表示在其上设置断点的对象的值。</span><span class="sxs-lookup"><span data-stu-id="99c05-103">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99c05-104">语法</span><span class="sxs-lookup"><span data-stu-id="99c05-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99c05-105">参数</span><span class="sxs-lookup"><span data-stu-id="99c05-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="99c05-106">弄指向 `ICorDebugValue` 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="99c05-106">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99c05-107">要求</span><span class="sxs-lookup"><span data-stu-id="99c05-107">Requirements</span></span>  
 <span data-ttu-id="99c05-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="99c05-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99c05-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99c05-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99c05-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99c05-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99c05-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99c05-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99c05-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="99c05-112">See also</span></span>
