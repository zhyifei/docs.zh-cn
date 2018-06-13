---
title: ICorDebugEval::IsActive 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::IsActive method [.NET Framework debugging]
ms.assetid: bf2bba24-d278-43bd-b1c5-35680e748d3e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fe29b3e35d2fbd42fac2d9ec1d1c594abe1239c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411153"
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="fb1f1-102">ICorDebugEval::IsActive 方法</span><span class="sxs-lookup"><span data-stu-id="fb1f1-102">ICorDebugEval::IsActive Method</span></span>
<span data-ttu-id="fb1f1-103">获取一个值，该值指示当前正在执行此 ICorDebugEval 对象。</span><span class="sxs-lookup"><span data-stu-id="fb1f1-103">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb1f1-104">语法</span><span class="sxs-lookup"><span data-stu-id="fb1f1-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb1f1-105">参数</span><span class="sxs-lookup"><span data-stu-id="fb1f1-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="fb1f1-106">[out]指向一个值，指示此评估是否处于活动状态的指针。</span><span class="sxs-lookup"><span data-stu-id="fb1f1-106">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb1f1-107">要求</span><span class="sxs-lookup"><span data-stu-id="fb1f1-107">Requirements</span></span>  
 <span data-ttu-id="fb1f1-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fb1f1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb1f1-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb1f1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb1f1-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb1f1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb1f1-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb1f1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
