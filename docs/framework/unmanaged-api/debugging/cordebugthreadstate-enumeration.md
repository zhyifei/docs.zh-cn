---
title: CorDebugThreadState 枚举
ms.date: 03/30/2017
api_name:
- CorDebugThreadState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugThreadState
helpviewer_keywords:
- CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type:
- apiref
ms.openlocfilehash: 69a8aabd1d79bb9bb4248259c99124ce50677600
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789243"
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="c1967-102">CorDebugThreadState 枚举</span><span class="sxs-lookup"><span data-stu-id="c1967-102">CorDebugThreadState Enumeration</span></span>
<span data-ttu-id="c1967-103">指定用于调试的线程的状态。</span><span class="sxs-lookup"><span data-stu-id="c1967-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1967-104">语法</span><span class="sxs-lookup"><span data-stu-id="c1967-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="c1967-105">Members</span><span class="sxs-lookup"><span data-stu-id="c1967-105">Members</span></span>  
  
|<span data-ttu-id="c1967-106">成员</span><span class="sxs-lookup"><span data-stu-id="c1967-106">Member</span></span>|<span data-ttu-id="c1967-107">描述</span><span class="sxs-lookup"><span data-stu-id="c1967-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="c1967-108">线程自由运行，除非调试事件发生。</span><span class="sxs-lookup"><span data-stu-id="c1967-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="c1967-109">线程无法运行。</span><span class="sxs-lookup"><span data-stu-id="c1967-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1967-110">备注</span><span class="sxs-lookup"><span data-stu-id="c1967-110">Remarks</span></span>  
 <span data-ttu-id="c1967-111">调试器使用 `CorDebugThreadState` 枚举来控制线程的执行。</span><span class="sxs-lookup"><span data-stu-id="c1967-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="c1967-112">可以使用[ICorDebugThread：： SetDebugState](icordebugthread-setdebugstate-method.md)或[ICorDebugController：： SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md)方法设置线程的状态。</span><span class="sxs-lookup"><span data-stu-id="c1967-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="c1967-113">向[宿主 API](../../../../docs/framework/unmanaged-api/hosting/index.md)提供的回调启用消息泵，因此不需要中断的状态。</span><span class="sxs-lookup"><span data-stu-id="c1967-113">A callback provided to the [hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1967-114">需求</span><span class="sxs-lookup"><span data-stu-id="c1967-114">Requirements</span></span>  
 <span data-ttu-id="c1967-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c1967-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1967-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c1967-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1967-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1967-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1967-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1967-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1967-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1967-119">See also</span></span>

- [<span data-ttu-id="c1967-120">调试枚举</span><span class="sxs-lookup"><span data-stu-id="c1967-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
