---
title: ICorDebugManagedCallback::StepComplete 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.StepComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::StepComplete
helpviewer_keywords:
- StepComplete method [.NET Framework debugging]
- ICorDebugManagedCallback::StepComplete method [.NET Framework debugging]
ms.assetid: 5e1f2c47-81df-4530-826d-96489cd68719
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f5b243d8c618559bd4371bf3acde1136f532f55e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476134"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="97ef0-102">ICorDebugManagedCallback::StepComplete 方法</span><span class="sxs-lookup"><span data-stu-id="97ef0-102">ICorDebugManagedCallback::StepComplete Method</span></span>
<span data-ttu-id="97ef0-103">通知调试器步骤已完成。</span><span class="sxs-lookup"><span data-stu-id="97ef0-103">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97ef0-104">语法</span><span class="sxs-lookup"><span data-stu-id="97ef0-104">Syntax</span></span>  
  
```  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97ef0-105">参数</span><span class="sxs-lookup"><span data-stu-id="97ef0-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="97ef0-106">[in]指向一个 ICorDebugAppDomain 对象，表示包含此步骤具有已完成的线程的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="97ef0-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="97ef0-107">[in]指向表示此步骤具有已完成的线程的 ICorDebugThread 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="97ef0-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="97ef0-108">[in]指向表示执行代码中的步 ICorDebugStepper 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="97ef0-108">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="97ef0-109">[in]CorDebugStepReason 枚举，指示一个单步执行的结果的值。</span><span class="sxs-lookup"><span data-stu-id="97ef0-109">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97ef0-110">备注</span><span class="sxs-lookup"><span data-stu-id="97ef0-110">Remarks</span></span>  
 <span data-ttu-id="97ef0-111">分档器可能用于继续单步执行必要时，除非终止调试。</span><span class="sxs-lookup"><span data-stu-id="97ef0-111">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97ef0-112">要求</span><span class="sxs-lookup"><span data-stu-id="97ef0-112">Requirements</span></span>  
 <span data-ttu-id="97ef0-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="97ef0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97ef0-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97ef0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97ef0-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97ef0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97ef0-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97ef0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97ef0-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="97ef0-117">See also</span></span>
- [<span data-ttu-id="97ef0-118">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="97ef0-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
