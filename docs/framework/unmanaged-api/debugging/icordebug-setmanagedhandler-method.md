---
title: "ICorDebug::SetManagedHandler 方法"
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
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dde32b6a8251474c4254e35a3a1ba3ba3bafcb8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="09912-102">ICorDebug::SetManagedHandler 方法</span><span class="sxs-lookup"><span data-stu-id="09912-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="09912-103">指定托管事件的事件处理程序对象。</span><span class="sxs-lookup"><span data-stu-id="09912-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09912-104">语法</span><span class="sxs-lookup"><span data-stu-id="09912-104">Syntax</span></span>  
  
```  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="09912-105">参数</span><span class="sxs-lookup"><span data-stu-id="09912-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="09912-106">[in]指向的指针[ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)对象，它是事件处理程序对象。</span><span class="sxs-lookup"><span data-stu-id="09912-106">[in] A pointer to an [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09912-107">备注</span><span class="sxs-lookup"><span data-stu-id="09912-107">Remarks</span></span>  
 <span data-ttu-id="09912-108">`SetManagedHandler`必须在创建时调用。</span><span class="sxs-lookup"><span data-stu-id="09912-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="09912-109">如果`ICorDebugManagedCallback`实现不包含足够的接口来处理的应用程序正在调试的调试事件`SetManagedHandler`返回 HRESULT E_NOINTERFACE。</span><span class="sxs-lookup"><span data-stu-id="09912-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09912-110">惠?</span><span class="sxs-lookup"><span data-stu-id="09912-110">Requirements</span></span>  
 <span data-ttu-id="09912-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="09912-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09912-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09912-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09912-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09912-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09912-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09912-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09912-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="09912-115">See Also</span></span>  
 [<span data-ttu-id="09912-116">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="09912-116">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
