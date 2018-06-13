---
title: ICorDebugThread2 接口 1
ms.date: 03/30/2017
api_name:
- ICorDebugThread2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2
helpviewer_keywords:
- ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c348cf28a6330523d1a490c136a3214e37d13f4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423044"
---
# <a name="icordebugthread2-interface1"></a><span data-ttu-id="e1131-102">ICorDebugThread2 接口 1</span><span class="sxs-lookup"><span data-stu-id="e1131-102">ICorDebugThread2 Interface1</span></span>
<span data-ttu-id="e1131-103">用作 ICorDebugThread 接口的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="e1131-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1131-104">方法</span><span class="sxs-lookup"><span data-stu-id="e1131-104">Methods</span></span>  
  
|<span data-ttu-id="e1131-105">方法</span><span class="sxs-lookup"><span data-stu-id="e1131-105">Method</span></span>|<span data-ttu-id="e1131-106">描述</span><span class="sxs-lookup"><span data-stu-id="e1131-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1131-107">GetActiveFunctions 方法</span><span class="sxs-lookup"><span data-stu-id="e1131-107">GetActiveFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="e1131-108">获取包含有关在线程框架中的活动函数的数据的 COR_ACTIVE_FUNCTION 实例的数组。</span><span class="sxs-lookup"><span data-stu-id="e1131-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="e1131-109">GetConnectionID 方法</span><span class="sxs-lookup"><span data-stu-id="e1131-109">GetConnectionID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="e1131-110">获取此连接标识符`ICorDebugThread2`。</span><span class="sxs-lookup"><span data-stu-id="e1131-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="e1131-111">GetTaskID 方法</span><span class="sxs-lookup"><span data-stu-id="e1131-111">GetTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|<span data-ttu-id="e1131-112">获取此任务标识符`ICorDebugThread2`。</span><span class="sxs-lookup"><span data-stu-id="e1131-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="e1131-113">GetVolatileOSThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="e1131-113">GetVolatileOSThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="e1131-114">获取此操作系统线程标识符`ICorDebugThread2`。</span><span class="sxs-lookup"><span data-stu-id="e1131-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="e1131-115">InterceptCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="e1131-115">InterceptCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="e1131-116">允许调试器来截获在线程上的当前异常。</span><span class="sxs-lookup"><span data-stu-id="e1131-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1131-117">备注</span><span class="sxs-lookup"><span data-stu-id="e1131-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1131-118">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="e1131-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1131-119">要求</span><span class="sxs-lookup"><span data-stu-id="e1131-119">Requirements</span></span>  
 <span data-ttu-id="e1131-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e1131-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1131-121">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1131-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1131-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1131-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1131-123">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1131-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1131-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1131-124">See Also</span></span>  
 [<span data-ttu-id="e1131-125">调试接口</span><span class="sxs-lookup"><span data-stu-id="e1131-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
