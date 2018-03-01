---
title: "ICorDebugChain::GetThread 方法"
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
- ICorDebugChain.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugChain interface [.NET Framework debugging]
- ICorDebugChain::GetThread method [.NET Framework debugging]
ms.assetid: b3390319-6366-418c-ba80-b552ac4dfc1e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 560f92eaed2d3482ca24d67810a3de6bc6f6fe31
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="0191f-102">ICorDebugChain::GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="0191f-102">ICorDebugChain::GetThread Method</span></span>
<span data-ttu-id="0191f-103">获取此调用链的物理线程的一部分。</span><span class="sxs-lookup"><span data-stu-id="0191f-103">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0191f-104">语法</span><span class="sxs-lookup"><span data-stu-id="0191f-104">Syntax</span></span>  
  
```  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0191f-105">参数</span><span class="sxs-lookup"><span data-stu-id="0191f-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="0191f-106">[out]指向一个 ICorDebugThread 对象，表示物理线程的调用链是的一部分。</span><span class="sxs-lookup"><span data-stu-id="0191f-106">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0191f-107">惠?</span><span class="sxs-lookup"><span data-stu-id="0191f-107">Requirements</span></span>  
 <span data-ttu-id="0191f-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0191f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0191f-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0191f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0191f-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0191f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0191f-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0191f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
