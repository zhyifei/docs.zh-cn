---
title: ICorDebugEval2::RudeAbort 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.RudeAbort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::RudeAbort
helpviewer_keywords:
- ICorDebugEval2::RudeAbort method [.NET Framework debugging]
- RudeAbort method, ICorDebugEval2 interface [.NET Framework debugging]
ms.assetid: 02468edf-d32b-4cb3-aaa8-3dd2abfc8b25
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a1adb79e5081fc909d0cd180d8161eccea7e58e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754352"
---
# <a name="icordebugeval2rudeabort-method"></a><span data-ttu-id="052d4-102">ICorDebugEval2::RudeAbort 方法</span><span class="sxs-lookup"><span data-stu-id="052d4-102">ICorDebugEval2::RudeAbort Method</span></span>
<span data-ttu-id="052d4-103">中止计算此`ICorDebugEval2`当前正在执行。</span><span class="sxs-lookup"><span data-stu-id="052d4-103">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="052d4-104">语法</span><span class="sxs-lookup"><span data-stu-id="052d4-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="052d4-105">备注</span><span class="sxs-lookup"><span data-stu-id="052d4-105">Remarks</span></span>  
 <span data-ttu-id="052d4-106">`RudeAbort` 不会释放计算器持有，任何锁，因此调试会话仍处于不安全的状态。</span><span class="sxs-lookup"><span data-stu-id="052d4-106">`RudeAbort` does not release any locks that the evaluator holds, so it leaves the debugging session in an unsafe state.</span></span> <span data-ttu-id="052d4-107">调用此方法时要特别注意。</span><span class="sxs-lookup"><span data-stu-id="052d4-107">Call this method with extreme caution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="052d4-108">要求</span><span class="sxs-lookup"><span data-stu-id="052d4-108">Requirements</span></span>  
 <span data-ttu-id="052d4-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="052d4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="052d4-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="052d4-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="052d4-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="052d4-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="052d4-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="052d4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
