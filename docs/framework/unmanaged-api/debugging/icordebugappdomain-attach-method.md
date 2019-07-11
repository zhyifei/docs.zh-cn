---
title: ICorDebugAppDomain::Attach 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d30b6cb083cc2f92bcbe089bf8e990fedd8e8f7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738090"
---
# <a name="icordebugappdomainattach-method"></a><span data-ttu-id="6e494-102">ICorDebugAppDomain::Attach 方法</span><span class="sxs-lookup"><span data-stu-id="6e494-102">ICorDebugAppDomain::Attach Method</span></span>
<span data-ttu-id="6e494-103">将调试器附加到应用程序域。</span><span class="sxs-lookup"><span data-stu-id="6e494-103">Attaches the debugger to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e494-104">语法</span><span class="sxs-lookup"><span data-stu-id="6e494-104">Syntax</span></span>  
  
```cpp  
HRESULT Attach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="6e494-105">备注</span><span class="sxs-lookup"><span data-stu-id="6e494-105">Remarks</span></span>  
 <span data-ttu-id="6e494-106">调试器必须附加到应用程序域才能接收事件，并以启用调试的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="6e494-106">The debugger must be attached to the application domain to receive events and to enable debugging of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e494-107">要求</span><span class="sxs-lookup"><span data-stu-id="6e494-107">Requirements</span></span>  
 <span data-ttu-id="6e494-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6e494-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e494-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e494-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e494-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e494-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e494-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e494-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
