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
ms.openlocfilehash: 682d6684b6c86485530b9e5283d843f3b2eb7e46
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995990"
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="f4edd-102">ICorDebugEval::Abort 方法</span><span class="sxs-lookup"><span data-stu-id="f4edd-102">ICorDebugEval::Abort Method</span></span>
<span data-ttu-id="f4edd-103">中止当前正在执行此 ICorDebugEval 对象的计算。</span><span class="sxs-lookup"><span data-stu-id="f4edd-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4edd-104">语法</span><span class="sxs-lookup"><span data-stu-id="f4edd-104">Syntax</span></span>  
  
```  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="f4edd-105">备注</span><span class="sxs-lookup"><span data-stu-id="f4edd-105">Remarks</span></span>  
 <span data-ttu-id="f4edd-106">如果评估嵌套的并且不是最新的项，`Abort`方法可能会失败。</span><span class="sxs-lookup"><span data-stu-id="f4edd-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4edd-107">要求</span><span class="sxs-lookup"><span data-stu-id="f4edd-107">Requirements</span></span>  
 <span data-ttu-id="f4edd-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f4edd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4edd-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4edd-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4edd-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4edd-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4edd-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4edd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
