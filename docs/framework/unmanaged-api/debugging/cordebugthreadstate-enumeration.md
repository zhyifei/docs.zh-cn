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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: efb7f5b8e63742471123a0e0a38cebe605f3696f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092443"
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="0d87d-102">CorDebugThreadState 枚举</span><span class="sxs-lookup"><span data-stu-id="0d87d-102">CorDebugThreadState Enumeration</span></span>
<span data-ttu-id="0d87d-103">指定用于调试的线程的状态。</span><span class="sxs-lookup"><span data-stu-id="0d87d-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d87d-104">语法</span><span class="sxs-lookup"><span data-stu-id="0d87d-104">Syntax</span></span>  
  
```  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="0d87d-105">成员</span><span class="sxs-lookup"><span data-stu-id="0d87d-105">Members</span></span>  
  
|<span data-ttu-id="0d87d-106">成员</span><span class="sxs-lookup"><span data-stu-id="0d87d-106">Member</span></span>|<span data-ttu-id="0d87d-107">描述</span><span class="sxs-lookup"><span data-stu-id="0d87d-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="0d87d-108">在线程自由运行，除非在调试事件发生。</span><span class="sxs-lookup"><span data-stu-id="0d87d-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="0d87d-109">该线程不能运行。</span><span class="sxs-lookup"><span data-stu-id="0d87d-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d87d-110">备注</span><span class="sxs-lookup"><span data-stu-id="0d87d-110">Remarks</span></span>  
 <span data-ttu-id="0d87d-111">调试器使用`CorDebugThreadState`枚举以控制线程的执行。</span><span class="sxs-lookup"><span data-stu-id="0d87d-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="0d87d-112">可以使用设置的线程状态[icordebugthread:: Setdebugstate](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)或[icordebugcontroller:: Setallthreadsdebugstate](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="0d87d-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="0d87d-113">提供给的回调[托管 API](../../../../docs/framework/unmanaged-api/hosting/index.md)实现消息泵处理，因此无需中断的状态。</span><span class="sxs-lookup"><span data-stu-id="0d87d-113">A callback provided to the [hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d87d-114">要求</span><span class="sxs-lookup"><span data-stu-id="0d87d-114">Requirements</span></span>  
 <span data-ttu-id="0d87d-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0d87d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d87d-116">**标头：** CorDebug.idl CorDegug.h</span><span class="sxs-lookup"><span data-stu-id="0d87d-116">**Header:** CorDebug.idl, CorDegug.h</span></span>  
  
 <span data-ttu-id="0d87d-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d87d-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0d87d-118">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="0d87d-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0d87d-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="0d87d-119">See also</span></span>

- [<span data-ttu-id="0d87d-120">调试枚举</span><span class="sxs-lookup"><span data-stu-id="0d87d-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
