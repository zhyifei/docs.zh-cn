---
title: "ICorDebugFrame::CreateStepper 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.CreateStepper
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a6f575febc488d01700c32198d4c00916dd5e249
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="0f301-102">ICorDebugFrame::CreateStepper 方法</span><span class="sxs-lookup"><span data-stu-id="0f301-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="0f301-103">获取使调试器能够执行单步执行操作相对于此 ICorDebugFrame 分档器。</span><span class="sxs-lookup"><span data-stu-id="0f301-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f301-104">语法</span><span class="sxs-lookup"><span data-stu-id="0f301-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f301-105">参数</span><span class="sxs-lookup"><span data-stu-id="0f301-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="0f301-106">[out]指向使调试器能够执行相对于当前帧的单步执行操作的 ICorDebugStepper 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="0f301-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f301-107">备注</span><span class="sxs-lookup"><span data-stu-id="0f301-107">Remarks</span></span>  
 <span data-ttu-id="0f301-108">如果帧未处于活动状态的该分档器对象通常将具有在步骤完成之前返回与该框架。</span><span class="sxs-lookup"><span data-stu-id="0f301-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f301-109">要求</span><span class="sxs-lookup"><span data-stu-id="0f301-109">Requirements</span></span>  
 <span data-ttu-id="0f301-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0f301-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f301-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f301-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f301-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f301-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f301-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f301-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
