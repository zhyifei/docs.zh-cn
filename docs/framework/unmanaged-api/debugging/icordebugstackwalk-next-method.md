---
title: ICorDebugStackWalk::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::Next
helpviewer_keywords:
- ICorDebugStackWalk::Next method [.NET Framework debugging]
- Next method, ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 189c36be-028c-4fba-a002-5edfb8fcd07f
topic_type:
- apiref
ms.openlocfilehash: 8cebb66ecf298eaaca0e7af23a9b8c6a2932c23f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131818"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="204aa-102">ICorDebugStackWalk::Next 方法</span><span class="sxs-lookup"><span data-stu-id="204aa-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="204aa-103">将[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)对象移动到下一帧。</span><span class="sxs-lookup"><span data-stu-id="204aa-103">Moves the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="204aa-104">语法</span><span class="sxs-lookup"><span data-stu-id="204aa-104">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="204aa-105">返回值</span><span class="sxs-lookup"><span data-stu-id="204aa-105">Return Value</span></span>  
 <span data-ttu-id="204aa-106">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="204aa-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="204aa-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="204aa-107">HRESULT</span></span>|<span data-ttu-id="204aa-108">描述</span><span class="sxs-lookup"><span data-stu-id="204aa-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="204aa-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="204aa-109">S_OK</span></span>|<span data-ttu-id="204aa-110">运行时成功地展开为下一帧（请参阅 "备注"）。</span><span class="sxs-lookup"><span data-stu-id="204aa-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="204aa-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="204aa-111">E_FAIL</span></span>|<span data-ttu-id="204aa-112">`ICorDebugStackWalk` 对象不是高级对象。</span><span class="sxs-lookup"><span data-stu-id="204aa-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="204aa-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="204aa-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="204aa-114">由于此展开导致堆栈结束。</span><span class="sxs-lookup"><span data-stu-id="204aa-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="204aa-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="204aa-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="204aa-116">帧指针已位于堆栈末尾;因此，不能访问其他帧。</span><span class="sxs-lookup"><span data-stu-id="204aa-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="204aa-117">异常</span><span class="sxs-lookup"><span data-stu-id="204aa-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="204aa-118">备注</span><span class="sxs-lookup"><span data-stu-id="204aa-118">Remarks</span></span>  
 <span data-ttu-id="204aa-119">仅当运行时可以展开当前帧时，`Next` 方法才将 `ICorDebugStackWalk` 对象前进到调用帧。</span><span class="sxs-lookup"><span data-stu-id="204aa-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="204aa-120">否则，对象会前进到运行时能够展开的下一帧。</span><span class="sxs-lookup"><span data-stu-id="204aa-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="204aa-121">要求</span><span class="sxs-lookup"><span data-stu-id="204aa-121">Requirements</span></span>  
 <span data-ttu-id="204aa-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="204aa-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="204aa-123">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="204aa-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="204aa-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="204aa-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="204aa-125">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="204aa-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="204aa-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="204aa-126">See also</span></span>

- [<span data-ttu-id="204aa-127">ICorDebugStackWalk 接口</span><span class="sxs-lookup"><span data-stu-id="204aa-127">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)
- [<span data-ttu-id="204aa-128">调试接口</span><span class="sxs-lookup"><span data-stu-id="204aa-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="204aa-129">调试</span><span class="sxs-lookup"><span data-stu-id="204aa-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
