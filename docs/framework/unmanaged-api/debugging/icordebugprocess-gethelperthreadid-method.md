---
title: ICorDebugProcess::GetHelperThreadID 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHelperThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type:
- apiref
ms.openlocfilehash: d38a59b23d47cbaf57dc21e121d56530a514d354
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128865"
---
# <a name="icordebugprocessgethelperthreadid-method"></a><span data-ttu-id="dbecc-102">ICorDebugProcess::GetHelperThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="dbecc-102">ICorDebugProcess::GetHelperThreadID Method</span></span>
<span data-ttu-id="dbecc-103">获取调试器的内部帮助器线程的操作系统（OS）线程 ID。</span><span class="sxs-lookup"><span data-stu-id="dbecc-103">Gets the operating system (OS) thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbecc-104">语法</span><span class="sxs-lookup"><span data-stu-id="dbecc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbecc-105">参数</span><span class="sxs-lookup"><span data-stu-id="dbecc-105">Parameters</span></span>  
 `pThreadID`  
 <span data-ttu-id="dbecc-106">弄指向调试器的内部帮助器线程的操作系统线程 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="dbecc-106">[out] A pointer to the OS thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbecc-107">备注</span><span class="sxs-lookup"><span data-stu-id="dbecc-107">Remarks</span></span>  
 <span data-ttu-id="dbecc-108">在托管和非托管调试期间，调试器负责确保具有指定 ID 的线程在命中调试器所放置的断点时保持运行状态。</span><span class="sxs-lookup"><span data-stu-id="dbecc-108">During managed and unmanaged debugging, it is the debugger's responsibility to ensure that the thread with the specified ID remains running if it hits a breakpoint placed by the debugger.</span></span> <span data-ttu-id="dbecc-109">调试器也可能希望从用户隐藏此线程。</span><span class="sxs-lookup"><span data-stu-id="dbecc-109">A debugger may also wish to hide this thread from the user.</span></span> <span data-ttu-id="dbecc-110">如果进程中尚不存在 helper 线程，则 `GetHelperThreadID` 方法将在 \*`pThreadID`中返回零。</span><span class="sxs-lookup"><span data-stu-id="dbecc-110">If no helper thread exists in the process yet, the `GetHelperThreadID` method returns zero in \*`pThreadID`.</span></span>  
  
 <span data-ttu-id="dbecc-111">不能缓存帮助器线程的线程 ID，因为它可能会随时间而改变。</span><span class="sxs-lookup"><span data-stu-id="dbecc-111">You cannot cache the thread ID of the helper thread, because it may change over time.</span></span> <span data-ttu-id="dbecc-112">必须在每次停止事件时重新查询线程 ID。</span><span class="sxs-lookup"><span data-stu-id="dbecc-112">You must re-query the thread ID at every stopping event.</span></span>  
  
 <span data-ttu-id="dbecc-113">在每个非托管[ICorDebugManagedCallback：： CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md)事件上，调试器的帮助器线程的线程 id 都是正确的，从而允许调试器确定其帮助器线程的线程 id 并将其隐藏给用户。</span><span class="sxs-lookup"><span data-stu-id="dbecc-113">The thread ID of the debugger's helper thread will be correct on every unmanaged [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) event, thus allowing a debugger to determine the thread ID of its helper thread and hide it from the user.</span></span> <span data-ttu-id="dbecc-114">在非托管 `ICorDebugManagedCallback::CreateThread` 事件期间识别为帮助器线程的线程永远不会运行托管的用户代码。</span><span class="sxs-lookup"><span data-stu-id="dbecc-114">A thread that is identified as a helper thread during an unmanaged `ICorDebugManagedCallback::CreateThread` event will never run managed user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbecc-115">要求</span><span class="sxs-lookup"><span data-stu-id="dbecc-115">Requirements</span></span>  
 <span data-ttu-id="dbecc-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dbecc-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbecc-117">**标头：** Cordebug.idl。</span><span class="sxs-lookup"><span data-stu-id="dbecc-117">**Header:** CorDebug.idl.</span></span> <span data-ttu-id="dbecc-118">Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="dbecc-118">CorDebug.h</span></span>  
  
 <span data-ttu-id="dbecc-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbecc-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbecc-120">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbecc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
