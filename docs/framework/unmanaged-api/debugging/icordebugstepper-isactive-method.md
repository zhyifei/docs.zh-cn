---
title: ICorDebugStepper::IsActive 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::IsActive method [.NET Framework debugging]
ms.assetid: 8b35e7a9-b40e-40a9-8d8e-b82e823fc575
topic_type:
- apiref
ms.openlocfilehash: faddf30248b58c68037635480d8977f22ad077d0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379024"
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="366a1-102">ICorDebugStepper::IsActive 方法</span><span class="sxs-lookup"><span data-stu-id="366a1-102">ICorDebugStepper::IsActive Method</span></span>
<span data-ttu-id="366a1-103">获取一个值，该值指示此 ICorDebugStepper 当前是否正在执行步骤。</span><span class="sxs-lookup"><span data-stu-id="366a1-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="366a1-104">语法</span><span class="sxs-lookup"><span data-stu-id="366a1-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="366a1-105">参数</span><span class="sxs-lookup"><span data-stu-id="366a1-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="366a1-106">弄`true`如果分档器当前正在执行步骤，则返回; 否则返回 `false` 。</span><span class="sxs-lookup"><span data-stu-id="366a1-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="366a1-107">备注</span><span class="sxs-lookup"><span data-stu-id="366a1-107">Remarks</span></span>  
 <span data-ttu-id="366a1-108">任何步骤操作都保持活动状态，直到调试器接收到[ICorDebugManagedCallback：： StepComplete](icordebugmanagedcallback-stepcomplete-method.md)调用，这将自动停用分档器。</span><span class="sxs-lookup"><span data-stu-id="366a1-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="366a1-109">在达到回调条件之前，还可以通过调用[ICorDebugStepper：:D eactivate](icordebugstepper-deactivate-method.md)提前停用分档器。</span><span class="sxs-lookup"><span data-stu-id="366a1-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="366a1-110">要求</span><span class="sxs-lookup"><span data-stu-id="366a1-110">Requirements</span></span>  
 <span data-ttu-id="366a1-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="366a1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="366a1-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="366a1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="366a1-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="366a1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="366a1-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="366a1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
