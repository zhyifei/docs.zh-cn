---
title: "ICorDebugFunction2::GetJMCStatus 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction2.GetJMCStatus
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d877b534ca2501117153047858a1a1f2736bdd4f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="1165d-102">ICorDebugFunction2::GetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="1165d-102">ICorDebugFunction2::GetJMCStatus Method</span></span>
<span data-ttu-id="1165d-103">获取一个值，该值指示是否将用此 ICorDebugFunction2 对象表示的函数标记为用户代码。</span><span class="sxs-lookup"><span data-stu-id="1165d-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1165d-104">语法</span><span class="sxs-lookup"><span data-stu-id="1165d-104">Syntax</span></span>  
  
```  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1165d-105">参数</span><span class="sxs-lookup"><span data-stu-id="1165d-105">Parameters</span></span>  
 `pbIsJustMyCode`  
 <span data-ttu-id="1165d-106">[out]一个布尔值，是一个指向`true`，如果此函数标记为用户代码; 否则，值为`false`。</span><span class="sxs-lookup"><span data-stu-id="1165d-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1165d-107">备注</span><span class="sxs-lookup"><span data-stu-id="1165d-107">Remarks</span></span>  
 <span data-ttu-id="1165d-108">如果该函数表示由此`ICorDebugFunction2`无法调试`pbIsJustMyCode`将始终为`false`。</span><span class="sxs-lookup"><span data-stu-id="1165d-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1165d-109">惠?</span><span class="sxs-lookup"><span data-stu-id="1165d-109">Requirements</span></span>  
 <span data-ttu-id="1165d-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1165d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1165d-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1165d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1165d-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1165d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1165d-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1165d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
