---
title: "ICorDebugManagedCallback2::CreateConnection 方法"
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
- ICorDebugManagedCallback2.CreateConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::CreateConnection
helpviewer_keywords:
- CreateConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::CreateConnection method [.NET Framework debugging]
ms.assetid: 49e647be-9d63-4250-9d11-704e2a400d1b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5e0037f72e51683e5b1d62ad7ecb9aa185f53370
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="9bd35-102">ICorDebugManagedCallback2::CreateConnection 方法</span><span class="sxs-lookup"><span data-stu-id="9bd35-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="9bd35-103">通知调试器已创建新的连接。</span><span class="sxs-lookup"><span data-stu-id="9bd35-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bd35-104">语法</span><span class="sxs-lookup"><span data-stu-id="9bd35-104">Syntax</span></span>  
  
```  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9bd35-105">参数</span><span class="sxs-lookup"><span data-stu-id="9bd35-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="9bd35-106">[in]指向一个表示在其中创建连接的过程的"ICorDebugProcess"对象的指针</span><span class="sxs-lookup"><span data-stu-id="9bd35-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="9bd35-107">[in]新的连接的 ID。</span><span class="sxs-lookup"><span data-stu-id="9bd35-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="9bd35-108">[in]指向新的连接的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="9bd35-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9bd35-109">备注</span><span class="sxs-lookup"><span data-stu-id="9bd35-109">Remarks</span></span>  
 <span data-ttu-id="9bd35-110">A`CreateConnection`回调将触发在以下情况：</span><span class="sxs-lookup"><span data-stu-id="9bd35-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
-   <span data-ttu-id="9bd35-111">当调试器附加到进程，其中包含连接。</span><span class="sxs-lookup"><span data-stu-id="9bd35-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="9bd35-112">在这种情况下，运行时将生成并调度`CreateConnection`事件和一个[icordebugmanagedcallback2:: Changeconnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md)事件过程中每个连接。</span><span class="sxs-lookup"><span data-stu-id="9bd35-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
-   <span data-ttu-id="9bd35-113">当主机调用[iclrdebugmanager:: Beginconnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)中[承载 API](../../../../docs/framework/unmanaged-api/hosting/index.md)。</span><span class="sxs-lookup"><span data-stu-id="9bd35-113">When a host calls [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bd35-114">惠?</span><span class="sxs-lookup"><span data-stu-id="9bd35-114">Requirements</span></span>  
 <span data-ttu-id="9bd35-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9bd35-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bd35-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9bd35-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9bd35-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9bd35-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bd35-118">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bd35-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bd35-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="9bd35-119">See Also</span></span>  
 [<span data-ttu-id="9bd35-120">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="9bd35-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="9bd35-121">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="9bd35-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
