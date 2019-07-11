---
title: ICorDebugProcess::ThreadForFiberCookie 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ThreadForFiberCookie
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ThreadForFiberCookie
helpviewer_keywords:
- ICorDebugProcess::ThreadForFiberCookie method [.NET Framework debugging]
- ThreadForFiberCookie method [.NET Framework debugging]
ms.assetid: afe4e97f-bffc-47e1-adad-d6e842487f35
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f631be9462a569110e08fdb58d2609b0894f8d68
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737025"
---
# <a name="icordebugprocessthreadforfibercookie-method"></a><span data-ttu-id="f1e43-102">ICorDebugProcess::ThreadForFiberCookie 方法</span><span class="sxs-lookup"><span data-stu-id="f1e43-102">ICorDebugProcess::ThreadForFiberCookie Method</span></span>
<span data-ttu-id="f1e43-103">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="f1e43-103">This method is not implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1e43-104">语法</span><span class="sxs-lookup"><span data-stu-id="f1e43-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadForFiberCookie (  
    [in] DWORD fiberCookie,  
    [out] ICorDebugThread **ppThread  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="f1e43-105">要求</span><span class="sxs-lookup"><span data-stu-id="f1e43-105">Requirements</span></span>  
 <span data-ttu-id="f1e43-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f1e43-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1e43-107">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1e43-107">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1e43-108">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1e43-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1e43-109">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1e43-109">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
