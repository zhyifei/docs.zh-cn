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
ms.openlocfilehash: e901c65824ee8d6949c79c7778944148c0d9eb28
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976052"
---
# <a name="icordebugeval2rudeabort-method"></a><span data-ttu-id="a87ee-102">ICorDebugEval2::RudeAbort 方法</span><span class="sxs-lookup"><span data-stu-id="a87ee-102">ICorDebugEval2::RudeAbort Method</span></span>
<span data-ttu-id="a87ee-103">中止此`ICorDebugEval2`当前正在执行的计算。</span><span class="sxs-lookup"><span data-stu-id="a87ee-103">Aborts the computation that this `ICorDebugEval2` is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a87ee-104">语法</span><span class="sxs-lookup"><span data-stu-id="a87ee-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="a87ee-105">备注</span><span class="sxs-lookup"><span data-stu-id="a87ee-105">Remarks</span></span>  
 <span data-ttu-id="a87ee-106">`RudeAbort`不会释放该计算器持有的任何锁，因此会使调试会话处于不安全状态。</span><span class="sxs-lookup"><span data-stu-id="a87ee-106">`RudeAbort` does not release any locks that the evaluator holds, so it leaves the debugging session in an unsafe state.</span></span> <span data-ttu-id="a87ee-107">请特别小心调用此方法。</span><span class="sxs-lookup"><span data-stu-id="a87ee-107">Call this method with extreme caution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a87ee-108">要求</span><span class="sxs-lookup"><span data-stu-id="a87ee-108">Requirements</span></span>  
 <span data-ttu-id="a87ee-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a87ee-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a87ee-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a87ee-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a87ee-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a87ee-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a87ee-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a87ee-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
