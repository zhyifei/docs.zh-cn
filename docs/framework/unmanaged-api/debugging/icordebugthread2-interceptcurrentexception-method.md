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
ms.openlocfilehash: c25a03ef5bbba18da31787c911f83a1348badd4b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791451"
---
# <a name="icordebugthread2interceptcurrentexception-method"></a><span data-ttu-id="c6d2d-102">ICorDebugThread2::InterceptCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="c6d2d-102">ICorDebugThread2::InterceptCurrentException Method</span></span>
<span data-ttu-id="c6d2d-103">允许调试器截获此线程上的当前异常。</span><span class="sxs-lookup"><span data-stu-id="c6d2d-103">Allows a debugger to intercept the current exception on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6d2d-104">语法</span><span class="sxs-lookup"><span data-stu-id="c6d2d-104">Syntax</span></span>  
  
```cpp  
HRESULT InterceptCurrentException (  
    [in] ICorDebugFrame  *pFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6d2d-105">参数</span><span class="sxs-lookup"><span data-stu-id="c6d2d-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="c6d2d-106">中指向表示活动堆栈帧的 ICorDebugFrame 的指针。</span><span class="sxs-lookup"><span data-stu-id="c6d2d-106">[in] A pointer to an ICorDebugFrame that represents the active stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6d2d-107">备注</span><span class="sxs-lookup"><span data-stu-id="c6d2d-107">Remarks</span></span>  
 <span data-ttu-id="c6d2d-108">可以在异常回调（[ICorDebugManagedCallback：： exception](icordebugmanagedcallback-exception-method.md)或[ICorDebugManagedCallback2：： exception](icordebugmanagedcallback2-exception-method.md)）与对[ICorDebugController：： Continue](icordebugcontroller-continue-method.md)的关联调用之间调用 `InterceptCurrentException` 方法。</span><span class="sxs-lookup"><span data-stu-id="c6d2d-108">The `InterceptCurrentException` method can be called between an exception callback ([ICorDebugManagedCallback::Exception](icordebugmanagedcallback-exception-method.md) or [ICorDebugManagedCallback2::Exception](icordebugmanagedcallback2-exception-method.md)) and the associated call to [ICorDebugController::Continue](icordebugcontroller-continue-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6d2d-109">需求</span><span class="sxs-lookup"><span data-stu-id="c6d2d-109">Requirements</span></span>  
 <span data-ttu-id="c6d2d-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c6d2d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6d2d-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6d2d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6d2d-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6d2d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6d2d-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6d2d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
