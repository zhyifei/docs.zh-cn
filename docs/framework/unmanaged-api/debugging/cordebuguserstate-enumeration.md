---
title: "CorDebugUserState 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 57fd9df27b1911c90bd11712b67e6e64588c2b5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cordebuguserstate-enumeration"></a><span data-ttu-id="55992-102">CorDebugUserState 枚举</span><span class="sxs-lookup"><span data-stu-id="55992-102">CorDebugUserState Enumeration</span></span>
<span data-ttu-id="55992-103">指示线程的用户状态。</span><span class="sxs-lookup"><span data-stu-id="55992-103">Indicates the user state of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55992-104">语法</span><span class="sxs-lookup"><span data-stu-id="55992-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="55992-105">成员</span><span class="sxs-lookup"><span data-stu-id="55992-105">Members</span></span>  
  
|<span data-ttu-id="55992-106">值</span><span class="sxs-lookup"><span data-stu-id="55992-106">Value</span></span>|<span data-ttu-id="55992-107">描述</span><span class="sxs-lookup"><span data-stu-id="55992-107">Description</span></span>|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|<span data-ttu-id="55992-108">已请求的线程终止。</span><span class="sxs-lookup"><span data-stu-id="55992-108">A termination of the thread has been requested.</span></span>|  
|`USER_SUSPEND_REQUESTED`|<span data-ttu-id="55992-109">已请求线程的挂起。</span><span class="sxs-lookup"><span data-stu-id="55992-109">A suspension of the thread has been requested.</span></span>|  
|`USER_BACKGROUND`|<span data-ttu-id="55992-110">在后台运行该线程。</span><span class="sxs-lookup"><span data-stu-id="55992-110">The thread is running in the background.</span></span>|  
|`USER_UNSTARTED`|<span data-ttu-id="55992-111">线程开始执行。</span><span class="sxs-lookup"><span data-stu-id="55992-111">The thread has not started executing.</span></span>|  
|`USER_STOPPED`|<span data-ttu-id="55992-112">线程已终止。</span><span class="sxs-lookup"><span data-stu-id="55992-112">The thread has been terminated.</span></span>|  
|`USER_WAIT_SLEEP_JOIN`|<span data-ttu-id="55992-113">线程正在等待另一个线程来完成任务。</span><span class="sxs-lookup"><span data-stu-id="55992-113">The thread is waiting for another thread to complete a task.</span></span>|  
|`USER_SUSPENDED`|<span data-ttu-id="55992-114">线程已挂起。</span><span class="sxs-lookup"><span data-stu-id="55992-114">The thread has been suspended.</span></span>|  
|`USER_UNSAFE_POINT`|<span data-ttu-id="55992-115">该线程是一个不安全的点处。</span><span class="sxs-lookup"><span data-stu-id="55992-115">The thread is at an unsafe point.</span></span> <span data-ttu-id="55992-116">也就是说，线程是执行在某个点中可能阻止垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="55992-116">That is, the thread is at a point in execution where it may block garbage collection.</span></span><br /><br /> <span data-ttu-id="55992-117">调试事件可能调度从不安全的点，但是挂起线程，将一个不安全的点处将很有可能导致死锁在恢复线程之前。</span><span class="sxs-lookup"><span data-stu-id="55992-117">Debug events may be dispatched from unsafe points, but suspending a thread at an unsafe point  will very likely cause a deadlock until the thread is resumed.</span></span> <span data-ttu-id="55992-118">由实时 (JIT) 和垃圾回收实现确定的安全和不安全的点。</span><span class="sxs-lookup"><span data-stu-id="55992-118">The safe and unsafe points are determined by the just-in-time (JIT) and garbage collection implementation.</span></span>|  
|`USER_THREADPOOL`|<span data-ttu-id="55992-119">该线程是从线程池。</span><span class="sxs-lookup"><span data-stu-id="55992-119">The thread is from the thread pool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55992-120">备注</span><span class="sxs-lookup"><span data-stu-id="55992-120">Remarks</span></span>  
 <span data-ttu-id="55992-121">用户状态是线程的时调试器检查该线程具有的状态。</span><span class="sxs-lookup"><span data-stu-id="55992-121">The user state of a thread is the state that the thread has when the debugger examines it.</span></span> <span data-ttu-id="55992-122">一个线程可能具有用户状态的组合。</span><span class="sxs-lookup"><span data-stu-id="55992-122">A thread may have a combination of user states.</span></span>  
  
 <span data-ttu-id="55992-123">使用[icordebugthread:: Getuserstate](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)方法来检索线程的用户状态。</span><span class="sxs-lookup"><span data-stu-id="55992-123">Use the [ICorDebugThread::GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) method to retrieve a thread's user state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55992-124">惠?</span><span class="sxs-lookup"><span data-stu-id="55992-124">Requirements</span></span>  
 <span data-ttu-id="55992-125">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="55992-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55992-126">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55992-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55992-127">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55992-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55992-128">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55992-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55992-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="55992-129">See Also</span></span>  
 [<span data-ttu-id="55992-130">调试枚举</span><span class="sxs-lookup"><span data-stu-id="55992-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
