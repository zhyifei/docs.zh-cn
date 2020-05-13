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
ms.openlocfilehash: 39b4e7e5123447a36254b55b6168c80e48c8dcab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205453"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="65412-102">ICorDebugFrame::CreateStepper 方法</span><span class="sxs-lookup"><span data-stu-id="65412-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="65412-103">获取一个分档器，该分档器允许调试器执行相对于此 ICorDebugFrame 的单步执行操作。</span><span class="sxs-lookup"><span data-stu-id="65412-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65412-104">语法</span><span class="sxs-lookup"><span data-stu-id="65412-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65412-105">参数</span><span class="sxs-lookup"><span data-stu-id="65412-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="65412-106">弄指向 ICorDebugStepper 对象地址的指针，该对象允许调试器相对于当前帧执行单步操作。</span><span class="sxs-lookup"><span data-stu-id="65412-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65412-107">备注</span><span class="sxs-lookup"><span data-stu-id="65412-107">Remarks</span></span>  
 <span data-ttu-id="65412-108">如果帧不处于活动状态，则在步骤完成之前，分档器对象通常需要返回到帧。</span><span class="sxs-lookup"><span data-stu-id="65412-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65412-109">要求</span><span class="sxs-lookup"><span data-stu-id="65412-109">Requirements</span></span>  
 <span data-ttu-id="65412-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="65412-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65412-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65412-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65412-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65412-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65412-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65412-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
