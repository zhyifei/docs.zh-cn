---
title: "ICorDebugStackWalk::Next 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStackWalk.Next Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStackWalk::Next
helpviewer_keywords:
- ICorDebugStackWalk::Next method [.NET Framework debugging]
- Next method, ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 189c36be-028c-4fba-a002-5edfb8fcd07f
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5a776f215d67c381a1c08416927cabd3ccb40afa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="360cd-102">ICorDebugStackWalk::Next 方法</span><span class="sxs-lookup"><span data-stu-id="360cd-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="360cd-103">将移动[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)到下一个帧的对象。</span><span class="sxs-lookup"><span data-stu-id="360cd-103">Moves the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="360cd-104">语法</span><span class="sxs-lookup"><span data-stu-id="360cd-104">Syntax</span></span>  
  
```  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="360cd-105">返回值</span><span class="sxs-lookup"><span data-stu-id="360cd-105">Return Value</span></span>  
 <span data-ttu-id="360cd-106">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="360cd-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="360cd-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="360cd-107">HRESULT</span></span>|<span data-ttu-id="360cd-108">描述</span><span class="sxs-lookup"><span data-stu-id="360cd-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="360cd-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="360cd-109">S_OK</span></span>|<span data-ttu-id="360cd-110">运行时成功地将展开到下一个帧 （请参阅备注）。</span><span class="sxs-lookup"><span data-stu-id="360cd-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="360cd-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="360cd-111">E_FAIL</span></span>|<span data-ttu-id="360cd-112">`ICorDebugStackWalk`不为高级对象。</span><span class="sxs-lookup"><span data-stu-id="360cd-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="360cd-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="360cd-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="360cd-114">由于此展开已达到堆栈的末尾。</span><span class="sxs-lookup"><span data-stu-id="360cd-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="360cd-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="360cd-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="360cd-116">帧指针是已在堆栈; 末尾因此，可以不访问任何其他帧。</span><span class="sxs-lookup"><span data-stu-id="360cd-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="360cd-117">异常</span><span class="sxs-lookup"><span data-stu-id="360cd-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="360cd-118">备注</span><span class="sxs-lookup"><span data-stu-id="360cd-118">Remarks</span></span>  
 <span data-ttu-id="360cd-119">`Next`方法的改进`ICorDebugStackWalk`对象到调用的帧，仅当运行时可以进行展开当前帧。</span><span class="sxs-lookup"><span data-stu-id="360cd-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="360cd-120">否则，该对象将前进到下一个帧以及运行时无法展开。</span><span class="sxs-lookup"><span data-stu-id="360cd-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="360cd-121">惠?</span><span class="sxs-lookup"><span data-stu-id="360cd-121">Requirements</span></span>  
 <span data-ttu-id="360cd-122">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="360cd-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="360cd-123">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="360cd-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="360cd-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="360cd-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="360cd-125">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="360cd-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="360cd-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="360cd-126">See Also</span></span>  
 [<span data-ttu-id="360cd-127">ICorDebugStackWalk 接口</span><span class="sxs-lookup"><span data-stu-id="360cd-127">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 [<span data-ttu-id="360cd-128">调试接口</span><span class="sxs-lookup"><span data-stu-id="360cd-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="360cd-129">调试</span><span class="sxs-lookup"><span data-stu-id="360cd-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
