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
ms.openlocfilehash: 51d34e68851bc6a60d25f643f63d112396abdc4e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209066"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="30950-102">ICorDebugManagedCallback2::CreateConnection 方法</span><span class="sxs-lookup"><span data-stu-id="30950-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="30950-103">通知调试器已创建新连接。</span><span class="sxs-lookup"><span data-stu-id="30950-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30950-104">语法</span><span class="sxs-lookup"><span data-stu-id="30950-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30950-105">参数</span><span class="sxs-lookup"><span data-stu-id="30950-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="30950-106">中一个指向 "ICorDebugProcess" 对象的指针，该对象表示在其中创建连接的进程</span><span class="sxs-lookup"><span data-stu-id="30950-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="30950-107">中新连接的 ID。</span><span class="sxs-lookup"><span data-stu-id="30950-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="30950-108">中指向新连接名称的指针。</span><span class="sxs-lookup"><span data-stu-id="30950-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30950-109">备注</span><span class="sxs-lookup"><span data-stu-id="30950-109">Remarks</span></span>  
 <span data-ttu-id="30950-110">`CreateConnection`在以下任一情况下，都将激发回调：</span><span class="sxs-lookup"><span data-stu-id="30950-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="30950-111">调试器附加到包含连接的进程时。</span><span class="sxs-lookup"><span data-stu-id="30950-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="30950-112">在这种情况下，运行时将 `CreateConnection` 为进程中的每个连接生成并调度一个事件和一个[ICorDebugManagedCallback2：： ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md)事件。</span><span class="sxs-lookup"><span data-stu-id="30950-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
- <span data-ttu-id="30950-113">当主机在[托管 API](../hosting/index.md)中调用[ICLRDebugManager：： BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)时。</span><span class="sxs-lookup"><span data-stu-id="30950-113">When a host calls [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30950-114">要求</span><span class="sxs-lookup"><span data-stu-id="30950-114">Requirements</span></span>  
 <span data-ttu-id="30950-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="30950-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30950-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30950-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30950-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30950-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30950-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30950-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30950-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="30950-119">See also</span></span>

- [<span data-ttu-id="30950-120">ICorDebugManagedCallback2 接口</span><span class="sxs-lookup"><span data-stu-id="30950-120">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="30950-121">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="30950-121">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
