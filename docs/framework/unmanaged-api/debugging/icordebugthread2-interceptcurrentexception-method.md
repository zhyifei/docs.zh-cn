---
title: ICorDebugThread2::InterceptCurrentException 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.InterceptCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::InterceptCurrentException
helpviewer_keywords:
- InterceptCurrentException method [.NET Framework debugging]
- ICorDebugThread2::InterceptCurrentException method [.NET Framework debugging]
ms.assetid: 536d2357-1b97-49e0-a10c-c860aed74e6e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01b883a5c6dd0cff119ff09747d32c607ac7ec60
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500988"
---
# <a name="icordebugthread2interceptcurrentexception-method"></a><span data-ttu-id="7ee87-102">ICorDebugThread2::InterceptCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="7ee87-102">ICorDebugThread2::InterceptCurrentException Method</span></span>
<span data-ttu-id="7ee87-103">允许调试器来拦截此线程上的当前异常。</span><span class="sxs-lookup"><span data-stu-id="7ee87-103">Allows a debugger to intercept the current exception on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ee87-104">语法</span><span class="sxs-lookup"><span data-stu-id="7ee87-104">Syntax</span></span>  
  
```  
HRESULT InterceptCurrentException (  
    [in] ICorDebugFrame  *pFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ee87-105">参数</span><span class="sxs-lookup"><span data-stu-id="7ee87-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="7ee87-106">[in]表示的活动堆栈帧 ICorDebugFrame 指向的指针。</span><span class="sxs-lookup"><span data-stu-id="7ee87-106">[in] A pointer to an ICorDebugFrame that represents the active stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ee87-107">备注</span><span class="sxs-lookup"><span data-stu-id="7ee87-107">Remarks</span></span>  
 <span data-ttu-id="7ee87-108">`InterceptCurrentException`之间的异常回调可以调用方法 ([icordebugmanagedcallback:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md)或[ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)) 和关联的调用[Icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)。</span><span class="sxs-lookup"><span data-stu-id="7ee87-108">The `InterceptCurrentException` method can be called between an exception callback ([ICorDebugManagedCallback::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md) or [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)) and the associated call to [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ee87-109">要求</span><span class="sxs-lookup"><span data-stu-id="7ee87-109">Requirements</span></span>  
 <span data-ttu-id="7ee87-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7ee87-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ee87-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ee87-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ee87-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ee87-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ee87-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ee87-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
