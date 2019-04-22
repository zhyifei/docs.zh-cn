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
ms.openlocfilehash: e33e9be112a6a10f89b88005496ce2e63dff2d54
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080678"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="ab208-102">ICorDebugStackWalk 接口</span><span class="sxs-lookup"><span data-stu-id="ab208-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="ab208-103">提供用于获取线程堆栈上的托管方法或帧的方法。</span><span class="sxs-lookup"><span data-stu-id="ab208-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ab208-104">方法</span><span class="sxs-lookup"><span data-stu-id="ab208-104">Methods</span></span>  
  
|<span data-ttu-id="ab208-105">方法</span><span class="sxs-lookup"><span data-stu-id="ab208-105">Method</span></span>|<span data-ttu-id="ab208-106">描述</span><span class="sxs-lookup"><span data-stu-id="ab208-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ab208-107">GetContext 方法</span><span class="sxs-lookup"><span data-stu-id="ab208-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="ab208-108">返回的上下文中的当前帧`ICorDebugStackWalk`对象。</span><span class="sxs-lookup"><span data-stu-id="ab208-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="ab208-109">SetContext 方法</span><span class="sxs-lookup"><span data-stu-id="ab208-109">SetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="ab208-110">集`ICorDebugStackWalk`到有效的线程的上下文对象的当前上下文。</span><span class="sxs-lookup"><span data-stu-id="ab208-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="ab208-111">Next 方法</span><span class="sxs-lookup"><span data-stu-id="ab208-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|<span data-ttu-id="ab208-112">将移动`ICorDebugStackWalk`到下一个帧的对象。</span><span class="sxs-lookup"><span data-stu-id="ab208-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="ab208-113">GetFrame 方法</span><span class="sxs-lookup"><span data-stu-id="ab208-113">GetFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|<span data-ttu-id="ab208-114">获取当前帧中`ICorDebugStackWalk`对象。</span><span class="sxs-lookup"><span data-stu-id="ab208-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab208-115">备注</span><span class="sxs-lookup"><span data-stu-id="ab208-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab208-116">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="ab208-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab208-117">要求</span><span class="sxs-lookup"><span data-stu-id="ab208-117">Requirements</span></span>  
 <span data-ttu-id="ab208-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ab208-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab208-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab208-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab208-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab208-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab208-121">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab208-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab208-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab208-122">See also</span></span>

- [<span data-ttu-id="ab208-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="ab208-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ab208-124">调试</span><span class="sxs-lookup"><span data-stu-id="ab208-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
