---
title: ICorDebugChain::GetThread 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d05002ecdb903a1adfeea88930083ba472164324
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745634"
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="de9e4-102">ICorDebugChain::GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="de9e4-102">ICorDebugChain::GetThread Method</span></span>
<span data-ttu-id="de9e4-103">获取此调用链的物理线程的一部分。</span><span class="sxs-lookup"><span data-stu-id="de9e4-103">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de9e4-104">语法</span><span class="sxs-lookup"><span data-stu-id="de9e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de9e4-105">参数</span><span class="sxs-lookup"><span data-stu-id="de9e4-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="de9e4-106">[out]指向一个 ICorDebugThread 对象，表示物理线程的此调用链是的一部分。</span><span class="sxs-lookup"><span data-stu-id="de9e4-106">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de9e4-107">要求</span><span class="sxs-lookup"><span data-stu-id="de9e4-107">Requirements</span></span>  
 <span data-ttu-id="de9e4-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="de9e4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de9e4-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de9e4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de9e4-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de9e4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de9e4-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de9e4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
