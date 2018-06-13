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
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413798"
---
# <a name="icordebugevalabort-method"></a><span data-ttu-id="b8f17-102">ICorDebugEval::Abort 方法</span><span class="sxs-lookup"><span data-stu-id="b8f17-102">ICorDebugEval::Abort Method</span></span>
<span data-ttu-id="b8f17-103">中止当前正在执行此 ICorDebugEval 对象计算。</span><span class="sxs-lookup"><span data-stu-id="b8f17-103">Aborts the computation this ICorDebugEval object is currently performing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8f17-104">语法</span><span class="sxs-lookup"><span data-stu-id="b8f17-104">Syntax</span></span>  
  
```  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="b8f17-105">备注</span><span class="sxs-lookup"><span data-stu-id="b8f17-105">Remarks</span></span>  
 <span data-ttu-id="b8f17-106">如果评估嵌套的并且它不是最新，`Abort`方法可能会失败。</span><span class="sxs-lookup"><span data-stu-id="b8f17-106">If the evaluation is nested and it is not the most recent one, the `Abort` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8f17-107">要求</span><span class="sxs-lookup"><span data-stu-id="b8f17-107">Requirements</span></span>  
 <span data-ttu-id="b8f17-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b8f17-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8f17-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8f17-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8f17-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8f17-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8f17-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8f17-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
