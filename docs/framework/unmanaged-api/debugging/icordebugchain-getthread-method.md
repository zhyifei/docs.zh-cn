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
ms.openlocfilehash: 4ab2b584b4a3e9bef17110f3084dc93efb2e5167
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989360"
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="31f07-102">ICorDebugChain::GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="31f07-102">ICorDebugChain::GetThread Method</span></span>
<span data-ttu-id="31f07-103">获取此调用链的物理线程的一部分。</span><span class="sxs-lookup"><span data-stu-id="31f07-103">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31f07-104">语法</span><span class="sxs-lookup"><span data-stu-id="31f07-104">Syntax</span></span>  
  
```  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31f07-105">参数</span><span class="sxs-lookup"><span data-stu-id="31f07-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="31f07-106">[out]指向一个 ICorDebugThread 对象，表示物理线程的此调用链是的一部分。</span><span class="sxs-lookup"><span data-stu-id="31f07-106">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31f07-107">要求</span><span class="sxs-lookup"><span data-stu-id="31f07-107">Requirements</span></span>  
 <span data-ttu-id="31f07-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="31f07-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31f07-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31f07-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31f07-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31f07-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31f07-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31f07-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
