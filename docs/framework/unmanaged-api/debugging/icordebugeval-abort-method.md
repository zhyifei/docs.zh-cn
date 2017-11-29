---
title: "ICorDebugEval::Abort 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.Abort
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::Abort
helpviewer_keywords:
- Abort method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::Abort method [.NET Framework debugging]
ms.assetid: 7070b6d0-f2e0-44ff-b124-0944cd807e69
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a53597067d14c5b3dc1f8829b8ea0a0df07de25a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="6e844-102">ICorDebugEval::Abort 方法</span><span class="sxs-lookup"><span data-stu-id="6e844-102">ICorDebugEval::Abort Method</span></span>
<span data-ttu-id="6e844-103">中止当前正在执行此 ICorDebugEval 对象计算。</span><span class="sxs-lookup"><span data-stu-id="6e844-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e844-104">语法</span><span class="sxs-lookup"><span data-stu-id="6e844-104">Syntax</span></span>  
  
```  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="6e844-105">备注</span><span class="sxs-lookup"><span data-stu-id="6e844-105">Remarks</span></span>  
 <span data-ttu-id="6e844-106">如果评估嵌套的并且它不是最新，`Abort`方法可能会失败。</span><span class="sxs-lookup"><span data-stu-id="6e844-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e844-107">要求</span><span class="sxs-lookup"><span data-stu-id="6e844-107">Requirements</span></span>  
 <span data-ttu-id="6e844-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6e844-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e844-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e844-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e844-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e844-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e844-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e844-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
