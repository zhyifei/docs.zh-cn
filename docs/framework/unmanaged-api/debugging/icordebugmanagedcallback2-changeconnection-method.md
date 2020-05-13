---
title: ICorDebugManagedCallback2::ChangeConnection 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ChangeConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type:
- apiref
ms.openlocfilehash: 2c6ed14f9238d653b15d26dec9d954c05238817c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213447"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a><span data-ttu-id="302ee-102">ICorDebugManagedCallback2::ChangeConnection 方法</span><span class="sxs-lookup"><span data-stu-id="302ee-102">ICorDebugManagedCallback2::ChangeConnection Method</span></span>
<span data-ttu-id="302ee-103">通知调试器与指定连接关联的任务集已更改。</span><span class="sxs-lookup"><span data-stu-id="302ee-103">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="302ee-104">语法</span><span class="sxs-lookup"><span data-stu-id="302ee-104">Syntax</span></span>  
  
```cpp  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="302ee-105">参数</span><span class="sxs-lookup"><span data-stu-id="302ee-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="302ee-106">中一个指向 "ICorDebugProcess" 对象的指针，该对象表示包含已更改的连接的进程。</span><span class="sxs-lookup"><span data-stu-id="302ee-106">[in] A pointer to an "ICorDebugProcess" object that represents the process containing the connection that changed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="302ee-107">中已更改的连接的 ID。</span><span class="sxs-lookup"><span data-stu-id="302ee-107">[in] The ID of the connection that changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="302ee-108">备注</span><span class="sxs-lookup"><span data-stu-id="302ee-108">Remarks</span></span>  
 <span data-ttu-id="302ee-109">`ChangeConnection`在以下任一情况下，都将激发回调：</span><span class="sxs-lookup"><span data-stu-id="302ee-109">A `ChangeConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="302ee-110">调试器附加到包含连接的进程时。</span><span class="sxs-lookup"><span data-stu-id="302ee-110">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="302ee-111">在这种情况下，运行时将为进程中的每个连接生成并调度一个[ICorDebugManagedCallback2：： CreateConnection](icordebugmanagedcallback2-createconnection-method.md)事件和一个 `ChangeConnection` 事件。</span><span class="sxs-lookup"><span data-stu-id="302ee-111">In this case, the runtime will generate and dispatch a [ICorDebugManagedCallback2::CreateConnection](icordebugmanagedcallback2-createconnection-method.md) event and a `ChangeConnection` event for each connection in the process.</span></span> <span data-ttu-id="302ee-112">将 `ChangeConnection` 为每个现有连接生成一个事件，而不管该连接的一组任务在创建后是否已更改。</span><span class="sxs-lookup"><span data-stu-id="302ee-112">A `ChangeConnection` event is generated for every existing connection, regardless of whether that connection’s set of tasks has been changed since its creation.</span></span>  
  
- <span data-ttu-id="302ee-113">当主机在[托管 API](../hosting/index.md)中调用[ICLRDebugManager：： SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)时。</span><span class="sxs-lookup"><span data-stu-id="302ee-113">When a host calls [ICLRDebugManager::SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
 <span data-ttu-id="302ee-114">调试器应扫描进程中的所有线程以选取新的更改。</span><span class="sxs-lookup"><span data-stu-id="302ee-114">The debugger should scan all threads in the process to pick up the new changes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="302ee-115">要求</span><span class="sxs-lookup"><span data-stu-id="302ee-115">Requirements</span></span>  
 <span data-ttu-id="302ee-116">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="302ee-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="302ee-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="302ee-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="302ee-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="302ee-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="302ee-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="302ee-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="302ee-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="302ee-120">See also</span></span>

- [<span data-ttu-id="302ee-121">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="302ee-121">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="302ee-122">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="302ee-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
