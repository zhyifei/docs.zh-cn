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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9622716e3a2cca7e3af0b1e1b134458a50ad1bec
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962979"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="ad832-102">ICorDebugThread3 接口</span><span class="sxs-lookup"><span data-stu-id="ad832-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="ad832-103">提供[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)和相应接口的入口点。</span><span class="sxs-lookup"><span data-stu-id="ad832-103">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ad832-104">方法</span><span class="sxs-lookup"><span data-stu-id="ad832-104">Methods</span></span>  
  
|<span data-ttu-id="ad832-105">方法</span><span class="sxs-lookup"><span data-stu-id="ad832-105">Method</span></span>|<span data-ttu-id="ad832-106">描述</span><span class="sxs-lookup"><span data-stu-id="ad832-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ad832-107">CreateStackWalk 方法</span><span class="sxs-lookup"><span data-stu-id="ad832-107">CreateStackWalk Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="ad832-108">为要展开其堆栈的线程创建[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="ad832-108">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="ad832-109">GetActiveInternalFrames 方法</span><span class="sxs-lookup"><span data-stu-id="ad832-109">GetActiveInternalFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="ad832-110">返回堆栈上的内部帧 ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)对象) 的数组。</span><span class="sxs-lookup"><span data-stu-id="ad832-110">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad832-111">备注</span><span class="sxs-lookup"><span data-stu-id="ad832-111">Remarks</span></span>  
 <span data-ttu-id="ad832-112">`ICorDebugThread3`是 ICorDebugThread 接口的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="ad832-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ad832-113">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="ad832-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad832-114">要求</span><span class="sxs-lookup"><span data-stu-id="ad832-114">Requirements</span></span>  
 <span data-ttu-id="ad832-115">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ad832-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad832-116">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="ad832-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad832-117">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad832-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad832-118">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad832-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad832-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad832-119">See also</span></span>

- [<span data-ttu-id="ad832-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="ad832-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ad832-121">调试</span><span class="sxs-lookup"><span data-stu-id="ad832-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
