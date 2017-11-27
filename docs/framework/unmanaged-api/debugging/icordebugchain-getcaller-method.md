---
title: "ICorDebugChain::GetCaller 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetCaller
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetCaller
helpviewer_keywords:
- ICorDebugChain::GetCaller method [.NET Framework debugging]
- GetCaller method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: d0b8ab4b-d7d2-4fa0-945f-3d2b87e7e991
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c714f321dc3c400b980d2d95b4655786fea9543b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="ba737-102">ICorDebugChain::GetCaller 方法</span><span class="sxs-lookup"><span data-stu-id="ba737-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="ba737-103">获取调用链的链。</span><span class="sxs-lookup"><span data-stu-id="ba737-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba737-104">语法</span><span class="sxs-lookup"><span data-stu-id="ba737-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ba737-105">参数</span><span class="sxs-lookup"><span data-stu-id="ba737-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="ba737-106">[out]指向一个表示调用链的 ICorDebugChain 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="ba737-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="ba737-107">如果此证书链自然而然地调用 （如如果此证书链或调试器初始化调用堆栈，则会出现此情况），`ppChain`将为 null。</span><span class="sxs-lookup"><span data-stu-id="ba737-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba737-108">备注</span><span class="sxs-lookup"><span data-stu-id="ba737-108">Remarks</span></span>  
 <span data-ttu-id="ba737-109">如果调用已跨线程封送处理，则在另一个线程，可能会调用链。</span><span class="sxs-lookup"><span data-stu-id="ba737-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba737-110">要求</span><span class="sxs-lookup"><span data-stu-id="ba737-110">Requirements</span></span>  
 <span data-ttu-id="ba737-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ba737-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba737-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba737-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba737-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba737-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba737-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba737-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
