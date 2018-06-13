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
ms.openlocfilehash: f050a3d9d37e43713c40896fb162bcf9932c6512
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403365"
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="c4c9b-102">ICorDebugChain::GetCallee 方法</span><span class="sxs-lookup"><span data-stu-id="c4c9b-102">ICorDebugChain::GetCallee Method</span></span>
<span data-ttu-id="c4c9b-103">获取被调用链的链。</span><span class="sxs-lookup"><span data-stu-id="c4c9b-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4c9b-104">语法</span><span class="sxs-lookup"><span data-stu-id="c4c9b-104">Syntax</span></span>  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c4c9b-105">参数</span><span class="sxs-lookup"><span data-stu-id="c4c9b-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="c4c9b-106">[out]指向一个表示调用的链的 ICorDebugChain 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="c4c9b-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="c4c9b-107">如果此证书链当前正在执行 （即，如果此证书链不等待调用链返回），`ppChain`将为 null。</span><span class="sxs-lookup"><span data-stu-id="c4c9b-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4c9b-108">备注</span><span class="sxs-lookup"><span data-stu-id="c4c9b-108">Remarks</span></span>  
 <span data-ttu-id="c4c9b-109">此证书链将等待调用链返回，然后才会继续执行。</span><span class="sxs-lookup"><span data-stu-id="c4c9b-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="c4c9b-110">对于跨线程封送调用另一个线程可能会被调用的链。</span><span class="sxs-lookup"><span data-stu-id="c4c9b-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4c9b-111">要求</span><span class="sxs-lookup"><span data-stu-id="c4c9b-111">Requirements</span></span>  
 <span data-ttu-id="c4c9b-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c4c9b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4c9b-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4c9b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4c9b-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4c9b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4c9b-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4c9b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
