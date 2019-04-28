---
title: ICorDebugController::Stop 方法
ms.date: 03/30/2017
api_name:
- ICorDebugController.Stop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 724db8c5c8dbb5bf3ff8bc7202a60397180b7b38
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749055"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="2f867-102">ICorDebugController::Stop 方法</span><span class="sxs-lookup"><span data-stu-id="2f867-102">ICorDebugController::Stop Method</span></span>
<span data-ttu-id="2f867-103">执行所有线程上的进程中运行托管的代码的同时停止。</span><span class="sxs-lookup"><span data-stu-id="2f867-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f867-104">语法</span><span class="sxs-lookup"><span data-stu-id="2f867-104">Syntax</span></span>  
  
```  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f867-105">参数</span><span class="sxs-lookup"><span data-stu-id="2f867-105">Parameters</span></span>  
 `dwTimeoutIgnored`  
 <span data-ttu-id="2f867-106">未使用。</span><span class="sxs-lookup"><span data-stu-id="2f867-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f867-107">备注</span><span class="sxs-lookup"><span data-stu-id="2f867-107">Remarks</span></span>  
 <span data-ttu-id="2f867-108">`Stop` 在进程中执行的同时停止对所有线程运行托管代码。</span><span class="sxs-lookup"><span data-stu-id="2f867-108">`Stop` performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="2f867-109">仅托管调试会话期间，非托管的线程可以继续运行 （但在尝试调用托管的代码时会被阻止）。</span><span class="sxs-lookup"><span data-stu-id="2f867-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="2f867-110">在互操作调试会话，非托管的线程也会停止。</span><span class="sxs-lookup"><span data-stu-id="2f867-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="2f867-111">`dwTimeoutIgnored`值当前被忽略，视为 INFINITE (-1)。</span><span class="sxs-lookup"><span data-stu-id="2f867-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="2f867-112">如果同时停止失败由于死锁，所有线程已都暂停，并返回 E_TIMEOUT。</span><span class="sxs-lookup"><span data-stu-id="2f867-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f867-113">`Stop` 是唯一的同步方法调试 API 中。</span><span class="sxs-lookup"><span data-stu-id="2f867-113">`Stop` is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="2f867-114">当`Stop`时返回 S_OK，该过程已停止。</span><span class="sxs-lookup"><span data-stu-id="2f867-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="2f867-115">不执行回调都在通知停止点的侦听器。</span><span class="sxs-lookup"><span data-stu-id="2f867-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="2f867-116">调试器必须调用[icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)以允许恢复的过程。</span><span class="sxs-lookup"><span data-stu-id="2f867-116">The debugger must call [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="2f867-117">调试器会维护一个停止的计数器。</span><span class="sxs-lookup"><span data-stu-id="2f867-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="2f867-118">当计数器回到零时，控制器将继续运行。</span><span class="sxs-lookup"><span data-stu-id="2f867-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="2f867-119">每次调用`Stop`或每次调度的回调递增的计数器。</span><span class="sxs-lookup"><span data-stu-id="2f867-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="2f867-120">每次调用`ICorDebugController::Continue`递减该计数器。</span><span class="sxs-lookup"><span data-stu-id="2f867-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f867-121">要求</span><span class="sxs-lookup"><span data-stu-id="2f867-121">Requirements</span></span>  
 <span data-ttu-id="2f867-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2f867-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f867-123">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f867-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f867-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f867-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f867-125">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f867-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f867-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f867-126">See also</span></span>
