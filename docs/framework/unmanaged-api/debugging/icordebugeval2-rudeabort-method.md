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
ms.openlocfilehash: 0aabff090634f1ecdeec5636336ad1fb77b8b81c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988918"
---
# <a name="icordebugeval2rudeabort-method"></a><span data-ttu-id="17331-102">ICorDebugEval2::RudeAbort 方法</span><span class="sxs-lookup"><span data-stu-id="17331-102">ICorDebugEval2::RudeAbort Method</span></span>
<span data-ttu-id="17331-103">中止计算此`ICorDebugEval2`当前正在执行。</span><span class="sxs-lookup"><span data-stu-id="17331-103">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17331-104">语法</span><span class="sxs-lookup"><span data-stu-id="17331-104">Syntax</span></span>  
  
```  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="17331-105">备注</span><span class="sxs-lookup"><span data-stu-id="17331-105">Remarks</span></span>  
 <span data-ttu-id="17331-106">`RudeAbort` 不会释放计算器持有，任何锁，因此调试会话仍处于不安全的状态。</span><span class="sxs-lookup"><span data-stu-id="17331-106">`RudeAbort` does not release any locks that the evaluator holds, so it leaves the debugging session in an unsafe state.</span></span> <span data-ttu-id="17331-107">调用此方法时要特别注意。</span><span class="sxs-lookup"><span data-stu-id="17331-107">Call this method with extreme caution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17331-108">要求</span><span class="sxs-lookup"><span data-stu-id="17331-108">Requirements</span></span>  
 <span data-ttu-id="17331-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="17331-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17331-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17331-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17331-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17331-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17331-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17331-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
