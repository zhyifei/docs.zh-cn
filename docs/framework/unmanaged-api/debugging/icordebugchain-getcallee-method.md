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
ms.openlocfilehash: ed5a7657affde335acf79952d77bbdb7ac42c7a0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490458"
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="09a2e-102">ICorDebugChain::GetCallee 方法</span><span class="sxs-lookup"><span data-stu-id="09a2e-102">ICorDebugChain::GetCallee Method</span></span>
<span data-ttu-id="09a2e-103">获取此链调用链。</span><span class="sxs-lookup"><span data-stu-id="09a2e-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09a2e-104">语法</span><span class="sxs-lookup"><span data-stu-id="09a2e-104">Syntax</span></span>  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09a2e-105">参数</span><span class="sxs-lookup"><span data-stu-id="09a2e-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="09a2e-106">[out]指向一个 ICorDebugChain 对象，表示被调用的链的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="09a2e-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="09a2e-107">如果当前正在执行此链，（即，如果此证书链不等待被调用链返回），`ppChain`将为 null。</span><span class="sxs-lookup"><span data-stu-id="09a2e-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09a2e-108">备注</span><span class="sxs-lookup"><span data-stu-id="09a2e-108">Remarks</span></span>  
 <span data-ttu-id="09a2e-109">此链将等待被调用链返回，然后再继续执行。</span><span class="sxs-lookup"><span data-stu-id="09a2e-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="09a2e-110">调用的链可能对于跨线程封送调用另一个线程上。</span><span class="sxs-lookup"><span data-stu-id="09a2e-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09a2e-111">要求</span><span class="sxs-lookup"><span data-stu-id="09a2e-111">Requirements</span></span>  
 <span data-ttu-id="09a2e-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="09a2e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09a2e-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09a2e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09a2e-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09a2e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09a2e-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09a2e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
