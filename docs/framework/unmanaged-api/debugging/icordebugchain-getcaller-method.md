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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a0b5d702e9718ce6ac537beae67fc190b152b9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405138"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="9ddea-102">ICorDebugChain::GetCaller 方法</span><span class="sxs-lookup"><span data-stu-id="9ddea-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="9ddea-103">获取调用链的链。</span><span class="sxs-lookup"><span data-stu-id="9ddea-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ddea-104">语法</span><span class="sxs-lookup"><span data-stu-id="9ddea-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ddea-105">参数</span><span class="sxs-lookup"><span data-stu-id="9ddea-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="9ddea-106">[out]指向一个表示调用链的 ICorDebugChain 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="9ddea-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="9ddea-107">如果此证书链自然而然地调用 （如如果此证书链或调试器初始化调用堆栈，则会出现此情况），`ppChain`将为 null。</span><span class="sxs-lookup"><span data-stu-id="9ddea-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ddea-108">备注</span><span class="sxs-lookup"><span data-stu-id="9ddea-108">Remarks</span></span>  
 <span data-ttu-id="9ddea-109">如果调用已跨线程封送处理，则在另一个线程，可能会调用链。</span><span class="sxs-lookup"><span data-stu-id="9ddea-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ddea-110">要求</span><span class="sxs-lookup"><span data-stu-id="9ddea-110">Requirements</span></span>  
 <span data-ttu-id="9ddea-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9ddea-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ddea-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ddea-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ddea-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ddea-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ddea-114">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ddea-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
