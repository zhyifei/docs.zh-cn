---
title: "ICorDebugEval::Abort 方法"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 064febeec32e5c43b6b73ef2b3a44625f151eb48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="d88e3-102">ICorDebugEval::Abort 方法</span><span class="sxs-lookup"><span data-stu-id="d88e3-102">ICorDebugEval::Abort Method</span></span>
<span data-ttu-id="d88e3-103">中止当前正在执行此 ICorDebugEval 对象计算。</span><span class="sxs-lookup"><span data-stu-id="d88e3-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d88e3-104">语法</span><span class="sxs-lookup"><span data-stu-id="d88e3-104">Syntax</span></span>  
  
```  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d88e3-105">备注</span><span class="sxs-lookup"><span data-stu-id="d88e3-105">Remarks</span></span>  
 <span data-ttu-id="d88e3-106">如果评估嵌套的并且它不是最新，`Abort`方法可能会失败。</span><span class="sxs-lookup"><span data-stu-id="d88e3-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d88e3-107">惠?</span><span class="sxs-lookup"><span data-stu-id="d88e3-107">Requirements</span></span>  
 <span data-ttu-id="d88e3-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d88e3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d88e3-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d88e3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d88e3-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d88e3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d88e3-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d88e3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
