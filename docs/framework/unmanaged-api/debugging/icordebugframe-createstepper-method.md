---
title: "ICorDebugFrame::CreateStepper 方法"
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
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 93f6741a030e72406fb8099c6373896d14cb9332
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="4674d-102">ICorDebugFrame::CreateStepper 方法</span><span class="sxs-lookup"><span data-stu-id="4674d-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="4674d-103">获取使调试器能够执行单步执行操作相对于此 ICorDebugFrame 分档器。</span><span class="sxs-lookup"><span data-stu-id="4674d-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4674d-104">语法</span><span class="sxs-lookup"><span data-stu-id="4674d-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4674d-105">参数</span><span class="sxs-lookup"><span data-stu-id="4674d-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="4674d-106">[out]指向使调试器能够执行相对于当前帧的单步执行操作的 ICorDebugStepper 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="4674d-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4674d-107">备注</span><span class="sxs-lookup"><span data-stu-id="4674d-107">Remarks</span></span>  
 <span data-ttu-id="4674d-108">如果帧未处于活动状态的该分档器对象通常将具有在步骤完成之前返回与该框架。</span><span class="sxs-lookup"><span data-stu-id="4674d-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4674d-109">惠?</span><span class="sxs-lookup"><span data-stu-id="4674d-109">Requirements</span></span>  
 <span data-ttu-id="4674d-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4674d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4674d-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4674d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4674d-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4674d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4674d-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4674d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
