---
title: ICorDebugStackWalk::SetContext 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.SetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::SetContext
helpviewer_keywords:
- SetContext method [.NET Framework debugging]
- ICorDebugStackWalk::SetContext method [.NET Framework debugging]
ms.assetid: bac0b156-31a3-4e7f-be4d-ab21789c81f1
topic_type:
- apiref
ms.openlocfilehash: 23ad8882ad97e5ceaeb690dfae08a6be55b85f64
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791860"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="ce890-102">ICorDebugStackWalk::SetContext 方法</span><span class="sxs-lookup"><span data-stu-id="ce890-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="ce890-103">将[ICorDebugStackWalk](icordebugstackwalk-interface.md)对象的当前上下文设置为线程的有效上下文。</span><span class="sxs-lookup"><span data-stu-id="ce890-103">Sets the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce890-104">语法</span><span class="sxs-lookup"><span data-stu-id="ce890-104">Syntax</span></span>  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce890-105">参数</span><span class="sxs-lookup"><span data-stu-id="ce890-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="ce890-106">中[CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md)标志，用于指示上下文是否来自堆栈上的活动帧，或通过展开堆栈获取的上下文。</span><span class="sxs-lookup"><span data-stu-id="ce890-106">[in] A [CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="ce890-107">中`CONTEXT` 缓冲区的已分配大小。</span><span class="sxs-lookup"><span data-stu-id="ce890-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="ce890-108">中`CONTEXT` 缓冲区。</span><span class="sxs-lookup"><span data-stu-id="ce890-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce890-109">返回值</span><span class="sxs-lookup"><span data-stu-id="ce890-109">Return Value</span></span>  
 <span data-ttu-id="ce890-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="ce890-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ce890-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ce890-111">HRESULT</span></span>|<span data-ttu-id="ce890-112">描述</span><span class="sxs-lookup"><span data-stu-id="ce890-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ce890-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce890-113">S_OK</span></span>|<span data-ttu-id="ce890-114">已成功设置 `ICorDebugStackWalk` 对象的上下文。</span><span class="sxs-lookup"><span data-stu-id="ce890-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="ce890-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ce890-115">E_FAIL</span></span>|<span data-ttu-id="ce890-116">未设置 `ICorDebugStackWalk` 对象的上下文。</span><span class="sxs-lookup"><span data-stu-id="ce890-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="ce890-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ce890-117">E_INVALIDARG</span></span>|<span data-ttu-id="ce890-118">上下文为 null。</span><span class="sxs-lookup"><span data-stu-id="ce890-118">The context is null.</span></span>|  
|<span data-ttu-id="ce890-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="ce890-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="ce890-120">上下文缓冲区太小。</span><span class="sxs-lookup"><span data-stu-id="ce890-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="ce890-121">异常</span><span class="sxs-lookup"><span data-stu-id="ce890-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce890-122">备注</span><span class="sxs-lookup"><span data-stu-id="ce890-122">Remarks</span></span>  
 <span data-ttu-id="ce890-123">此方法不会更改线程的当前上下文。</span><span class="sxs-lookup"><span data-stu-id="ce890-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="ce890-124">将当前上下文设置为无效上下文可能会导致堆栈查看程序产生不可预知的结果。</span><span class="sxs-lookup"><span data-stu-id="ce890-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="ce890-125">可以通过立即调用[ICorDebugStackWalk：： GetContext](icordebugstackwalk-getcontext-method.md)方法来检索此上下文的精确按位副本。</span><span class="sxs-lookup"><span data-stu-id="ce890-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce890-126">需求</span><span class="sxs-lookup"><span data-stu-id="ce890-126">Requirements</span></span>  
 <span data-ttu-id="ce890-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ce890-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce890-128">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce890-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce890-129">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce890-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce890-130">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce890-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce890-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce890-131">See also</span></span>

- [<span data-ttu-id="ce890-132">调试接口</span><span class="sxs-lookup"><span data-stu-id="ce890-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ce890-133">调试</span><span class="sxs-lookup"><span data-stu-id="ce890-133">Debugging</span></span>](index.md)
