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
ms.openlocfilehash: 0d992ea86b3221af222bb01f1985fe277cea5a2c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480047"
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="2bc57-102">ICorDebugEval::IsActive 方法</span><span class="sxs-lookup"><span data-stu-id="2bc57-102">ICorDebugEval::IsActive Method</span></span>
<span data-ttu-id="2bc57-103">获取一个值，该值指示此 ICorDebugEval 对象当前是否正在执行。</span><span class="sxs-lookup"><span data-stu-id="2bc57-103">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bc57-104">语法</span><span class="sxs-lookup"><span data-stu-id="2bc57-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bc57-105">参数</span><span class="sxs-lookup"><span data-stu-id="2bc57-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="2bc57-106">[out]指向一个值，指示此评估版是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="2bc57-106">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bc57-107">要求</span><span class="sxs-lookup"><span data-stu-id="2bc57-107">Requirements</span></span>  
 <span data-ttu-id="2bc57-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2bc57-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bc57-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2bc57-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2bc57-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bc57-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bc57-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bc57-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
