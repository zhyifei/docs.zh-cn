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
ms.openlocfilehash: 5f71dfcdffaaa683ca4f2abebaa99115ef90e0ff
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378909"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="a0db0-102">ICorDebugStackWalk 接口</span><span class="sxs-lookup"><span data-stu-id="a0db0-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="a0db0-103">提供用于获取线程堆栈上的托管方法或帧的方法。</span><span class="sxs-lookup"><span data-stu-id="a0db0-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0db0-104">方法</span><span class="sxs-lookup"><span data-stu-id="a0db0-104">Methods</span></span>  
  
|<span data-ttu-id="a0db0-105">方法</span><span class="sxs-lookup"><span data-stu-id="a0db0-105">Method</span></span>|<span data-ttu-id="a0db0-106">描述</span><span class="sxs-lookup"><span data-stu-id="a0db0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a0db0-107">GetContext 方法</span><span class="sxs-lookup"><span data-stu-id="a0db0-107">GetContext Method</span></span>](icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="a0db0-108">返回对象中当前帧的上下文 `ICorDebugStackWalk` 。</span><span class="sxs-lookup"><span data-stu-id="a0db0-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="a0db0-109">SetContext 方法</span><span class="sxs-lookup"><span data-stu-id="a0db0-109">SetContext Method</span></span>](icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="a0db0-110">将 `ICorDebugStackWalk` 对象的当前上下文设置为线程的有效上下文。</span><span class="sxs-lookup"><span data-stu-id="a0db0-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="a0db0-111">Next 方法</span><span class="sxs-lookup"><span data-stu-id="a0db0-111">Next Method</span></span>](icordebugstackwalk-next-method.md)|<span data-ttu-id="a0db0-112">将 `ICorDebugStackWalk` 对象移动到下一帧。</span><span class="sxs-lookup"><span data-stu-id="a0db0-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="a0db0-113">GetFrame 方法</span><span class="sxs-lookup"><span data-stu-id="a0db0-113">GetFrame Method</span></span>](icordebugstackwalk-getframe-method.md)|<span data-ttu-id="a0db0-114">获取对象中的当前帧 `ICorDebugStackWalk` 。</span><span class="sxs-lookup"><span data-stu-id="a0db0-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0db0-115">备注</span><span class="sxs-lookup"><span data-stu-id="a0db0-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a0db0-116">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="a0db0-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0db0-117">要求</span><span class="sxs-lookup"><span data-stu-id="a0db0-117">Requirements</span></span>  
 <span data-ttu-id="a0db0-118">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a0db0-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0db0-119">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0db0-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0db0-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0db0-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0db0-121">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0db0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0db0-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0db0-122">See also</span></span>

- [<span data-ttu-id="a0db0-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="a0db0-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a0db0-124">调试</span><span class="sxs-lookup"><span data-stu-id="a0db0-124">Debugging</span></span>](index.md)
