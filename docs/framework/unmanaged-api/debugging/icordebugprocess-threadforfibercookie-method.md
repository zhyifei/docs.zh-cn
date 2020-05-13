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
ms.openlocfilehash: faaa118fa73a4c9b8750752d84a9dd980170ff66
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210444"
---
# <a name="icordebugprocessthreadforfibercookie-method"></a><span data-ttu-id="31cac-102">ICorDebugProcess::ThreadForFiberCookie 方法</span><span class="sxs-lookup"><span data-stu-id="31cac-102">ICorDebugProcess::ThreadForFiberCookie Method</span></span>
<span data-ttu-id="31cac-103">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="31cac-103">This method is not implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31cac-104">语法</span><span class="sxs-lookup"><span data-stu-id="31cac-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadForFiberCookie (  
    [in] DWORD fiberCookie,  
    [out] ICorDebugThread **ppThread  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="31cac-105">要求</span><span class="sxs-lookup"><span data-stu-id="31cac-105">Requirements</span></span>  
 <span data-ttu-id="31cac-106">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="31cac-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31cac-107">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31cac-107">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31cac-108">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31cac-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31cac-109">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31cac-109">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
