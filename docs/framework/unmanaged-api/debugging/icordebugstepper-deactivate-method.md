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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bcd7bfb52cadf740d8fe3cb92a09b071f530b7ee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994326"
---
# <a name="icordebugstepperdeactivate-method"></a><span data-ttu-id="af322-102">ICorDebugStepper::Deactivate 方法</span><span class="sxs-lookup"><span data-stu-id="af322-102">ICorDebugStepper::Deactivate Method</span></span>
<span data-ttu-id="af322-103">导致此 ICorDebugStepper 取消它收到的最后一个步骤命令。</span><span class="sxs-lookup"><span data-stu-id="af322-103">Causes this ICorDebugStepper to cancel the last step command that it received.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af322-104">语法</span><span class="sxs-lookup"><span data-stu-id="af322-104">Syntax</span></span>  
  
```  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="af322-105">备注</span><span class="sxs-lookup"><span data-stu-id="af322-105">Remarks</span></span>  
 <span data-ttu-id="af322-106">已取消最近收到的步骤命令后，可以发出新的单步执行命令。</span><span class="sxs-lookup"><span data-stu-id="af322-106">A new stepping command may be issued after the most recently received step command has been canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af322-107">要求</span><span class="sxs-lookup"><span data-stu-id="af322-107">Requirements</span></span>  
 <span data-ttu-id="af322-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="af322-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af322-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af322-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af322-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af322-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af322-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af322-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
