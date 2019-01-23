---
title: ICorDebugManagedCallback2::CreateConnection 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 50e9f3b8271cb5e518b75ee129fe6ea2a1b7720d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512926"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="4cd97-102">ICorDebugManagedCallback2::CreateConnection 方法</span><span class="sxs-lookup"><span data-stu-id="4cd97-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="4cd97-103">通知调试器已创建新的连接。</span><span class="sxs-lookup"><span data-stu-id="4cd97-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cd97-104">语法</span><span class="sxs-lookup"><span data-stu-id="4cd97-104">Syntax</span></span>  
  
```  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4cd97-105">参数</span><span class="sxs-lookup"><span data-stu-id="4cd97-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="4cd97-106">[in]指向"ICorDebugProcess"对象，表示在其中创建该连接的进程</span><span class="sxs-lookup"><span data-stu-id="4cd97-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="4cd97-107">[in]新的连接的 ID。</span><span class="sxs-lookup"><span data-stu-id="4cd97-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="4cd97-108">[in]一个指向新的连接的名称。</span><span class="sxs-lookup"><span data-stu-id="4cd97-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cd97-109">备注</span><span class="sxs-lookup"><span data-stu-id="4cd97-109">Remarks</span></span>  
 <span data-ttu-id="4cd97-110">一个`CreateConnection`回调时将触发以下情况之一：</span><span class="sxs-lookup"><span data-stu-id="4cd97-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
-   <span data-ttu-id="4cd97-111">当调试器附加到包含连接的进程。</span><span class="sxs-lookup"><span data-stu-id="4cd97-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="4cd97-112">在这种情况下，运行时将生成并调度`CreateConnection`事件和一个[ICorDebugManagedCallback2::ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md)事件过程中每个连接。</span><span class="sxs-lookup"><span data-stu-id="4cd97-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
-   <span data-ttu-id="4cd97-113">当主机调用[iclrdebugmanager:: Beginconnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)中[承载 API](../../../../docs/framework/unmanaged-api/hosting/index.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd97-113">When a host calls [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cd97-114">要求</span><span class="sxs-lookup"><span data-stu-id="4cd97-114">Requirements</span></span>  
 <span data-ttu-id="4cd97-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd97-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cd97-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4cd97-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4cd97-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cd97-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cd97-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cd97-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cd97-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cd97-119">See also</span></span>
- [<span data-ttu-id="4cd97-120">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="4cd97-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="4cd97-121">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="4cd97-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
