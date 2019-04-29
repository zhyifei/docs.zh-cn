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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 724db50285532c20132fbfd5262df26227db6742
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782663"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="78c29-102">ICorDebugStackWalk::Next 方法</span><span class="sxs-lookup"><span data-stu-id="78c29-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="78c29-103">将移动[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)到下一个帧的对象。</span><span class="sxs-lookup"><span data-stu-id="78c29-103">Moves the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78c29-104">语法</span><span class="sxs-lookup"><span data-stu-id="78c29-104">Syntax</span></span>  
  
```  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="78c29-105">返回值</span><span class="sxs-lookup"><span data-stu-id="78c29-105">Return Value</span></span>  
 <span data-ttu-id="78c29-106">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="78c29-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="78c29-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="78c29-107">HRESULT</span></span>|<span data-ttu-id="78c29-108">描述</span><span class="sxs-lookup"><span data-stu-id="78c29-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="78c29-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="78c29-109">S_OK</span></span>|<span data-ttu-id="78c29-110">在运行时成功展开至下一帧 （请参阅备注）。</span><span class="sxs-lookup"><span data-stu-id="78c29-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="78c29-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="78c29-111">E_FAIL</span></span>|<span data-ttu-id="78c29-112">`ICorDebugStackWalk`不为高级对象。</span><span class="sxs-lookup"><span data-stu-id="78c29-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="78c29-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="78c29-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="78c29-114">由于此展开已达到堆栈的末尾。</span><span class="sxs-lookup"><span data-stu-id="78c29-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="78c29-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="78c29-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="78c29-116">帧指针已末尾的堆栈;因此，可以不访问任何其他帧。</span><span class="sxs-lookup"><span data-stu-id="78c29-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="78c29-117">Exceptions</span><span class="sxs-lookup"><span data-stu-id="78c29-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78c29-118">备注</span><span class="sxs-lookup"><span data-stu-id="78c29-118">Remarks</span></span>  
 <span data-ttu-id="78c29-119">`Next`方法的改进`ICorDebugStackWalk`仅当运行时可展开当前帧对象传递给调用的帧。</span><span class="sxs-lookup"><span data-stu-id="78c29-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="78c29-120">否则，对象前移至下一个运行时能够展开的帧。</span><span class="sxs-lookup"><span data-stu-id="78c29-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78c29-121">要求</span><span class="sxs-lookup"><span data-stu-id="78c29-121">Requirements</span></span>  
 <span data-ttu-id="78c29-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="78c29-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78c29-123">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="78c29-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78c29-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78c29-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78c29-125">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78c29-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78c29-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="78c29-126">See also</span></span>

- [<span data-ttu-id="78c29-127">ICorDebugStackWalk 接口</span><span class="sxs-lookup"><span data-stu-id="78c29-127">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)
- [<span data-ttu-id="78c29-128">调试接口</span><span class="sxs-lookup"><span data-stu-id="78c29-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="78c29-129">调试</span><span class="sxs-lookup"><span data-stu-id="78c29-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
