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
ms.openlocfilehash: fd65de77209f5a981c0a4c291f8573a61cf6335b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645274"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="5bde4-102">ICorDebugChain::GetCaller 方法</span><span class="sxs-lookup"><span data-stu-id="5bde4-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="5bde4-103">获取调用此链的链。</span><span class="sxs-lookup"><span data-stu-id="5bde4-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bde4-104">语法</span><span class="sxs-lookup"><span data-stu-id="5bde4-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bde4-105">参数</span><span class="sxs-lookup"><span data-stu-id="5bde4-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="5bde4-106">[out]指向一个 ICorDebugChain 对象，表示调用链的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="5bde4-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="5bde4-107">如果此链自然而然地调用 （就会是这种情况，如果此证书链或调试程序初始化的调用堆栈），`ppChain`将为 null。</span><span class="sxs-lookup"><span data-stu-id="5bde4-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bde4-108">备注</span><span class="sxs-lookup"><span data-stu-id="5bde4-108">Remarks</span></span>  
 <span data-ttu-id="5bde4-109">调用链可能在另一个线程，如果在调用已在线程之间封送。</span><span class="sxs-lookup"><span data-stu-id="5bde4-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bde4-110">要求</span><span class="sxs-lookup"><span data-stu-id="5bde4-110">Requirements</span></span>  
 <span data-ttu-id="5bde4-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5bde4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bde4-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5bde4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5bde4-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bde4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bde4-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bde4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
