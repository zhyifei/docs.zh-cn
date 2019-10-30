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
ms.openlocfilehash: 6ea2b24d37f56a5cb9e6b3dea0d666c8acc719dc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091035"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="eea94-102">ICorDebugFrame::CreateStepper 方法</span><span class="sxs-lookup"><span data-stu-id="eea94-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="eea94-103">获取一个分档器，该分档器允许调试器执行相对于此 ICorDebugFrame 的单步执行操作。</span><span class="sxs-lookup"><span data-stu-id="eea94-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eea94-104">语法</span><span class="sxs-lookup"><span data-stu-id="eea94-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eea94-105">参数</span><span class="sxs-lookup"><span data-stu-id="eea94-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="eea94-106">弄指向 ICorDebugStepper 对象地址的指针，该对象允许调试器相对于当前帧执行单步操作。</span><span class="sxs-lookup"><span data-stu-id="eea94-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eea94-107">备注</span><span class="sxs-lookup"><span data-stu-id="eea94-107">Remarks</span></span>  
 <span data-ttu-id="eea94-108">如果帧不处于活动状态，则在步骤完成之前，分档器对象通常需要返回到帧。</span><span class="sxs-lookup"><span data-stu-id="eea94-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eea94-109">要求</span><span class="sxs-lookup"><span data-stu-id="eea94-109">Requirements</span></span>  
 <span data-ttu-id="eea94-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eea94-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eea94-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eea94-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eea94-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eea94-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eea94-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eea94-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
