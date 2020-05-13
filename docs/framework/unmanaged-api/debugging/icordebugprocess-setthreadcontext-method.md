---
title: ICorDebugProcess::SetThreadContext 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: c9e403dc8cbb75a1e93c426a9e0b3a2083f1f10e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210457"
---
# <a name="icordebugprocesssetthreadcontext-method"></a><span data-ttu-id="b9354-102">ICorDebugProcess::SetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="b9354-102">ICorDebugProcess::SetThreadContext Method</span></span>
<span data-ttu-id="b9354-103">设置此进程中给定线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="b9354-103">Sets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9354-104">语法</span><span class="sxs-lookup"><span data-stu-id="b9354-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9354-105">参数</span><span class="sxs-lookup"><span data-stu-id="b9354-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="b9354-106">中要为其设置上下文的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="b9354-106">[in] The ID of the thread for which to set the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="b9354-107">[in] `context` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="b9354-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="b9354-108">中用于描述线程上下文的字节数组。</span><span class="sxs-lookup"><span data-stu-id="b9354-108">[in] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="b9354-109">上下文指定正在执行线程的处理器的体系结构。</span><span class="sxs-lookup"><span data-stu-id="b9354-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9354-110">备注</span><span class="sxs-lookup"><span data-stu-id="b9354-110">Remarks</span></span>  
 <span data-ttu-id="b9354-111">调试器应调用此方法而不是 Win32 `SetThreadContext` 函数，因为该线程实际可能处于 "被劫持" 状态，在该状态下，其上下文已暂时更改。</span><span class="sxs-lookup"><span data-stu-id="b9354-111">The debugger should call this method rather than the Win32 `SetThreadContext` function, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="b9354-112">仅当线程在本机代码中时，才应使用此方法。</span><span class="sxs-lookup"><span data-stu-id="b9354-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="b9354-113">在托管代码中对线程使用[ICorDebugRegisterSet](icordebugregisterset-interface.md) 。</span><span class="sxs-lookup"><span data-stu-id="b9354-113">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) for threads in managed code.</span></span> <span data-ttu-id="b9354-114">在带外（OOB）调试事件期间，你永远不需要修改线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="b9354-114">You should never need to modify the context of a thread during an out-of-band (OOB) debug event.</span></span>  
  
 <span data-ttu-id="b9354-115">传递的数据必须是当前平台的上下文结构。</span><span class="sxs-lookup"><span data-stu-id="b9354-115">The data passed must be a context structure for the current platform.</span></span>  
  
 <span data-ttu-id="b9354-116">如果使用不当，此方法可能会损坏运行时。</span><span class="sxs-lookup"><span data-stu-id="b9354-116">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9354-117">要求</span><span class="sxs-lookup"><span data-stu-id="b9354-117">Requirements</span></span>  
 <span data-ttu-id="b9354-118">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b9354-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9354-119">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9354-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9354-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9354-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9354-121">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9354-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
