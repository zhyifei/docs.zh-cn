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
ms.openlocfilehash: 62e2be44165472e2fbf368f61b865d39a5e9fc28
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395469"
---
# <a name="icordebugcontrollercontinue-method"></a><span data-ttu-id="be24c-102">ICorDebugController::Continue 方法</span><span class="sxs-lookup"><span data-stu-id="be24c-102">ICorDebugController::Continue Method</span></span>

<span data-ttu-id="be24c-103">在调用[Stop 方法](icordebugcontroller-stop-method.md)后继续执行托管线程。</span><span class="sxs-lookup"><span data-stu-id="be24c-103">Resumes execution of managed threads after a call to [Stop Method](icordebugcontroller-stop-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="be24c-104">语法</span><span class="sxs-lookup"><span data-stu-id="be24c-104">Syntax</span></span>

```cpp
HRESULT Continue (
    [in] BOOL fIsOutOfBand
);
```

## <a name="parameters"></a><span data-ttu-id="be24c-105">参数</span><span class="sxs-lookup"><span data-stu-id="be24c-105">Parameters</span></span>

`fIsOutOfBand`  
<span data-ttu-id="be24c-106">中如果从带外事件继续，则设置为 `true`;否则，设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="be24c-106">[in] Set to `true` if continuing from an out-of-band event; otherwise, set to `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="be24c-107">备注</span><span class="sxs-lookup"><span data-stu-id="be24c-107">Remarks</span></span>

<span data-ttu-id="be24c-108">@no__t 在调用 `ICorDebugController::Stop` 方法后继续执行此过程。</span><span class="sxs-lookup"><span data-stu-id="be24c-108">`Continue` continues the process after a call to the `ICorDebugController::Stop` method.</span></span>

<span data-ttu-id="be24c-109">执行混合模式调试时，请不要在 Win32 事件线程上调用 `Continue`，除非从带外事件继续。</span><span class="sxs-lookup"><span data-stu-id="be24c-109">When doing mixed-mode debugging, do not call `Continue` on the Win32 event thread unless you are continuing from an out-of-band event.</span></span>

<span data-ttu-id="be24c-110">*带内事件*是托管事件或普通非托管事件，在此期间，调试器支持与进程的托管状态交互。</span><span class="sxs-lookup"><span data-stu-id="be24c-110">An *in-band event* is either a managed event or a normal unmanaged event during which the debugger supports interaction with the managed state of the process.</span></span> <span data-ttu-id="be24c-111">在这种情况下，调试器接收[ICorDebugUnmanagedCallback：:D ebugevent](icordebugunmanagedcallback-debugevent-method.md)回调，并将其 @no__t 参数设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="be24c-111">In this case, the debugger receives the [ICorDebugUnmanagedCallback::DebugEvent](icordebugunmanagedcallback-debugevent-method.md) callback with its `fOutOfBand` parameter set to `false`.</span></span>

<span data-ttu-id="be24c-112">带*外事件*是一种非托管事件，在此过程中，由于发生事件，进程停止时无法与进程的托管状态交互。</span><span class="sxs-lookup"><span data-stu-id="be24c-112">An *out-of-band event* is an unmanaged event during which interaction with the managed state of the process is impossible while the process is stopped due to the event.</span></span> <span data-ttu-id="be24c-113">在这种情况下，调试器接收到 `ICorDebugUnmanagedCallback::DebugEvent` 回调，其 @no__t 参数设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="be24c-113">In this case, the debugger receives the `ICorDebugUnmanagedCallback::DebugEvent` callback with its `fOutOfBand` parameter set to `true`.</span></span>

## <a name="requirements"></a><span data-ttu-id="be24c-114">要求</span><span class="sxs-lookup"><span data-stu-id="be24c-114">Requirements</span></span>

<span data-ttu-id="be24c-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="be24c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="be24c-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be24c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="be24c-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be24c-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="be24c-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be24c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
