---
title: "ICorDebugProcess::SetThreadContext 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugProcess.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a7d40d455ea17b8df2acd77a1222ac6b080116c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocesssetthreadcontext-method"></a><span data-ttu-id="e707b-102">ICorDebugProcess::SetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="e707b-102">ICorDebugProcess::SetThreadContext Method</span></span>
<span data-ttu-id="e707b-103">在此过程中设置给定线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="e707b-103">Sets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e707b-104">语法</span><span class="sxs-lookup"><span data-stu-id="e707b-104">Syntax</span></span>  
  
```  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e707b-105">参数</span><span class="sxs-lookup"><span data-stu-id="e707b-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="e707b-106">[in]为其设置上下文线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="e707b-106">[in] The ID of the thread for which to set the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="e707b-107">[in] `context` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="e707b-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="e707b-108">[in]描述线程的上下文的字节数组。</span><span class="sxs-lookup"><span data-stu-id="e707b-108">[in] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="e707b-109">上下文指定在其执行线程的处理器的体系结构。</span><span class="sxs-lookup"><span data-stu-id="e707b-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e707b-110">备注</span><span class="sxs-lookup"><span data-stu-id="e707b-110">Remarks</span></span>  
 <span data-ttu-id="e707b-111">调试器应调用此方法，而不是 Win32`SetThreadContext`函数，因为线程实际上可能是处于"被劫持"状态，在其中其上下文已被暂时更改。</span><span class="sxs-lookup"><span data-stu-id="e707b-111">The debugger should call this method rather than the Win32 `SetThreadContext` function, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="e707b-112">只有当线程处于本机代码时，应使用此方法。</span><span class="sxs-lookup"><span data-stu-id="e707b-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="e707b-113">使用[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)托管代码中的线程。</span><span class="sxs-lookup"><span data-stu-id="e707b-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) for threads in managed code.</span></span> <span data-ttu-id="e707b-114">你应从不需要以在带外 (OOB) 调试事件期间修改的线程上下文。</span><span class="sxs-lookup"><span data-stu-id="e707b-114">You should never need to modify the context of a thread during an out-of-band (OOB) debug event.</span></span>  
  
 <span data-ttu-id="e707b-115">传递的数据必须是当前平台的上下文结构。</span><span class="sxs-lookup"><span data-stu-id="e707b-115">The data passed must be a context structure for the current platform.</span></span>  
  
 <span data-ttu-id="e707b-116">如果使用不正确，此方法会损坏运行时。</span><span class="sxs-lookup"><span data-stu-id="e707b-116">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e707b-117">惠?</span><span class="sxs-lookup"><span data-stu-id="e707b-117">Requirements</span></span>  
 <span data-ttu-id="e707b-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e707b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e707b-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e707b-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e707b-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e707b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e707b-121">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e707b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
