---
title: ICorDebugStackWalk 接口
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06ce2da435df9458ca59d76fa426becbede2e619
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959679"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="2d884-102">ICorDebugStackWalk 接口</span><span class="sxs-lookup"><span data-stu-id="2d884-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="2d884-103">提供用于获取线程堆栈上的托管方法或帧的方法。</span><span class="sxs-lookup"><span data-stu-id="2d884-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2d884-104">方法</span><span class="sxs-lookup"><span data-stu-id="2d884-104">Methods</span></span>  
  
|<span data-ttu-id="2d884-105">方法</span><span class="sxs-lookup"><span data-stu-id="2d884-105">Method</span></span>|<span data-ttu-id="2d884-106">描述</span><span class="sxs-lookup"><span data-stu-id="2d884-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2d884-107">GetContext 方法</span><span class="sxs-lookup"><span data-stu-id="2d884-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="2d884-108">返回`ICorDebugStackWalk`对象中当前帧的上下文。</span><span class="sxs-lookup"><span data-stu-id="2d884-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="2d884-109">SetContext 方法</span><span class="sxs-lookup"><span data-stu-id="2d884-109">SetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="2d884-110">`ICorDebugStackWalk`将对象的当前上下文设置为线程的有效上下文。</span><span class="sxs-lookup"><span data-stu-id="2d884-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="2d884-111">Next 方法</span><span class="sxs-lookup"><span data-stu-id="2d884-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|<span data-ttu-id="2d884-112">`ICorDebugStackWalk`将对象移动到下一帧。</span><span class="sxs-lookup"><span data-stu-id="2d884-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="2d884-113">GetFrame 方法</span><span class="sxs-lookup"><span data-stu-id="2d884-113">GetFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|<span data-ttu-id="2d884-114">获取`ICorDebugStackWalk`对象中的当前帧。</span><span class="sxs-lookup"><span data-stu-id="2d884-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d884-115">备注</span><span class="sxs-lookup"><span data-stu-id="2d884-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d884-116">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="2d884-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d884-117">要求</span><span class="sxs-lookup"><span data-stu-id="2d884-117">Requirements</span></span>  
 <span data-ttu-id="2d884-118">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2d884-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d884-119">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="2d884-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d884-120">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d884-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d884-121">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d884-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d884-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d884-122">See also</span></span>

- [<span data-ttu-id="2d884-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="2d884-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2d884-124">调试</span><span class="sxs-lookup"><span data-stu-id="2d884-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
