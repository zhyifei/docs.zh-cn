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
ms.openlocfilehash: 2cd0fc9f86515d63533275002301eb47f11feebb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411261"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="968c5-102">ICorDebugController::Stop 方法</span><span class="sxs-lookup"><span data-stu-id="968c5-102">ICorDebugController::Stop Method</span></span>
<span data-ttu-id="968c5-103">在进程中运行托管的代码的所有线程上执行协作停止。</span><span class="sxs-lookup"><span data-stu-id="968c5-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="968c5-104">语法</span><span class="sxs-lookup"><span data-stu-id="968c5-104">Syntax</span></span>  
  
```  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="968c5-105">参数</span><span class="sxs-lookup"><span data-stu-id="968c5-105">Parameters</span></span>  
 `dwTimeoutIgnored`  
 <span data-ttu-id="968c5-106">未使用。</span><span class="sxs-lookup"><span data-stu-id="968c5-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="968c5-107">备注</span><span class="sxs-lookup"><span data-stu-id="968c5-107">Remarks</span></span>  
 <span data-ttu-id="968c5-108">`Stop` 在进程中执行的协作停止运行的所有线程上托管代码。</span><span class="sxs-lookup"><span data-stu-id="968c5-108">`Stop` performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="968c5-109">仅托管调试会话期间，非托管的线程可能会继续运行 （但在尝试调用托管的代码时会被阻止）。</span><span class="sxs-lookup"><span data-stu-id="968c5-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="968c5-110">互操作调试会话，在非托管的线程也会停止。</span><span class="sxs-lookup"><span data-stu-id="968c5-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="968c5-111">`dwTimeoutIgnored`值是当前忽略并且视为 INFINITE (-1)。</span><span class="sxs-lookup"><span data-stu-id="968c5-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="968c5-112">如果协作停止失败。 由于死锁，所有线程均会都挂起，并返回 E_TIMEOUT。</span><span class="sxs-lookup"><span data-stu-id="968c5-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="968c5-113">`Stop` 是调试 API 中的仅同步方法。</span><span class="sxs-lookup"><span data-stu-id="968c5-113">`Stop` is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="968c5-114">当`Stop`返回 S_OK，进程已停止。</span><span class="sxs-lookup"><span data-stu-id="968c5-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="968c5-115">不执行回调提供通知停止点的侦听器。</span><span class="sxs-lookup"><span data-stu-id="968c5-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="968c5-116">调试器必须调用[icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)以允许恢复的过程。</span><span class="sxs-lookup"><span data-stu-id="968c5-116">The debugger must call [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="968c5-117">调试器维护停止计数器。</span><span class="sxs-lookup"><span data-stu-id="968c5-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="968c5-118">在计数器变为零时，控制器将继续运行。</span><span class="sxs-lookup"><span data-stu-id="968c5-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="968c5-119">每次调用`Stop`或每次调度的回调递增的计数器。</span><span class="sxs-lookup"><span data-stu-id="968c5-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="968c5-120">每次调用`ICorDebugController::Continue`递减计数器。</span><span class="sxs-lookup"><span data-stu-id="968c5-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="968c5-121">要求</span><span class="sxs-lookup"><span data-stu-id="968c5-121">Requirements</span></span>  
 <span data-ttu-id="968c5-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="968c5-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="968c5-123">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="968c5-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="968c5-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="968c5-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="968c5-125">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="968c5-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="968c5-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="968c5-126">See Also</span></span>  
 
