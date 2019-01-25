---
title: ICorDebugManagedCallback2::DestroyConnection 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.DestroyConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::DestroyConnection
helpviewer_keywords:
- DestroyConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::DestroyConnection method [.NET Framework debugging]
ms.assetid: cf7940e9-4558-4319-925c-09f6c98c8fcd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c38846dc142cf011cd7fe859626aa8c19426074
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563790"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="f50c8-102">ICorDebugManagedCallback2::DestroyConnection 方法</span><span class="sxs-lookup"><span data-stu-id="f50c8-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>
<span data-ttu-id="f50c8-103">通知调试器指定的连接已终止。</span><span class="sxs-lookup"><span data-stu-id="f50c8-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f50c8-104">语法</span><span class="sxs-lookup"><span data-stu-id="f50c8-104">Syntax</span></span>  
  
```  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f50c8-105">参数</span><span class="sxs-lookup"><span data-stu-id="f50c8-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="f50c8-106">[in]指向表示包含已被销毁连接流程 ICorDebugProcess 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="f50c8-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="f50c8-107">[in]已被销毁连接的 ID。</span><span class="sxs-lookup"><span data-stu-id="f50c8-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f50c8-108">备注</span><span class="sxs-lookup"><span data-stu-id="f50c8-108">Remarks</span></span>  
 <span data-ttu-id="f50c8-109">一个`DestroyConnection`主机可调用时，将会激发回调[iclrdebugmanager:: Endconnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)中[宿主 API](../../../../docs/framework/unmanaged-api/hosting/index.md)。</span><span class="sxs-lookup"><span data-stu-id="f50c8-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f50c8-110">要求</span><span class="sxs-lookup"><span data-stu-id="f50c8-110">Requirements</span></span>  
 <span data-ttu-id="f50c8-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f50c8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f50c8-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f50c8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f50c8-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f50c8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f50c8-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f50c8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f50c8-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f50c8-115">See also</span></span>
- [<span data-ttu-id="f50c8-116">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="f50c8-116">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="f50c8-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="f50c8-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
