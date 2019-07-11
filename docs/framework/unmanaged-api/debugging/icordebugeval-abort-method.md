---
title: ICorDebugEval::Abort 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval.Abort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::Abort
helpviewer_keywords:
- Abort method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::Abort method [.NET Framework debugging]
ms.assetid: 7070b6d0-f2e0-44ff-b124-0944cd807e69
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 052c467f5570119cd08b4719c768d178dd52aba2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752219"
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="28901-102">ICorDebugEval::Abort 方法</span><span class="sxs-lookup"><span data-stu-id="28901-102">ICorDebugEval::Abort Method</span></span>
<span data-ttu-id="28901-103">中止当前正在执行此 ICorDebugEval 对象的计算。</span><span class="sxs-lookup"><span data-stu-id="28901-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28901-104">语法</span><span class="sxs-lookup"><span data-stu-id="28901-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="28901-105">备注</span><span class="sxs-lookup"><span data-stu-id="28901-105">Remarks</span></span>  
 <span data-ttu-id="28901-106">如果评估嵌套的并且不是最新的项，`Abort`方法可能会失败。</span><span class="sxs-lookup"><span data-stu-id="28901-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28901-107">要求</span><span class="sxs-lookup"><span data-stu-id="28901-107">Requirements</span></span>  
 <span data-ttu-id="28901-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="28901-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28901-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28901-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28901-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28901-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28901-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28901-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
