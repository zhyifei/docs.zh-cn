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
ms.openlocfilehash: 43982ebb634843c0130c3321aa84c90b84e8c786
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793312"
---
# <a name="icordebugmanagedcallback2-interface"></a><span data-ttu-id="3ec52-102">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="3ec52-102">ICorDebugManagedCallback2 Interface</span></span>
<span data-ttu-id="3ec52-103">提供支持调试器异常处理和托管调试助手 (MDA) 的方法。</span><span class="sxs-lookup"><span data-stu-id="3ec52-103">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="3ec52-104">`ICorDebugManagedCallback2` 是[ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)接口的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="3ec52-104">`ICorDebugManagedCallback2` is a logical extension of the [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3ec52-105">方法</span><span class="sxs-lookup"><span data-stu-id="3ec52-105">Methods</span></span>  
  
|<span data-ttu-id="3ec52-106">方法</span><span class="sxs-lookup"><span data-stu-id="3ec52-106">Method</span></span>|<span data-ttu-id="3ec52-107">描述</span><span class="sxs-lookup"><span data-stu-id="3ec52-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3ec52-108">ChangeConnection 方法</span><span class="sxs-lookup"><span data-stu-id="3ec52-108">ChangeConnection Method</span></span>](icordebugmanagedcallback2-changeconnection-method.md)|<span data-ttu-id="3ec52-109">通知调试器与指定连接关联的任务集已更改。</span><span class="sxs-lookup"><span data-stu-id="3ec52-109">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>|  
|[<span data-ttu-id="3ec52-110">CreateConnection 方法</span><span class="sxs-lookup"><span data-stu-id="3ec52-110">CreateConnection Method</span></span>](icordebugmanagedcallback2-createconnection-method.md)|<span data-ttu-id="3ec52-111">通知调试器已创建新连接。</span><span class="sxs-lookup"><span data-stu-id="3ec52-111">Notifies the debugger that a new connection has been created.</span></span>|  
|[<span data-ttu-id="3ec52-112">DestroyConnection 方法</span><span class="sxs-lookup"><span data-stu-id="3ec52-112">DestroyConnection Method</span></span>](icordebugmanagedcallback2-destroyconnection-method.md)|<span data-ttu-id="3ec52-113">通知调试器指定的连接已终止。</span><span class="sxs-lookup"><span data-stu-id="3ec52-113">Notifies the debugger that the specified connection has been terminated.</span></span>|  
|[<span data-ttu-id="3ec52-114">Exception 方法</span><span class="sxs-lookup"><span data-stu-id="3ec52-114">Exception Method</span></span>](icordebugmanagedcallback2-exception-method.md)|<span data-ttu-id="3ec52-115">通知调试器已开始搜索异常处理程序。</span><span class="sxs-lookup"><span data-stu-id="3ec52-115">Notifies the debugger that a search for an exception handler has started.</span></span>|  
|[<span data-ttu-id="3ec52-116">ExceptionUnwind 方法</span><span class="sxs-lookup"><span data-stu-id="3ec52-116">ExceptionUnwind Method</span></span>](icordebugmanagedcallback2-exceptionunwind-method.md)|<span data-ttu-id="3ec52-117">在异常展开过程中提供状态通知。</span><span class="sxs-lookup"><span data-stu-id="3ec52-117">Provides a status notification during the exception unwinding process.</span></span>|  
|[<span data-ttu-id="3ec52-118">FunctionRemapComplete 方法</span><span class="sxs-lookup"><span data-stu-id="3ec52-118">FunctionRemapComplete Method</span></span>](icordebugmanagedcallback2-functionremapcomplete-method.md)|<span data-ttu-id="3ec52-119">通知调试器，代码执行已切换到已编辑函数的新版本。</span><span class="sxs-lookup"><span data-stu-id="3ec52-119">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>|  
|[<span data-ttu-id="3ec52-120">FunctionRemapOpportunity 方法</span><span class="sxs-lookup"><span data-stu-id="3ec52-120">FunctionRemapOpportunity Method</span></span>](icordebugmanagedcallback2-functionremapopportunity-method.md)|<span data-ttu-id="3ec52-121">通知调试程序代码执行已到达已编辑函数的较早版本中的序列点。</span><span class="sxs-lookup"><span data-stu-id="3ec52-121">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>|  
|[<span data-ttu-id="3ec52-122">MDANotification 方法</span><span class="sxs-lookup"><span data-stu-id="3ec52-122">MDANotification Method</span></span>](icordebugmanagedcallback2-mdanotification-method.md)|<span data-ttu-id="3ec52-123">提供代码执行遇到托管调试助手（MDA）消息的通知。</span><span class="sxs-lookup"><span data-stu-id="3ec52-123">Provides notification that code execution has encountered a managed debugging assistant (MDA) message.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ec52-124">备注</span><span class="sxs-lookup"><span data-stu-id="3ec52-124">Remarks</span></span>  
 <span data-ttu-id="3ec52-125">`ICorDebugManagedCallback2` 接口扩展了 `ICorDebugManagedCallback` 接口，以处理 .NET Framework 版本2.0 中引入的新调试事件。</span><span class="sxs-lookup"><span data-stu-id="3ec52-125">The `ICorDebugManagedCallback2` interface extends the `ICorDebugManagedCallback` interface to handle new debug events introduced in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="3ec52-126">如果调试程序 .NET Framework 2.0 应用程序进行调试，则调试器必须实现 `ICorDebugManagedCallback2`。</span><span class="sxs-lookup"><span data-stu-id="3ec52-126">A debugger must implement `ICorDebugManagedCallback2` if it is debugging .NET Framework 2.0 applications.</span></span> <span data-ttu-id="3ec52-127">`ICorDebugManagedCallback` 或 `ICorDebugManagedCallback2` 的实例作为回调对象传递到[ICorDebug：： SetManagedHandler](icordebug-setmanagedhandler-method.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec52-127">An instance of `ICorDebugManagedCallback` or `ICorDebugManagedCallback2` is passed as the callback object to [ICorDebug::SetManagedHandler](icordebug-setmanagedhandler-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3ec52-128">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="3ec52-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ec52-129">需求</span><span class="sxs-lookup"><span data-stu-id="3ec52-129">Requirements</span></span>  
 <span data-ttu-id="3ec52-130">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec52-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ec52-131">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ec52-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ec52-132">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ec52-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ec52-133">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ec52-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ec52-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ec52-134">See also</span></span>

- [<span data-ttu-id="3ec52-135">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="3ec52-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="3ec52-136">调试接口</span><span class="sxs-lookup"><span data-stu-id="3ec52-136">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3ec52-137">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="3ec52-137">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
