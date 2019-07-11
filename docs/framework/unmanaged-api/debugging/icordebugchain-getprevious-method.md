---
title: ICorDebugChain::GetPrevious 方法
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetPrevious
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetPrevious
helpviewer_keywords:
- ICorDebugChain::GetPrevious method [.NET Framework debugging]
- GetPrevious method [.NET Framework debugging]
ms.assetid: 58eed4c8-d80c-4c6a-a875-967a90dd926c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31c795c2fbbfdc45b6e1aac6684f730f55fc106a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746416"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="fcfb5-102">ICorDebugChain::GetPrevious 方法</span><span class="sxs-lookup"><span data-stu-id="fcfb5-102">ICorDebugChain::GetPrevious Method</span></span>
<span data-ttu-id="fcfb5-103">获取线程的上一帧链。</span><span class="sxs-lookup"><span data-stu-id="fcfb5-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcfb5-104">语法</span><span class="sxs-lookup"><span data-stu-id="fcfb5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcfb5-105">参数</span><span class="sxs-lookup"><span data-stu-id="fcfb5-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="fcfb5-106">[out]指向表示此线程的帧的上一个链的 ICorDebugChain 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="fcfb5-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="fcfb5-107">如果此证书链的第一个链`ppChain`为 null。</span><span class="sxs-lookup"><span data-stu-id="fcfb5-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcfb5-108">要求</span><span class="sxs-lookup"><span data-stu-id="fcfb5-108">Requirements</span></span>  
 <span data-ttu-id="fcfb5-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fcfb5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcfb5-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fcfb5-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fcfb5-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcfb5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcfb5-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcfb5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
