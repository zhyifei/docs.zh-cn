---
title: "ICorDebugHeapValue3 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue3
helpviewer_keywords: ICorDebugHeapValue3 interface [.NET Framework debugging]
ms.assetid: 9c421bb0-e647-4b2d-a986-f3d578cc7f20
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5531689a3a4ba66fddfc98cadec7dc8d51c8629a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="6df6e-102">ICorDebugHeapValue3 接口</span><span class="sxs-lookup"><span data-stu-id="6df6e-102">ICorDebugHeapValue3 Interface</span></span>
<span data-ttu-id="6df6e-103">公开对象的监视器锁属性。</span><span class="sxs-lookup"><span data-stu-id="6df6e-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="6df6e-104">此接口扩展的 ICorDebugHeapValue 和 ICorDebugHeapValue2 接口。</span><span class="sxs-lookup"><span data-stu-id="6df6e-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6df6e-105">方法</span><span class="sxs-lookup"><span data-stu-id="6df6e-105">Methods</span></span>  
  
|<span data-ttu-id="6df6e-106">方法</span><span class="sxs-lookup"><span data-stu-id="6df6e-106">Method</span></span>|<span data-ttu-id="6df6e-107">描述</span><span class="sxs-lookup"><span data-stu-id="6df6e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6df6e-108">GetThreadOwningMonitorLock 方法</span><span class="sxs-lookup"><span data-stu-id="6df6e-108">GetThreadOwningMonitorLock Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="6df6e-109">返回拥有此对象的监视器锁的托管的线程。</span><span class="sxs-lookup"><span data-stu-id="6df6e-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="6df6e-110">GetMonitorEventWaitList 方法</span><span class="sxs-lookup"><span data-stu-id="6df6e-110">GetMonitorEventWaitList Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="6df6e-111">提供有关与监视器锁关联的事件将排队等待的线程的已排序的列表。</span><span class="sxs-lookup"><span data-stu-id="6df6e-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6df6e-112">备注</span><span class="sxs-lookup"><span data-stu-id="6df6e-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6df6e-113">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="6df6e-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6df6e-114">要求</span><span class="sxs-lookup"><span data-stu-id="6df6e-114">Requirements</span></span>  
 <span data-ttu-id="6df6e-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6df6e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6df6e-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6df6e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6df6e-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6df6e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6df6e-118">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6df6e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6df6e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6df6e-119">See Also</span></span>  
 [<span data-ttu-id="6df6e-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="6df6e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="6df6e-121">调试</span><span class="sxs-lookup"><span data-stu-id="6df6e-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
