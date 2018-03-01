---
title: "ICorDebugAppDomain::Attach 方法"
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
- ICorDebugAppDomain.Attach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::Attach
helpviewer_keywords:
- ICorDebugAppDomain::Attach method [.NET Framework debugging]
- Attach method [.NET Framework debugging]
ms.assetid: 0358b84a-4236-4c34-945b-4babff7df570
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7ba725cfe4aabab14de4b64297a038bf0b0ccec0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomainattach-method"></a><span data-ttu-id="23117-102">ICorDebugAppDomain::Attach 方法</span><span class="sxs-lookup"><span data-stu-id="23117-102">ICorDebugAppDomain::Attach Method</span></span>
<span data-ttu-id="23117-103">将调试器附加到应用程序域。</span><span class="sxs-lookup"><span data-stu-id="23117-103">Attaches the debugger to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23117-104">语法</span><span class="sxs-lookup"><span data-stu-id="23117-104">Syntax</span></span>  
  
```  
HRESULT Attach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="23117-105">备注</span><span class="sxs-lookup"><span data-stu-id="23117-105">Remarks</span></span>  
 <span data-ttu-id="23117-106">调试器必须附加到应用程序域才能接收事件，并启用调试的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="23117-106">The debugger must be attached to the application domain to receive events and to enable debugging of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23117-107">惠?</span><span class="sxs-lookup"><span data-stu-id="23117-107">Requirements</span></span>  
 <span data-ttu-id="23117-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="23117-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23117-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23117-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23117-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23117-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23117-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23117-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
