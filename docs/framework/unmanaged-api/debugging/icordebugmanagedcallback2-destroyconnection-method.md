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
ms.openlocfilehash: 4f6940f863504a9aedd9539e121c7b3791f746b9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788306"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="39686-102">ICorDebugManagedCallback2::DestroyConnection 方法</span><span class="sxs-lookup"><span data-stu-id="39686-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>
<span data-ttu-id="39686-103">通知调试器指定的连接已终止。</span><span class="sxs-lookup"><span data-stu-id="39686-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39686-104">语法</span><span class="sxs-lookup"><span data-stu-id="39686-104">Syntax</span></span>  
  
```cpp  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39686-105">参数</span><span class="sxs-lookup"><span data-stu-id="39686-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="39686-106">中指向 ICorDebugProcess 对象的指针，该对象表示包含已销毁的连接的进程。</span><span class="sxs-lookup"><span data-stu-id="39686-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="39686-107">中已销毁的连接的 ID。</span><span class="sxs-lookup"><span data-stu-id="39686-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39686-108">备注</span><span class="sxs-lookup"><span data-stu-id="39686-108">Remarks</span></span>  
 <span data-ttu-id="39686-109">当主机调用[宿主 API](../../../../docs/framework/unmanaged-api/hosting/index.md)中的[ICLRDebugManager：： EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)时，将激发 `DestroyConnection` 回调。</span><span class="sxs-lookup"><span data-stu-id="39686-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39686-110">需求</span><span class="sxs-lookup"><span data-stu-id="39686-110">Requirements</span></span>  
 <span data-ttu-id="39686-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="39686-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39686-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39686-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39686-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39686-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39686-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39686-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39686-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39686-115">See also</span></span>

- [<span data-ttu-id="39686-116">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="39686-116">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="39686-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="39686-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
