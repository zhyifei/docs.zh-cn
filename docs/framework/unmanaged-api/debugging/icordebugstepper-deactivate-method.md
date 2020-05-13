---
title: ICorDebugStepper::Deactivate 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Deactivate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Deactivate
helpviewer_keywords:
- Deactivate method [.NET Framework debugging]
- ICorDebugStepper::Deactivate method [.NET Framework debugging]
ms.assetid: 855f4199-b62d-40ce-998e-1eb4a1772142
topic_type:
- apiref
ms.openlocfilehash: 760f69baf311cf320e9c358ba1c45c942934f1a5
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379400"
---
# <a name="icordebugstepperdeactivate-method"></a><span data-ttu-id="469c0-102">ICorDebugStepper::Deactivate 方法</span><span class="sxs-lookup"><span data-stu-id="469c0-102">ICorDebugStepper::Deactivate Method</span></span>
<span data-ttu-id="469c0-103">使此 ICorDebugStepper 取消其收到的最后一个步骤命令。</span><span class="sxs-lookup"><span data-stu-id="469c0-103">Causes this ICorDebugStepper to cancel the last step command that it received.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="469c0-104">语法</span><span class="sxs-lookup"><span data-stu-id="469c0-104">Syntax</span></span>  
  
```cpp  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="469c0-105">备注</span><span class="sxs-lookup"><span data-stu-id="469c0-105">Remarks</span></span>  
 <span data-ttu-id="469c0-106">在取消最近收到的步骤命令后，可能会发出新的单步执行命令。</span><span class="sxs-lookup"><span data-stu-id="469c0-106">A new stepping command may be issued after the most recently received step command has been canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="469c0-107">要求</span><span class="sxs-lookup"><span data-stu-id="469c0-107">Requirements</span></span>  
 <span data-ttu-id="469c0-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="469c0-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="469c0-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="469c0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="469c0-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="469c0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="469c0-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="469c0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
