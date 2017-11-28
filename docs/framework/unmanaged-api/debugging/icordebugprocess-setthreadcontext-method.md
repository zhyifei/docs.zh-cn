---
title: "ICorDebugProcess::SetThreadContext 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.SetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 70368602672e06dc3a5aaf4f2f4bc7632c5a9a79
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocesssetthreadcontext-method"></a><span data-ttu-id="e28bb-102">ICorDebugProcess::SetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="e28bb-102">ICorDebugProcess::SetThreadContext Method</span></span>
<span data-ttu-id="e28bb-103">在此过程中设置给定线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="e28bb-103">Sets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e28bb-104">语法</span><span class="sxs-lookup"><span data-stu-id="e28bb-104">Syntax</span></span>  
  
```  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e28bb-105">参数</span><span class="sxs-lookup"><span data-stu-id="e28bb-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="e28bb-106">[in]为其设置上下文线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="e28bb-106">[in] The ID of the thread for which to set the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="e28bb-107">[in] `context` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="e28bb-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="e28bb-108">[in]描述线程的上下文的字节数组。</span><span class="sxs-lookup"><span data-stu-id="e28bb-108">[in] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="e28bb-109">上下文指定在其执行线程的处理器的体系结构。</span><span class="sxs-lookup"><span data-stu-id="e28bb-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e28bb-110">备注</span><span class="sxs-lookup"><span data-stu-id="e28bb-110">Remarks</span></span>  
 <span data-ttu-id="e28bb-111">调试器应调用此方法，而不是 Win32`SetThreadContext`函数，因为线程实际上可能是处于"被劫持"状态，在其中其上下文已被暂时更改。</span><span class="sxs-lookup"><span data-stu-id="e28bb-111">The debugger should call this method rather than the Win32 `SetThreadContext` function, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="e28bb-112">只有当线程处于本机代码时，应使用此方法。</span><span class="sxs-lookup"><span data-stu-id="e28bb-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="e28bb-113">使用[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)托管代码中的线程。</span><span class="sxs-lookup"><span data-stu-id="e28bb-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) for threads in managed code.</span></span> <span data-ttu-id="e28bb-114">你应从不需要以在带外 (OOB) 调试事件期间修改的线程上下文。</span><span class="sxs-lookup"><span data-stu-id="e28bb-114">You should never need to modify the context of a thread during an out-of-band (OOB) debug event.</span></span>  
  
 <span data-ttu-id="e28bb-115">传递的数据必须是当前平台的上下文结构。</span><span class="sxs-lookup"><span data-stu-id="e28bb-115">The data passed must be a context structure for the current platform.</span></span>  
  
 <span data-ttu-id="e28bb-116">如果使用不正确，此方法会损坏运行时。</span><span class="sxs-lookup"><span data-stu-id="e28bb-116">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e28bb-117">要求</span><span class="sxs-lookup"><span data-stu-id="e28bb-117">Requirements</span></span>  
 <span data-ttu-id="e28bb-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e28bb-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e28bb-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e28bb-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e28bb-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e28bb-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e28bb-121">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e28bb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
