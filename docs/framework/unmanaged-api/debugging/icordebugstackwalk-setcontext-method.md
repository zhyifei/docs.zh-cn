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
ms.openlocfilehash: 90156152a2c133446dedbe22426785ab63f8dfb9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131816"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="5e7f4-102">ICorDebugStackWalk::SetContext 方法</span><span class="sxs-lookup"><span data-stu-id="5e7f4-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="5e7f4-103">将[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)对象的当前上下文设置为线程的有效上下文。</span><span class="sxs-lookup"><span data-stu-id="5e7f4-103">Sets the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e7f4-104">语法</span><span class="sxs-lookup"><span data-stu-id="5e7f4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e7f4-105">参数</span><span class="sxs-lookup"><span data-stu-id="5e7f4-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="5e7f4-106">中[CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md)标志，用于指示上下文是否来自堆栈上的活动帧，或通过展开堆栈获取的上下文。</span><span class="sxs-lookup"><span data-stu-id="5e7f4-106">[in] A [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="5e7f4-107">中`CONTEXT` 缓冲区的已分配大小。</span><span class="sxs-lookup"><span data-stu-id="5e7f4-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="5e7f4-108">中`CONTEXT` 缓冲区。</span><span class="sxs-lookup"><span data-stu-id="5e7f4-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e7f4-109">返回值</span><span class="sxs-lookup"><span data-stu-id="5e7f4-109">Return Value</span></span>  
 <span data-ttu-id="5e7f4-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="5e7f4-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5e7f4-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5e7f4-111">HRESULT</span></span>|<span data-ttu-id="5e7f4-112">描述</span><span class="sxs-lookup"><span data-stu-id="5e7f4-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5e7f4-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="5e7f4-113">S_OK</span></span>|<span data-ttu-id="5e7f4-114">已成功设置 `ICorDebugStackWalk` 对象的上下文。</span><span class="sxs-lookup"><span data-stu-id="5e7f4-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="5e7f4-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5e7f4-115">E_FAIL</span></span>|<span data-ttu-id="5e7f4-116">未设置 `ICorDebugStackWalk` 对象的上下文。</span><span class="sxs-lookup"><span data-stu-id="5e7f4-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="5e7f4-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="5e7f4-117">E_INVALIDARG</span></span>|<span data-ttu-id="5e7f4-118">上下文为 null。</span><span class="sxs-lookup"><span data-stu-id="5e7f4-118">The context is null.</span></span>|  
|<span data-ttu-id="5e7f4-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="5e7f4-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="5e7f4-120">上下文缓冲区太小。</span><span class="sxs-lookup"><span data-stu-id="5e7f4-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="5e7f4-121">异常</span><span class="sxs-lookup"><span data-stu-id="5e7f4-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e7f4-122">备注</span><span class="sxs-lookup"><span data-stu-id="5e7f4-122">Remarks</span></span>  
 <span data-ttu-id="5e7f4-123">此方法不会更改线程的当前上下文。</span><span class="sxs-lookup"><span data-stu-id="5e7f4-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="5e7f4-124">将当前上下文设置为无效上下文可能会导致堆栈查看程序产生不可预知的结果。</span><span class="sxs-lookup"><span data-stu-id="5e7f4-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="5e7f4-125">可以通过立即调用[ICorDebugStackWalk：： GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)方法来检索此上下文的精确按位副本。</span><span class="sxs-lookup"><span data-stu-id="5e7f4-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e7f4-126">要求</span><span class="sxs-lookup"><span data-stu-id="5e7f4-126">Requirements</span></span>  
 <span data-ttu-id="5e7f4-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5e7f4-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e7f4-128">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e7f4-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e7f4-129">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e7f4-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e7f4-130">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e7f4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e7f4-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e7f4-131">See also</span></span>

- [<span data-ttu-id="5e7f4-132">调试接口</span><span class="sxs-lookup"><span data-stu-id="5e7f4-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="5e7f4-133">调试</span><span class="sxs-lookup"><span data-stu-id="5e7f4-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
