---
title: "ICorDebugBreakpoint::Activate 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBreakpoint.Activate
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBreakpoint::Activate
helpviewer_keywords:
- ICorDebugBreakpoint::Activate method [.NET Framework debugging]
- Activate method [.NET Framework debugging]
ms.assetid: e30c29f7-3f19-4081-b572-a731aa14cd44
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ef0880c40cb09b836938f253447f5ffeaaec207b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugbreakpointactivate-method"></a><span data-ttu-id="a768f-102">ICorDebugBreakpoint::Activate 方法</span><span class="sxs-lookup"><span data-stu-id="a768f-102">ICorDebugBreakpoint::Activate Method</span></span>
<span data-ttu-id="a768f-103">设置此活动的状态`ICorDebugBreakpoint`。</span><span class="sxs-lookup"><span data-stu-id="a768f-103">Sets the active state of this `ICorDebugBreakpoint`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a768f-104">语法</span><span class="sxs-lookup"><span data-stu-id="a768f-104">Syntax</span></span>  
  
```  
HRESULT Activate (  
    [in] BOOL bActive  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a768f-105">参数</span><span class="sxs-lookup"><span data-stu-id="a768f-105">Parameters</span></span>  
 `bActive`  
 <span data-ttu-id="a768f-106">[in]将此值设置为`true`以指定的状态为活动状态; 否则，将此值设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="a768f-106">[in] Set this value to `true` to specify the state as active; otherwise, set this value to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a768f-107">惠?</span><span class="sxs-lookup"><span data-stu-id="a768f-107">Requirements</span></span>  
 <span data-ttu-id="a768f-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a768f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a768f-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a768f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a768f-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a768f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a768f-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a768f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
