---
title: "ICorDebugCode::GetVersionNumber 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetVersionNumber
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6efcfa60a6254081ea28aeb9d51f41410ab5049e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="c9bb6-102">ICorDebugCode::GetVersionNumber 方法</span><span class="sxs-lookup"><span data-stu-id="c9bb6-102">ICorDebugCode::GetVersionNumber Method</span></span>
<span data-ttu-id="c9bb6-103">获取标识此"icor 调试代码"表示的代码的版本的基于 1 的数字。</span><span class="sxs-lookup"><span data-stu-id="c9bb6-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9bb6-104">语法</span><span class="sxs-lookup"><span data-stu-id="c9bb6-104">Syntax</span></span>  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32    *nVersion  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c9bb6-105">参数</span><span class="sxs-lookup"><span data-stu-id="c9bb6-105">Parameters</span></span>  
 `nVersion`  
 <span data-ttu-id="c9bb6-106">[out]指向代码的版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="c9bb6-106">[out] A pointer to the version number of the code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9bb6-107">备注</span><span class="sxs-lookup"><span data-stu-id="c9bb6-107">Remarks</span></span>  
 <span data-ttu-id="c9bb6-108">编辑并继续 (EnC) 操作执行的代码，每次都会递增的版本号。</span><span class="sxs-lookup"><span data-stu-id="c9bb6-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9bb6-109">惠?</span><span class="sxs-lookup"><span data-stu-id="c9bb6-109">Requirements</span></span>  
 <span data-ttu-id="c9bb6-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c9bb6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9bb6-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9bb6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9bb6-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9bb6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9bb6-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9bb6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9bb6-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9bb6-114">See Also</span></span>  
 
