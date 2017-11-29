---
title: "ICorDebugManagedCallback2 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2
helpviewer_keywords: ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: cf7b7cfa-1c4b-4d8c-be70-4f9ed15a788b
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0d5b8ac63d200e54d25b58870089f6c062397186
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2-interface"></a><span data-ttu-id="d575e-102">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="d575e-102">ICorDebugManagedCallback2 Interface</span></span>
<span data-ttu-id="d575e-103">提供支持调试器异常处理和托管调试助手 (MDA) 的方法。</span><span class="sxs-lookup"><span data-stu-id="d575e-103">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="d575e-104">`ICorDebugManagedCallback2`是的逻辑扩展[ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="d575e-104">`ICorDebugManagedCallback2` is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d575e-105">方法</span><span class="sxs-lookup"><span data-stu-id="d575e-105">Methods</span></span>  
  
|<span data-ttu-id="d575e-106">方法</span><span class="sxs-lookup"><span data-stu-id="d575e-106">Method</span></span>|<span data-ttu-id="d575e-107">描述</span><span class="sxs-lookup"><span data-stu-id="d575e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d575e-108">ChangeConnection 方法</span><span class="sxs-lookup"><span data-stu-id="d575e-108">ChangeConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md)|<span data-ttu-id="d575e-109">通知调试器与指定连接关联的任务组已更改。</span><span class="sxs-lookup"><span data-stu-id="d575e-109">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>|  
|[<span data-ttu-id="d575e-110">CreateConnection 方法</span><span class="sxs-lookup"><span data-stu-id="d575e-110">CreateConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md)|<span data-ttu-id="d575e-111">通知调试器已创建新的连接。</span><span class="sxs-lookup"><span data-stu-id="d575e-111">Notifies the debugger that a new connection has been created.</span></span>|  
|[<span data-ttu-id="d575e-112">DestroyConnection 方法</span><span class="sxs-lookup"><span data-stu-id="d575e-112">DestroyConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-destroyconnection-method.md)|<span data-ttu-id="d575e-113">通知调试器已终止指定的连接。</span><span class="sxs-lookup"><span data-stu-id="d575e-113">Notifies the debugger that the specified connection has been terminated.</span></span>|  
|[<span data-ttu-id="d575e-114">Exception 方法</span><span class="sxs-lookup"><span data-stu-id="d575e-114">Exception Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)|<span data-ttu-id="d575e-115">通知调试器搜索异常处理程序已开始。</span><span class="sxs-lookup"><span data-stu-id="d575e-115">Notifies the debugger that a search for an exception handler has started.</span></span>|  
|[<span data-ttu-id="d575e-116">ExceptionUnwind 方法</span><span class="sxs-lookup"><span data-stu-id="d575e-116">ExceptionUnwind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exceptionunwind-method.md)|<span data-ttu-id="d575e-117">提供在异常展开过程中的状态通知。</span><span class="sxs-lookup"><span data-stu-id="d575e-117">Provides a status notification during the exception unwinding process.</span></span>|  
|[<span data-ttu-id="d575e-118">FunctionRemapComplete 方法</span><span class="sxs-lookup"><span data-stu-id="d575e-118">FunctionRemapComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapcomplete-method.md)|<span data-ttu-id="d575e-119">通知调试器执行代码已切换到新版本的已编辑函数。</span><span class="sxs-lookup"><span data-stu-id="d575e-119">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>|  
|[<span data-ttu-id="d575e-120">FunctionRemapOpportunity 方法</span><span class="sxs-lookup"><span data-stu-id="d575e-120">FunctionRemapOpportunity Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md)|<span data-ttu-id="d575e-121">通知调试器执行代码已达到经过编辑的函数的早期版本中的序列点。</span><span class="sxs-lookup"><span data-stu-id="d575e-121">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>|  
|[<span data-ttu-id="d575e-122">MDANotification 方法</span><span class="sxs-lookup"><span data-stu-id="d575e-122">MDANotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-mdanotification-method.md)|<span data-ttu-id="d575e-123">提供了执行代码遇到托管调试助手 (MDA) 消息的通知。</span><span class="sxs-lookup"><span data-stu-id="d575e-123">Provides notification that code execution has encountered a managed debugging assistant (MDA) message.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d575e-124">备注</span><span class="sxs-lookup"><span data-stu-id="d575e-124">Remarks</span></span>  
 <span data-ttu-id="d575e-125">`ICorDebugManagedCallback2`接口扩展`ICorDebugManagedCallback`接口来处理.NET Framework 2.0 版中引入的新调试事件。</span><span class="sxs-lookup"><span data-stu-id="d575e-125">The `ICorDebugManagedCallback2` interface extends the `ICorDebugManagedCallback` interface to handle new debug events introduced in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="d575e-126">调试器必须实现`ICorDebugManagedCallback2`如果它调试.NET Framework 2.0 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d575e-126">A debugger must implement `ICorDebugManagedCallback2` if it is debugging .NET Framework 2.0 applications.</span></span> <span data-ttu-id="d575e-127">实例`ICorDebugManagedCallback`或`ICorDebugManagedCallback2`作为回调对象传递[icordebug:: Setmanagedhandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)。</span><span class="sxs-lookup"><span data-stu-id="d575e-127">An instance of `ICorDebugManagedCallback` or `ICorDebugManagedCallback2` is passed as the callback object to [ICorDebug::SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d575e-128">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="d575e-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d575e-129">要求</span><span class="sxs-lookup"><span data-stu-id="d575e-129">Requirements</span></span>  
 <span data-ttu-id="d575e-130">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d575e-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d575e-131">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d575e-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d575e-132">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d575e-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d575e-133">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d575e-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d575e-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d575e-134">See Also</span></span>  
 [<span data-ttu-id="d575e-135">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="d575e-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="d575e-136">调试接口</span><span class="sxs-lookup"><span data-stu-id="d575e-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="d575e-137">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="d575e-137">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
