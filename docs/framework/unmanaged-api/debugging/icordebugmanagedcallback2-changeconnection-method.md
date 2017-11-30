---
title: "ICorDebugManagedCallback2::ChangeConnection 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.ChangeConnection
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c62859cb6a3e61af9670834db169410cecb6787
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a><span data-ttu-id="a46a8-102">ICorDebugManagedCallback2::ChangeConnection 方法</span><span class="sxs-lookup"><span data-stu-id="a46a8-102">ICorDebugManagedCallback2::ChangeConnection Method</span></span>
<span data-ttu-id="a46a8-103">通知调试器与指定连接关联的任务组已更改。</span><span class="sxs-lookup"><span data-stu-id="a46a8-103">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a46a8-104">语法</span><span class="sxs-lookup"><span data-stu-id="a46a8-104">Syntax</span></span>  
  
```  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a46a8-105">参数</span><span class="sxs-lookup"><span data-stu-id="a46a8-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="a46a8-106">[in]指向一个表示包含更改连接的过程的"ICorDebugProcess"对象的指针。</span><span class="sxs-lookup"><span data-stu-id="a46a8-106">[in] A pointer to an "ICorDebugProcess" object that represents the process containing the connection that changed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="a46a8-107">[in]更改连接的 ID。</span><span class="sxs-lookup"><span data-stu-id="a46a8-107">[in] The ID of the connection that changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a46a8-108">备注</span><span class="sxs-lookup"><span data-stu-id="a46a8-108">Remarks</span></span>  
 <span data-ttu-id="a46a8-109">A`ChangeConnection`回调将触发在以下情况：</span><span class="sxs-lookup"><span data-stu-id="a46a8-109">A `ChangeConnection` callback will be fired in either of the following cases:</span></span>  
  
-   <span data-ttu-id="a46a8-110">当调试器附加到进程，其中包含连接。</span><span class="sxs-lookup"><span data-stu-id="a46a8-110">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="a46a8-111">在这种情况下，运行时将生成并调度[icordebugmanagedcallback2:: Createconnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md)事件和一个`ChangeConnection`事件过程中每个连接。</span><span class="sxs-lookup"><span data-stu-id="a46a8-111">In this case, the runtime will generate and dispatch a [ICorDebugManagedCallback2::CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) event and a `ChangeConnection` event for each connection in the process.</span></span> <span data-ttu-id="a46a8-112">A`ChangeConnection`对于每个现有的连接，而不考虑该连接组的任务具有已更改其创建后生成事件。</span><span class="sxs-lookup"><span data-stu-id="a46a8-112">A `ChangeConnection` event is generated for every existing connection, regardless of whether that connection’s set of tasks has been changed since its creation.</span></span>  
  
-   <span data-ttu-id="a46a8-113">当主机调用[iclrdebugmanager:: Setconnectiontasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)中[承载 API](../../../../docs/framework/unmanaged-api/hosting/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a46a8-113">When a host calls [ICLRDebugManager::SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
 <span data-ttu-id="a46a8-114">调试器应扫描以拾取新的更改的过程中的所有线程。</span><span class="sxs-lookup"><span data-stu-id="a46a8-114">The debugger should scan all threads in the process to pick up the new changes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a46a8-115">要求</span><span class="sxs-lookup"><span data-stu-id="a46a8-115">Requirements</span></span>  
 <span data-ttu-id="a46a8-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a46a8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a46a8-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a46a8-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a46a8-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a46a8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a46a8-119">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a46a8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a46a8-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a46a8-120">See Also</span></span>  
 [<span data-ttu-id="a46a8-121">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="a46a8-121">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="a46a8-122">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="a46a8-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
