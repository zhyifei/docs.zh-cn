---
title: ICorDebugThread3 接口
ms.date: 03/30/2017
api_name:
- ICorDebugThread3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3
helpviewer_keywords:
- ICorDebugThread3 interface [.NET Framework debugging]
ms.assetid: eb2860ef-06cb-4968-a6c3-6d048ecda2a4
topic_type:
- apiref
ms.openlocfilehash: 7cddf860f044e8493a0fdf6023b2853ac16c5b14
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137505"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="50acf-102">ICorDebugThread3 接口</span><span class="sxs-lookup"><span data-stu-id="50acf-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="50acf-103">提供[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)和相应接口的入口点。</span><span class="sxs-lookup"><span data-stu-id="50acf-103">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50acf-104">方法</span><span class="sxs-lookup"><span data-stu-id="50acf-104">Methods</span></span>  
  
|<span data-ttu-id="50acf-105">方法</span><span class="sxs-lookup"><span data-stu-id="50acf-105">Method</span></span>|<span data-ttu-id="50acf-106">描述</span><span class="sxs-lookup"><span data-stu-id="50acf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50acf-107">CreateStackWalk 方法</span><span class="sxs-lookup"><span data-stu-id="50acf-107">CreateStackWalk Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="50acf-108">为要展开其堆栈的线程创建[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="50acf-108">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="50acf-109">GetActiveInternalFrames 方法</span><span class="sxs-lookup"><span data-stu-id="50acf-109">GetActiveInternalFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="50acf-110">返回堆栈上的内部帧（[ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)对象）的数组。</span><span class="sxs-lookup"><span data-stu-id="50acf-110">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50acf-111">备注</span><span class="sxs-lookup"><span data-stu-id="50acf-111">Remarks</span></span>  
 <span data-ttu-id="50acf-112">`ICorDebugThread3` 是 ICorDebugThread 接口的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="50acf-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="50acf-113">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="50acf-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50acf-114">要求</span><span class="sxs-lookup"><span data-stu-id="50acf-114">Requirements</span></span>  
 <span data-ttu-id="50acf-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="50acf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50acf-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50acf-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50acf-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50acf-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50acf-118">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50acf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50acf-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="50acf-119">See also</span></span>

- [<span data-ttu-id="50acf-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="50acf-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="50acf-121">调试</span><span class="sxs-lookup"><span data-stu-id="50acf-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
