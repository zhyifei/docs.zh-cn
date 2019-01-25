---
title: CorDebugUserState 枚举
ms.date: 03/30/2017
api_name:
- CorDebugUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUserState
helpviewer_keywords:
- CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1ee5044c2223d3ff90cf10b53cad4e1b353d87c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726502"
---
# <a name="cordebuguserstate-enumeration"></a><span data-ttu-id="385f4-102">CorDebugUserState 枚举</span><span class="sxs-lookup"><span data-stu-id="385f4-102">CorDebugUserState Enumeration</span></span>
<span data-ttu-id="385f4-103">指示线程的用户状态。</span><span class="sxs-lookup"><span data-stu-id="385f4-103">Indicates the user state of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="385f4-104">语法</span><span class="sxs-lookup"><span data-stu-id="385f4-104">Syntax</span></span>  
  
```  
typedef enum CorDebugUserState {  
    USER_STOP_REQUESTED     =  0x01,  
    USER_SUSPEND_REQUESTED  =  0x02,  
    USER_BACKGROUND         =  0x04,  
    USER_UNSTARTED          =  0x08,  
    USER_STOPPED            =  0x10,  
    USER_WAIT_SLEEP_JOIN    =  0x20,  
    USER_SUSPENDED          =  0x40,  
    USER_UNSAFE_POINT       =  0x80,  
    USER_THREADPOOL         = 0x100  
} CorDebugUserState;  
```  
  
## <a name="members"></a><span data-ttu-id="385f4-105">成员</span><span class="sxs-lookup"><span data-stu-id="385f4-105">Members</span></span>  
  
|<span data-ttu-id="385f4-106">值</span><span class="sxs-lookup"><span data-stu-id="385f4-106">Value</span></span>|<span data-ttu-id="385f4-107">描述</span><span class="sxs-lookup"><span data-stu-id="385f4-107">Description</span></span>|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|<span data-ttu-id="385f4-108">已请求的线程终止。</span><span class="sxs-lookup"><span data-stu-id="385f4-108">A termination of the thread has been requested.</span></span>|  
|`USER_SUSPEND_REQUESTED`|<span data-ttu-id="385f4-109">已请求挂起线程。</span><span class="sxs-lookup"><span data-stu-id="385f4-109">A suspension of the thread has been requested.</span></span>|  
|`USER_BACKGROUND`|<span data-ttu-id="385f4-110">线程已在后台运行。</span><span class="sxs-lookup"><span data-stu-id="385f4-110">The thread is running in the background.</span></span>|  
|`USER_UNSTARTED`|<span data-ttu-id="385f4-111">该线程尚未开始执行。</span><span class="sxs-lookup"><span data-stu-id="385f4-111">The thread has not started executing.</span></span>|  
|`USER_STOPPED`|<span data-ttu-id="385f4-112">线程已终止。</span><span class="sxs-lookup"><span data-stu-id="385f4-112">The thread has been terminated.</span></span>|  
|`USER_WAIT_SLEEP_JOIN`|<span data-ttu-id="385f4-113">线程正在等待另一个线程来完成任务。</span><span class="sxs-lookup"><span data-stu-id="385f4-113">The thread is waiting for another thread to complete a task.</span></span>|  
|`USER_SUSPENDED`|<span data-ttu-id="385f4-114">线程已挂起。</span><span class="sxs-lookup"><span data-stu-id="385f4-114">The thread has been suspended.</span></span>|  
|`USER_UNSAFE_POINT`|<span data-ttu-id="385f4-115">该线程是在不安全的点。</span><span class="sxs-lookup"><span data-stu-id="385f4-115">The thread is at an unsafe point.</span></span> <span data-ttu-id="385f4-116">也就是说，线程处于中执行的点，它可能会阻止垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="385f4-116">That is, the thread is at a point in execution where it may block garbage collection.</span></span><br /><br /> <span data-ttu-id="385f4-117">调试事件的调度可能不安全的点，但挂起线程，在不安全的点将很有可能导致死锁在恢复该线程之前。</span><span class="sxs-lookup"><span data-stu-id="385f4-117">Debug events may be dispatched from unsafe points, but suspending a thread at an unsafe point  will very likely cause a deadlock until the thread is resumed.</span></span> <span data-ttu-id="385f4-118">由实时 (JIT) 和垃圾回收实现确定的安全和不安全点。</span><span class="sxs-lookup"><span data-stu-id="385f4-118">The safe and unsafe points are determined by the just-in-time (JIT) and garbage collection implementation.</span></span>|  
|`USER_THREADPOOL`|<span data-ttu-id="385f4-119">该线程是从线程池。</span><span class="sxs-lookup"><span data-stu-id="385f4-119">The thread is from the thread pool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="385f4-120">备注</span><span class="sxs-lookup"><span data-stu-id="385f4-120">Remarks</span></span>  
 <span data-ttu-id="385f4-121">用户状态是线程的调试器检查时该线程具有的状态。</span><span class="sxs-lookup"><span data-stu-id="385f4-121">The user state of a thread is the state that the thread has when the debugger examines it.</span></span> <span data-ttu-id="385f4-122">一个线程可能具有的用户状态的组合。</span><span class="sxs-lookup"><span data-stu-id="385f4-122">A thread may have a combination of user states.</span></span>  
  
 <span data-ttu-id="385f4-123">使用[icordebugthread:: Getuserstate](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)方法来检索线程的用户状态。</span><span class="sxs-lookup"><span data-stu-id="385f4-123">Use the [ICorDebugThread::GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) method to retrieve a thread's user state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="385f4-124">要求</span><span class="sxs-lookup"><span data-stu-id="385f4-124">Requirements</span></span>  
 <span data-ttu-id="385f4-125">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="385f4-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="385f4-126">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="385f4-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="385f4-127">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="385f4-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="385f4-128">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="385f4-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="385f4-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="385f4-129">See also</span></span>
- [<span data-ttu-id="385f4-130">调试枚举</span><span class="sxs-lookup"><span data-stu-id="385f4-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
