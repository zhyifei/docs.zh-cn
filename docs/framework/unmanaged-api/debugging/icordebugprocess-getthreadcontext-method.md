---
title: "ICorDebugProcess::GetThreadContext 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.GetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::GetThreadContext
helpviewer_keywords:
- ICorDebugProcess::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: 5b132ef1-8d4b-4525-89b3-54123596c194
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9cb2b0be2954c041b364f9c85c40570a9f04421f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessgetthreadcontext-method"></a><span data-ttu-id="a130b-102">ICorDebugProcess::GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="a130b-102">ICorDebugProcess::GetThreadContext Method</span></span>
<span data-ttu-id="a130b-103">获取此进程中给定的线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="a130b-103">Gets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a130b-104">语法</span><span class="sxs-lookup"><span data-stu-id="a130b-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a130b-105">参数</span><span class="sxs-lookup"><span data-stu-id="a130b-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="a130b-106">[in]为其检索上下文线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="a130b-106">[in] The ID of the thread for which to retrieve the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="a130b-107">[in] `context` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="a130b-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="a130b-108">[在中，out]描述线程的上下文的字节数组。</span><span class="sxs-lookup"><span data-stu-id="a130b-108">[in, out] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="a130b-109">上下文指定在其执行线程的处理器的体系结构。</span><span class="sxs-lookup"><span data-stu-id="a130b-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a130b-110">备注</span><span class="sxs-lookup"><span data-stu-id="a130b-110">Remarks</span></span>  
 <span data-ttu-id="a130b-111">调试器应调用此方法，而不是 Win32`GetThreadContext`方法，因为该线程可能实际上处于"被劫持"状态，在其中其上下文已被暂时更改。</span><span class="sxs-lookup"><span data-stu-id="a130b-111">The debugger should call this method rather than the Win32 `GetThreadContext` method, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="a130b-112">只有当线程处于本机代码时，应使用此方法。</span><span class="sxs-lookup"><span data-stu-id="a130b-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="a130b-113">使用[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)托管代码中的线程。</span><span class="sxs-lookup"><span data-stu-id="a130b-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) for threads in managed code.</span></span>  
  
 <span data-ttu-id="a130b-114">返回的数据是当前平台的上下文结构。</span><span class="sxs-lookup"><span data-stu-id="a130b-114">The data returned is a context structure for the current platform.</span></span> <span data-ttu-id="a130b-115">只需与 Win32`GetThreadContext`方法中，调用方应初始化`context`之前调用此方法的参数。</span><span class="sxs-lookup"><span data-stu-id="a130b-115">Just as with the Win32 `GetThreadContext` method, the caller should initialize the `context` parameter before calling this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a130b-116">要求</span><span class="sxs-lookup"><span data-stu-id="a130b-116">Requirements</span></span>  
 <span data-ttu-id="a130b-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a130b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a130b-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a130b-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a130b-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a130b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a130b-120">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a130b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
