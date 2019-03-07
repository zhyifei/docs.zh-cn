---
title: ICorDebugController::Continue 方法
ms.date: 03/30/2017
api_name:
- ICorDebugController.Continue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f448a0383d3ad121cbddb59e13acef46a336261
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485728"
---
# <a name="icordebugcontrollercontinue-method"></a><span data-ttu-id="0d166-102">ICorDebugController::Continue 方法</span><span class="sxs-lookup"><span data-stu-id="0d166-102">ICorDebugController::Continue Method</span></span>
<span data-ttu-id="0d166-103">恢复托管线程执行后调用[停止方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)。</span><span class="sxs-lookup"><span data-stu-id="0d166-103">Resumes execution of managed threads after a call to [Stop Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d166-104">语法</span><span class="sxs-lookup"><span data-stu-id="0d166-104">Syntax</span></span>  
  
```  
HRESULT Continue (  
    [in] BOOL fIsOutOfBand  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d166-105">参数</span><span class="sxs-lookup"><span data-stu-id="0d166-105">Parameters</span></span>  
 `fIsOutOfBand`  
 <span data-ttu-id="0d166-106">[in]设置为`true`如果继续从带外事件; 否则设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="0d166-106">[in] Set to `true` if continuing from an out-of-band event; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d166-107">备注</span><span class="sxs-lookup"><span data-stu-id="0d166-107">Remarks</span></span>  
 <span data-ttu-id="0d166-108">`Continue` 在调用后继续执行过程`ICorDebugController::Stop`方法。</span><span class="sxs-lookup"><span data-stu-id="0d166-108">`Continue` continues the process after a call to the `ICorDebugController::Stop` method.</span></span>  
  
 <span data-ttu-id="0d166-109">在进行混合模式调试时，不要调用`Continue`上 Win32 事件线程除非您要从带外事件继续执行。</span><span class="sxs-lookup"><span data-stu-id="0d166-109">When doing mixed-mode debugging, do not call `Continue` on the Win32 event thread unless you are continuing from an out-of-band event.</span></span>  
  
 <span data-ttu-id="0d166-110">*带内事件*托管的事件或正常非托管事件，在此期间，调试器支持与托管进程的状态的交互事件。</span><span class="sxs-lookup"><span data-stu-id="0d166-110">An *in-band event* is either a managed event or a normal unmanaged event during which the debugger supports interaction with the managed state of the process.</span></span> <span data-ttu-id="0d166-111">在这种情况下，调试器将接收[icordebugunmanagedcallback:: Debugevent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md)具有回调其`fOutOfBand`参数设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="0d166-111">In this case, the debugger receives the [ICorDebugUnmanagedCallback::DebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) callback with its `fOutOfBand` parameter set to `false`.</span></span>  
  
 <span data-ttu-id="0d166-112">*的带事件*是在此期间与托管状态的进程的交互是不可能同时由于事件停止该进程的非托管的事件。</span><span class="sxs-lookup"><span data-stu-id="0d166-112">An *out-of-band event* is an unmanaged event during which interaction with the managed state of the process is impossible while the process is stopped due to the event.</span></span> <span data-ttu-id="0d166-113">在这种情况下，调试器将接收`ICorDebugUnmanagedCallback::DebugEvent`具有回调其`fOutOfBand`参数设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="0d166-113">In this case, the debugger receives the `ICorDebugUnmanagedCallback::DebugEvent` callback with its `fOutOfBand` parameter set to `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d166-114">要求</span><span class="sxs-lookup"><span data-stu-id="0d166-114">Requirements</span></span>  
 <span data-ttu-id="0d166-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0d166-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d166-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d166-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d166-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d166-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d166-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d166-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d166-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="0d166-119">See also</span></span>

