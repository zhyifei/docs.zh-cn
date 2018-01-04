---
title: "ICorDebugProcess::GetHelperThreadID 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.GetHelperThreadID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 03e801cb58b8f5c3f658085fcee4288278e545c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessgethelperthreadid-method"></a><span data-ttu-id="c96af-102">ICorDebugProcess::GetHelperThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="c96af-102">ICorDebugProcess::GetHelperThreadID Method</span></span>
<span data-ttu-id="c96af-103">获取调试器的内部帮助程序线程的操作系统 (OS) 线程 ID。</span><span class="sxs-lookup"><span data-stu-id="c96af-103">Gets the operating system (OS) thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c96af-104">语法</span><span class="sxs-lookup"><span data-stu-id="c96af-104">Syntax</span></span>  
  
```  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c96af-105">参数</span><span class="sxs-lookup"><span data-stu-id="c96af-105">Parameters</span></span>  
 `pThreadID`  
 <span data-ttu-id="c96af-106">[out]指向操作系统线程的调试器的内部帮助程序线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="c96af-106">[out] A pointer to the OS thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c96af-107">备注</span><span class="sxs-lookup"><span data-stu-id="c96af-107">Remarks</span></span>  
 <span data-ttu-id="c96af-108">托管和非托管在调试期间，它将由调试器的负责确保具有指定 ID 的线程保持运行，如果它达到由调试器放置一个断点。</span><span class="sxs-lookup"><span data-stu-id="c96af-108">During managed and unmanaged debugging, it is the debugger's responsibility to ensure that the thread with the specified ID remains running if it hits a breakpoint placed by the debugger.</span></span> <span data-ttu-id="c96af-109">调试器还可能想要隐藏用户此线程。</span><span class="sxs-lookup"><span data-stu-id="c96af-109">A debugger may also wish to hide this thread from the user.</span></span> <span data-ttu-id="c96af-110">如果没有帮助程序线程存在于进程中尚未，`GetHelperThreadID`方法返回零 *`pThreadID`。</span><span class="sxs-lookup"><span data-stu-id="c96af-110">If no helper thread exists in the process yet, the `GetHelperThreadID` method returns zero in *`pThreadID`.</span></span>  
  
 <span data-ttu-id="c96af-111">无法缓存帮助程序线程的线程 ID，因为它可能会随着时间的推移进行更改。</span><span class="sxs-lookup"><span data-stu-id="c96af-111">You cannot cache the thread ID of the helper thread, because it may change over time.</span></span> <span data-ttu-id="c96af-112">你必须重新查询每次发生停止事件的线程 ID。</span><span class="sxs-lookup"><span data-stu-id="c96af-112">You must re-query the thread ID at every stopping event.</span></span>  
  
 <span data-ttu-id="c96af-113">将调试器的帮助程序线程的线程 ID 将正确上每个非托管[icordebugmanagedcallback:: Createthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md)事件，从而允许调试器来确定其帮助程序线程的线程 ID 和隐藏用户。</span><span class="sxs-lookup"><span data-stu-id="c96af-113">The thread ID of the debugger's helper thread will be correct on every unmanaged [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) event, thus allowing a debugger to determine the thread ID of its helper thread and hide it from the user.</span></span> <span data-ttu-id="c96af-114">在非托管过程标识为帮助程序线程的线程`ICorDebugManagedCallback::CreateThread`事件将永远不会运行托管的用户代码。</span><span class="sxs-lookup"><span data-stu-id="c96af-114">A thread that is identified as a helper thread during an unmanaged `ICorDebugManagedCallback::CreateThread` event will never run managed user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c96af-115">惠?</span><span class="sxs-lookup"><span data-stu-id="c96af-115">Requirements</span></span>  
 <span data-ttu-id="c96af-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c96af-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c96af-117">**标头：** CorDebug.idl。</span><span class="sxs-lookup"><span data-stu-id="c96af-117">**Header:** CorDebug.idl.</span></span> <span data-ttu-id="c96af-118">CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c96af-118">CorDebug.h</span></span>  
  
 <span data-ttu-id="c96af-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c96af-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c96af-120">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c96af-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
