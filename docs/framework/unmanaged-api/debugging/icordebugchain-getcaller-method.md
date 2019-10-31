---
title: ICorDebugChain::GetCaller 方法
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCaller
helpviewer_keywords:
- ICorDebugChain::GetCaller method [.NET Framework debugging]
- GetCaller method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: d0b8ab4b-d7d2-4fa0-945f-3d2b87e7e991
topic_type:
- apiref
ms.openlocfilehash: 5a07550d44857526e8ab4ded9f1827ef12e3bba4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192135"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="cbcb5-102">ICorDebugChain::GetCaller 方法</span><span class="sxs-lookup"><span data-stu-id="cbcb5-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="cbcb5-103">获取调用此链的链。</span><span class="sxs-lookup"><span data-stu-id="cbcb5-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbcb5-104">语法</span><span class="sxs-lookup"><span data-stu-id="cbcb5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbcb5-105">参数</span><span class="sxs-lookup"><span data-stu-id="cbcb5-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="cbcb5-106">弄指向表示调用链的 ICorDebugChain 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="cbcb5-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="cbcb5-107">如果此链是自发调用的（如果此链或调试器初始化了调用堆栈，就是这种情况），`ppChain` 将为 null。</span><span class="sxs-lookup"><span data-stu-id="cbcb5-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbcb5-108">备注</span><span class="sxs-lookup"><span data-stu-id="cbcb5-108">Remarks</span></span>  
 <span data-ttu-id="cbcb5-109">如果调用是在线程间封送的，则调用链可能位于不同的线程上。</span><span class="sxs-lookup"><span data-stu-id="cbcb5-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbcb5-110">要求</span><span class="sxs-lookup"><span data-stu-id="cbcb5-110">Requirements</span></span>  
 <span data-ttu-id="cbcb5-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cbcb5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbcb5-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cbcb5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbcb5-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbcb5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbcb5-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbcb5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
