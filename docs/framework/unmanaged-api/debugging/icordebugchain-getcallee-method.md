---
title: ICorDebugChain::GetCallee 方法
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79743b78ea3d19bab4756b580d2feddd07e0a23b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744981"
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="92ee5-102">ICorDebugChain::GetCallee 方法</span><span class="sxs-lookup"><span data-stu-id="92ee5-102">ICorDebugChain::GetCallee Method</span></span>
<span data-ttu-id="92ee5-103">获取此链调用链。</span><span class="sxs-lookup"><span data-stu-id="92ee5-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92ee5-104">语法</span><span class="sxs-lookup"><span data-stu-id="92ee5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92ee5-105">参数</span><span class="sxs-lookup"><span data-stu-id="92ee5-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="92ee5-106">[out]指向一个 ICorDebugChain 对象，表示被调用的链的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="92ee5-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="92ee5-107">如果当前正在执行此链，（即，如果此证书链不等待被调用链返回），`ppChain`将为 null。</span><span class="sxs-lookup"><span data-stu-id="92ee5-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92ee5-108">备注</span><span class="sxs-lookup"><span data-stu-id="92ee5-108">Remarks</span></span>  
 <span data-ttu-id="92ee5-109">此链将等待被调用链返回，然后再继续执行。</span><span class="sxs-lookup"><span data-stu-id="92ee5-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="92ee5-110">调用的链可能对于跨线程封送调用另一个线程上。</span><span class="sxs-lookup"><span data-stu-id="92ee5-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92ee5-111">要求</span><span class="sxs-lookup"><span data-stu-id="92ee5-111">Requirements</span></span>  
 <span data-ttu-id="92ee5-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="92ee5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92ee5-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92ee5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92ee5-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92ee5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92ee5-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92ee5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
