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
ms.openlocfilehash: c7598a9d93631ca93187886fd8929ba10726dad7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124734"
---
# <a name="icordebugchaingetprevious-method"></a><span data-ttu-id="af6f9-102">ICorDebugChain::GetPrevious 方法</span><span class="sxs-lookup"><span data-stu-id="af6f9-102">ICorDebugChain::GetPrevious Method</span></span>
<span data-ttu-id="af6f9-103">获取线程的上一个帧链。</span><span class="sxs-lookup"><span data-stu-id="af6f9-103">Gets the previous chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af6f9-104">语法</span><span class="sxs-lookup"><span data-stu-id="af6f9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPrevious (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af6f9-105">参数</span><span class="sxs-lookup"><span data-stu-id="af6f9-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="af6f9-106">弄指向 ICorDebugChain 对象的地址的指针，该对象表示此线程的上一个帧链。</span><span class="sxs-lookup"><span data-stu-id="af6f9-106">[out] A pointer to the address of an ICorDebugChain object that represents the previous chain of frames for this thread.</span></span> <span data-ttu-id="af6f9-107">如果此链是第一个链，则 `ppChain` 为 null。</span><span class="sxs-lookup"><span data-stu-id="af6f9-107">If this chain is the first chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af6f9-108">要求</span><span class="sxs-lookup"><span data-stu-id="af6f9-108">Requirements</span></span>  
 <span data-ttu-id="af6f9-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="af6f9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af6f9-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af6f9-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af6f9-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af6f9-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af6f9-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af6f9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
