---
title: "ICorDebugManagedCallback2::DestroyConnection 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.DestroyConnection
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::DestroyConnection
helpviewer_keywords:
- DestroyConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::DestroyConnection method [.NET Framework debugging]
ms.assetid: cf7940e9-4558-4319-925c-09f6c98c8fcd
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9d87f3c57e72c567be582ba2ac78589fa2e3357
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="8eb2e-102">ICorDebugManagedCallback2::DestroyConnection 方法</span><span class="sxs-lookup"><span data-stu-id="8eb2e-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>
<span data-ttu-id="8eb2e-103">通知调试器已终止指定的连接。</span><span class="sxs-lookup"><span data-stu-id="8eb2e-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eb2e-104">语法</span><span class="sxs-lookup"><span data-stu-id="8eb2e-104">Syntax</span></span>  
  
```  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8eb2e-105">参数</span><span class="sxs-lookup"><span data-stu-id="8eb2e-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="8eb2e-106">[in]指向一个表示包含了已被破坏的连接的过程的 ICorDebugProcess 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="8eb2e-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="8eb2e-107">[in]已被销毁，连接的 ID。</span><span class="sxs-lookup"><span data-stu-id="8eb2e-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8eb2e-108">备注</span><span class="sxs-lookup"><span data-stu-id="8eb2e-108">Remarks</span></span>  
 <span data-ttu-id="8eb2e-109">A`DestroyConnection`在主机可调用时，将触发回调[iclrdebugmanager:: Endconnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)中[承载 API](../../../../docs/framework/unmanaged-api/hosting/index.md)。</span><span class="sxs-lookup"><span data-stu-id="8eb2e-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8eb2e-110">惠?</span><span class="sxs-lookup"><span data-stu-id="8eb2e-110">Requirements</span></span>  
 <span data-ttu-id="8eb2e-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8eb2e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8eb2e-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8eb2e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8eb2e-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8eb2e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8eb2e-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8eb2e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eb2e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="8eb2e-115">See Also</span></span>  
 [<span data-ttu-id="8eb2e-116">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="8eb2e-116">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="8eb2e-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="8eb2e-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
