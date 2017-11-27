---
title: "ICorDebugManagedCallback::StepComplete 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.StepComplete
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::StepComplete
helpviewer_keywords:
- StepComplete method [.NET Framework debugging]
- ICorDebugManagedCallback::StepComplete method [.NET Framework debugging]
ms.assetid: 5e1f2c47-81df-4530-826d-96489cd68719
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: eabc9a2730a1afdf574cee97a6f1b40bae34c7ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="51934-102">ICorDebugManagedCallback::StepComplete 方法</span><span class="sxs-lookup"><span data-stu-id="51934-102">ICorDebugManagedCallback::StepComplete Method</span></span>
<span data-ttu-id="51934-103">通知调试器已完成一个步骤。</span><span class="sxs-lookup"><span data-stu-id="51934-103">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51934-104">语法</span><span class="sxs-lookup"><span data-stu-id="51934-104">Syntax</span></span>  
  
```  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="51934-105">参数</span><span class="sxs-lookup"><span data-stu-id="51934-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="51934-106">[in]指向一个表示包含该步骤已完成在其中的线程的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="51934-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="51934-107">[in]指向一个表示该步骤已完成在其中的线程的 ICorDebugThread 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="51934-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="51934-108">[in]指向一个表示在代码执行步骤的 ICorDebugStepper 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="51934-108">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="51934-109">[in]CorDebugStepReason 枚举，该值指示一个单步执行的结果的值。</span><span class="sxs-lookup"><span data-stu-id="51934-109">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51934-110">备注</span><span class="sxs-lookup"><span data-stu-id="51934-110">Remarks</span></span>  
 <span data-ttu-id="51934-111">分档器可能用于继续单步执行必要时，除非调试已终止。</span><span class="sxs-lookup"><span data-stu-id="51934-111">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51934-112">要求</span><span class="sxs-lookup"><span data-stu-id="51934-112">Requirements</span></span>  
 <span data-ttu-id="51934-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="51934-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51934-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51934-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51934-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51934-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51934-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51934-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51934-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51934-117">See Also</span></span>  
 [<span data-ttu-id="51934-118">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="51934-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
