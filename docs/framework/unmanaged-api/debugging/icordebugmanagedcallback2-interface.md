---
title: ICorDebugManagedCallback2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2
helpviewer_keywords:
- ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: cf7b7cfa-1c4b-4d8c-be70-4f9ed15a788b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1ecfea208f87f53f15fcc4cdafb58341c293e43
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096083"
---
# <a name="icordebugmanagedcallback2-interface"></a><span data-ttu-id="b9483-102">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="b9483-102">ICorDebugManagedCallback2 Interface</span></span>
<span data-ttu-id="b9483-103">提供支持调试器异常处理和托管调试助手 (MDA) 的方法。</span><span class="sxs-lookup"><span data-stu-id="b9483-103">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="b9483-104">`ICorDebugManagedCallback2` 是的逻辑扩展[ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="b9483-104">`ICorDebugManagedCallback2` is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b9483-105">方法</span><span class="sxs-lookup"><span data-stu-id="b9483-105">Methods</span></span>  
  
|<span data-ttu-id="b9483-106">方法</span><span class="sxs-lookup"><span data-stu-id="b9483-106">Method</span></span>|<span data-ttu-id="b9483-107">描述</span><span class="sxs-lookup"><span data-stu-id="b9483-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b9483-108">ChangeConnection 方法</span><span class="sxs-lookup"><span data-stu-id="b9483-108">ChangeConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md)|<span data-ttu-id="b9483-109">通知调试器与指定的连接关联的任务集已更改。</span><span class="sxs-lookup"><span data-stu-id="b9483-109">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>|  
|[<span data-ttu-id="b9483-110">CreateConnection 方法</span><span class="sxs-lookup"><span data-stu-id="b9483-110">CreateConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md)|<span data-ttu-id="b9483-111">通知调试器已创建新的连接。</span><span class="sxs-lookup"><span data-stu-id="b9483-111">Notifies the debugger that a new connection has been created.</span></span>|  
|[<span data-ttu-id="b9483-112">DestroyConnection 方法</span><span class="sxs-lookup"><span data-stu-id="b9483-112">DestroyConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-destroyconnection-method.md)|<span data-ttu-id="b9483-113">通知调试器指定的连接已终止。</span><span class="sxs-lookup"><span data-stu-id="b9483-113">Notifies the debugger that the specified connection has been terminated.</span></span>|  
|[<span data-ttu-id="b9483-114">Exception 方法</span><span class="sxs-lookup"><span data-stu-id="b9483-114">Exception Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)|<span data-ttu-id="b9483-115">通知调试器的异常处理程序的搜索已启动。</span><span class="sxs-lookup"><span data-stu-id="b9483-115">Notifies the debugger that a search for an exception handler has started.</span></span>|  
|[<span data-ttu-id="b9483-116">ExceptionUnwind 方法</span><span class="sxs-lookup"><span data-stu-id="b9483-116">ExceptionUnwind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exceptionunwind-method.md)|<span data-ttu-id="b9483-117">提供在异常展开过程中的状态通知。</span><span class="sxs-lookup"><span data-stu-id="b9483-117">Provides a status notification during the exception unwinding process.</span></span>|  
|[<span data-ttu-id="b9483-118">FunctionRemapComplete 方法</span><span class="sxs-lookup"><span data-stu-id="b9483-118">FunctionRemapComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapcomplete-method.md)|<span data-ttu-id="b9483-119">通知调试器执行代码已切换到新版本的已编辑函数。</span><span class="sxs-lookup"><span data-stu-id="b9483-119">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>|  
|[<span data-ttu-id="b9483-120">FunctionRemapOpportunity 方法</span><span class="sxs-lookup"><span data-stu-id="b9483-120">FunctionRemapOpportunity Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md)|<span data-ttu-id="b9483-121">通知调试器执行代码已达到已编辑函数的较旧版本中的序列点。</span><span class="sxs-lookup"><span data-stu-id="b9483-121">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>|  
|[<span data-ttu-id="b9483-122">MDANotification 方法</span><span class="sxs-lookup"><span data-stu-id="b9483-122">MDANotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-mdanotification-method.md)|<span data-ttu-id="b9483-123">提供了执行代码遇到托管调试助手 (MDA) 消息的通知。</span><span class="sxs-lookup"><span data-stu-id="b9483-123">Provides notification that code execution has encountered a managed debugging assistant (MDA) message.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9483-124">备注</span><span class="sxs-lookup"><span data-stu-id="b9483-124">Remarks</span></span>  
 <span data-ttu-id="b9483-125">`ICorDebugManagedCallback2`接口扩展`ICorDebugManagedCallback`接口以处理在.NET Framework 2.0 版中引入的新调试事件。</span><span class="sxs-lookup"><span data-stu-id="b9483-125">The `ICorDebugManagedCallback2` interface extends the `ICorDebugManagedCallback` interface to handle new debug events introduced in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="b9483-126">调试程序必须实现`ICorDebugManagedCallback2`如果它调试.NET Framework 2.0 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b9483-126">A debugger must implement `ICorDebugManagedCallback2` if it is debugging .NET Framework 2.0 applications.</span></span> <span data-ttu-id="b9483-127">实例`ICorDebugManagedCallback`或`ICorDebugManagedCallback2`传递到回调对象作为[icordebug:: Setmanagedhandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)。</span><span class="sxs-lookup"><span data-stu-id="b9483-127">An instance of `ICorDebugManagedCallback` or `ICorDebugManagedCallback2` is passed as the callback object to [ICorDebug::SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b9483-128">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="b9483-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9483-129">要求</span><span class="sxs-lookup"><span data-stu-id="b9483-129">Requirements</span></span>  
 <span data-ttu-id="b9483-130">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b9483-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9483-131">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9483-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9483-132">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9483-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9483-133">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9483-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9483-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9483-134">See also</span></span>

- [<span data-ttu-id="b9483-135">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="b9483-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="b9483-136">调试接口</span><span class="sxs-lookup"><span data-stu-id="b9483-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="b9483-137">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="b9483-137">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
