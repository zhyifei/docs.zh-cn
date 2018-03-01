---
title: "ICorDebugStepper::Deactivate 方法"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1541c6fa838115655c3ff176a0cb29f803733daa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepperdeactivate-method"></a><span data-ttu-id="71a2b-102">ICorDebugStepper::Deactivate 方法</span><span class="sxs-lookup"><span data-stu-id="71a2b-102">ICorDebugStepper::Deactivate Method</span></span>
<span data-ttu-id="71a2b-103">导致此 ICorDebugStepper 取消它收到的最后一个步骤命令。</span><span class="sxs-lookup"><span data-stu-id="71a2b-103">Causes this ICorDebugStepper to cancel the last step command that it received.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71a2b-104">语法</span><span class="sxs-lookup"><span data-stu-id="71a2b-104">Syntax</span></span>  
  
```  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="71a2b-105">备注</span><span class="sxs-lookup"><span data-stu-id="71a2b-105">Remarks</span></span>  
 <span data-ttu-id="71a2b-106">已取消在最近收到的步骤命令后，可以发出一个新的单步执行命令。</span><span class="sxs-lookup"><span data-stu-id="71a2b-106">A new stepping command may be issued after the most recently received step command has been canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71a2b-107">惠?</span><span class="sxs-lookup"><span data-stu-id="71a2b-107">Requirements</span></span>  
 <span data-ttu-id="71a2b-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="71a2b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71a2b-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71a2b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71a2b-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71a2b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71a2b-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71a2b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
