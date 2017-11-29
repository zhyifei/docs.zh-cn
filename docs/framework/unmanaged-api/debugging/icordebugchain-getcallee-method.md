---
title: "ICorDebugChain::GetCallee 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetCallee
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ed2bf8d8e91799fd0b01012d5d6e212d26a526be
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="9df9c-102">ICorDebugChain::GetCallee 方法</span><span class="sxs-lookup"><span data-stu-id="9df9c-102">ICorDebugChain::GetCallee Method</span></span>
<span data-ttu-id="9df9c-103">获取被调用链的链。</span><span class="sxs-lookup"><span data-stu-id="9df9c-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9df9c-104">语法</span><span class="sxs-lookup"><span data-stu-id="9df9c-104">Syntax</span></span>  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9df9c-105">参数</span><span class="sxs-lookup"><span data-stu-id="9df9c-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="9df9c-106">[out]指向一个表示调用的链的 ICorDebugChain 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="9df9c-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="9df9c-107">如果此证书链当前正在执行 （即，如果此证书链不等待调用链返回），`ppChain`将为 null。</span><span class="sxs-lookup"><span data-stu-id="9df9c-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9df9c-108">备注</span><span class="sxs-lookup"><span data-stu-id="9df9c-108">Remarks</span></span>  
 <span data-ttu-id="9df9c-109">此证书链将等待调用链返回，然后才会继续执行。</span><span class="sxs-lookup"><span data-stu-id="9df9c-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="9df9c-110">对于跨线程封送调用另一个线程可能会被调用的链。</span><span class="sxs-lookup"><span data-stu-id="9df9c-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9df9c-111">要求</span><span class="sxs-lookup"><span data-stu-id="9df9c-111">Requirements</span></span>  
 <span data-ttu-id="9df9c-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9df9c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9df9c-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9df9c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9df9c-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9df9c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9df9c-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9df9c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
