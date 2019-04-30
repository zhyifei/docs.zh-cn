---
title: ICorDebugFrame::CreateStepper 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3fe3cbc4bad83496bcc58aaea60e6724b1d1f06c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988892"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="e02cb-102">ICorDebugFrame::CreateStepper 方法</span><span class="sxs-lookup"><span data-stu-id="e02cb-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="e02cb-103">获取使调试器能够在执行单步执行操作相对于此 ICorDebugFrame 分档器。</span><span class="sxs-lookup"><span data-stu-id="e02cb-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e02cb-104">语法</span><span class="sxs-lookup"><span data-stu-id="e02cb-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e02cb-105">参数</span><span class="sxs-lookup"><span data-stu-id="e02cb-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="e02cb-106">[out]为使调试器能够执行相对于当前的框架的单步执行操作的 ICorDebugStepper 对象的地址指针。</span><span class="sxs-lookup"><span data-stu-id="e02cb-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e02cb-107">备注</span><span class="sxs-lookup"><span data-stu-id="e02cb-107">Remarks</span></span>  
 <span data-ttu-id="e02cb-108">如果帧未处于活动状态，分档器对象通常需要此步骤已完成之前返回的帧。</span><span class="sxs-lookup"><span data-stu-id="e02cb-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e02cb-109">要求</span><span class="sxs-lookup"><span data-stu-id="e02cb-109">Requirements</span></span>  
 <span data-ttu-id="e02cb-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e02cb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e02cb-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e02cb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e02cb-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e02cb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e02cb-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e02cb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
