---
title: "CorDebugThreadState 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugThreadState
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugThreadState
helpviewer_keywords: CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a5363282f2efed003238014390f50c448c529ce2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="e58a3-102">CorDebugThreadState 枚举</span><span class="sxs-lookup"><span data-stu-id="e58a3-102">CorDebugThreadState Enumeration</span></span>
<span data-ttu-id="e58a3-103">指定用于调试的线程的状态。</span><span class="sxs-lookup"><span data-stu-id="e58a3-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e58a3-104">语法</span><span class="sxs-lookup"><span data-stu-id="e58a3-104">Syntax</span></span>  
  
```  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="e58a3-105">成员</span><span class="sxs-lookup"><span data-stu-id="e58a3-105">Members</span></span>  
  
|<span data-ttu-id="e58a3-106">成员</span><span class="sxs-lookup"><span data-stu-id="e58a3-106">Member</span></span>|<span data-ttu-id="e58a3-107">描述</span><span class="sxs-lookup"><span data-stu-id="e58a3-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="e58a3-108">线程自由运行，除非调试事件发生。</span><span class="sxs-lookup"><span data-stu-id="e58a3-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="e58a3-109">线程无法运行。</span><span class="sxs-lookup"><span data-stu-id="e58a3-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e58a3-110">备注</span><span class="sxs-lookup"><span data-stu-id="e58a3-110">Remarks</span></span>  
 <span data-ttu-id="e58a3-111">调试器使用`CorDebugThreadState`枚举，以控制线程的执行。</span><span class="sxs-lookup"><span data-stu-id="e58a3-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="e58a3-112">可以通过使用设置线程的状态[icordebugthread:: Setdebugstate](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)或[icordebugcontroller:: Setallthreadsdebugstate](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e58a3-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="e58a3-113">提供给回调[托管 API](../../../../docs/framework/unmanaged-api/hosting/index.md)实现消息泵处理，因此不需要中断的状态。</span><span class="sxs-lookup"><span data-stu-id="e58a3-113">A callback provided to the [hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e58a3-114">惠?</span><span class="sxs-lookup"><span data-stu-id="e58a3-114">Requirements</span></span>  
 <span data-ttu-id="e58a3-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e58a3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e58a3-116">**标头：** CorDebug.idl、 CorDegug.h</span><span class="sxs-lookup"><span data-stu-id="e58a3-116">**Header:** CorDebug.idl, CorDegug.h</span></span>  
  
 <span data-ttu-id="e58a3-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e58a3-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e58a3-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e58a3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e58a3-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="e58a3-119">See Also</span></span>  
 [<span data-ttu-id="e58a3-120">调试枚举</span><span class="sxs-lookup"><span data-stu-id="e58a3-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
