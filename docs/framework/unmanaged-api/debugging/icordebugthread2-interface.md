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
ms.openlocfilehash: 3826bfd16d3cf7534a6e920c516987908547b419
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716139"
---
# <a name="icordebugthread2-interface1"></a><span data-ttu-id="dad8a-102">ICorDebugThread2 接口 1</span><span class="sxs-lookup"><span data-stu-id="dad8a-102">ICorDebugThread2 Interface1</span></span>
<span data-ttu-id="dad8a-103">用作 ICorDebugThread 接口的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="dad8a-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dad8a-104">方法</span><span class="sxs-lookup"><span data-stu-id="dad8a-104">Methods</span></span>  
  
|<span data-ttu-id="dad8a-105">方法</span><span class="sxs-lookup"><span data-stu-id="dad8a-105">Method</span></span>|<span data-ttu-id="dad8a-106">描述</span><span class="sxs-lookup"><span data-stu-id="dad8a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dad8a-107">GetActiveFunctions 方法</span><span class="sxs-lookup"><span data-stu-id="dad8a-107">GetActiveFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="dad8a-108">获取包含有关线程的帧中的活动函数的数据的 COR_ACTIVE_FUNCTION 实例的数组。</span><span class="sxs-lookup"><span data-stu-id="dad8a-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="dad8a-109">GetConnectionID 方法</span><span class="sxs-lookup"><span data-stu-id="dad8a-109">GetConnectionID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="dad8a-110">获取此连接标识符`ICorDebugThread2`。</span><span class="sxs-lookup"><span data-stu-id="dad8a-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="dad8a-111">GetTaskID 方法</span><span class="sxs-lookup"><span data-stu-id="dad8a-111">GetTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|<span data-ttu-id="dad8a-112">获取此任务标识符`ICorDebugThread2`。</span><span class="sxs-lookup"><span data-stu-id="dad8a-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="dad8a-113">GetVolatileOSThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="dad8a-113">GetVolatileOSThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="dad8a-114">获取此操作系统线程标识符`ICorDebugThread2`。</span><span class="sxs-lookup"><span data-stu-id="dad8a-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="dad8a-115">InterceptCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="dad8a-115">InterceptCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="dad8a-116">允许调试器来拦截上一个线程的当前异常。</span><span class="sxs-lookup"><span data-stu-id="dad8a-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dad8a-117">备注</span><span class="sxs-lookup"><span data-stu-id="dad8a-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dad8a-118">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="dad8a-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dad8a-119">要求</span><span class="sxs-lookup"><span data-stu-id="dad8a-119">Requirements</span></span>  
 <span data-ttu-id="dad8a-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dad8a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dad8a-121">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dad8a-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dad8a-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dad8a-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dad8a-123">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dad8a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dad8a-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="dad8a-124">See also</span></span>
- [<span data-ttu-id="dad8a-125">调试接口</span><span class="sxs-lookup"><span data-stu-id="dad8a-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
