---
title: "ICorDebugEval::IsActive 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.IsActive
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::IsActive method [.NET Framework debugging]
ms.assetid: bf2bba24-d278-43bd-b1c5-35680e748d3e
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a695bfc4b7575a1a56dfba3dca515321a07239cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugevalisactive-method"></a><span data-ttu-id="ae5c2-102">ICorDebugEval::IsActive 方法</span><span class="sxs-lookup"><span data-stu-id="ae5c2-102">ICorDebugEval::IsActive Method</span></span>
<span data-ttu-id="ae5c2-103">获取一个值，该值指示当前正在执行此 ICorDebugEval 对象。</span><span class="sxs-lookup"><span data-stu-id="ae5c2-103">Gets a value that indicates whether this ICorDebugEval object is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae5c2-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae5c2-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL              *pbActive  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae5c2-105">参数</span><span class="sxs-lookup"><span data-stu-id="ae5c2-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="ae5c2-106">[out]指向一个值，指示此评估是否处于活动状态的指针。</span><span class="sxs-lookup"><span data-stu-id="ae5c2-106">[out] Pointer to a value that indicates whether this evaluation is active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae5c2-107">要求</span><span class="sxs-lookup"><span data-stu-id="ae5c2-107">Requirements</span></span>  
 <span data-ttu-id="ae5c2-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae5c2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae5c2-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae5c2-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae5c2-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae5c2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae5c2-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae5c2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
