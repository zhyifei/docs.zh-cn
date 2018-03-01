---
title: "ICorDebugChain::EnumerateFrames 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d9df99c239568948c04f61ca4ec5e2b9207930f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="3206f-102">ICorDebugChain::EnumerateFrames 方法</span><span class="sxs-lookup"><span data-stu-id="3206f-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="3206f-103">获取一个枚举器包含的链中的所有托管的堆栈帧并从最新帧开始。</span><span class="sxs-lookup"><span data-stu-id="3206f-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3206f-104">语法</span><span class="sxs-lookup"><span data-stu-id="3206f-104">Syntax</span></span>  
  
```  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3206f-105">参数</span><span class="sxs-lookup"><span data-stu-id="3206f-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="3206f-106">[out]指向一个 ICorDebugFrameEnum 对象，它的堆栈帧的枚举器的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="3206f-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3206f-107">备注</span><span class="sxs-lookup"><span data-stu-id="3206f-107">Remarks</span></span>  
 <span data-ttu-id="3206f-108">链表示线程的物理调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="3206f-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="3206f-109">`EnumerateFrames`应该仅用于托管链的调用方法。</span><span class="sxs-lookup"><span data-stu-id="3206f-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="3206f-110">调试 API 不提供用于获取非托管链中包含的帧的方法。</span><span class="sxs-lookup"><span data-stu-id="3206f-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="3206f-111">调试器必须使用其他方法来获取此信息。</span><span class="sxs-lookup"><span data-stu-id="3206f-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3206f-112">惠?</span><span class="sxs-lookup"><span data-stu-id="3206f-112">Requirements</span></span>  
 <span data-ttu-id="3206f-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3206f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3206f-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3206f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3206f-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3206f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3206f-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3206f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
