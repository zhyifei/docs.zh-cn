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
ms.openlocfilehash: 291c8129a790c235ee6e7f163c49c4e1e726cce5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402707"
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="ff398-102">ICorDebugChain::GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="ff398-102">ICorDebugChain::GetThread Method</span></span>
<span data-ttu-id="ff398-103">获取此调用链的物理线程的一部分。</span><span class="sxs-lookup"><span data-stu-id="ff398-103">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff398-104">语法</span><span class="sxs-lookup"><span data-stu-id="ff398-104">Syntax</span></span>  
  
```  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff398-105">参数</span><span class="sxs-lookup"><span data-stu-id="ff398-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="ff398-106">[out]指向一个 ICorDebugThread 对象，表示物理线程的调用链是的一部分。</span><span class="sxs-lookup"><span data-stu-id="ff398-106">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff398-107">要求</span><span class="sxs-lookup"><span data-stu-id="ff398-107">Requirements</span></span>  
 <span data-ttu-id="ff398-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ff398-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff398-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff398-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff398-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff398-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff398-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff398-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
