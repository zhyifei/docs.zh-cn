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
ms.openlocfilehash: 896e797acc76e8d8034bd964e488317a62eed97b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378780"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="faed7-102">ICorDebugStackWalk::SetContext 方法</span><span class="sxs-lookup"><span data-stu-id="faed7-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="faed7-103">将[ICorDebugStackWalk](icordebugstackwalk-interface.md)对象的当前上下文设置为线程的有效上下文。</span><span class="sxs-lookup"><span data-stu-id="faed7-103">Sets the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faed7-104">语法</span><span class="sxs-lookup"><span data-stu-id="faed7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="faed7-105">参数</span><span class="sxs-lookup"><span data-stu-id="faed7-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="faed7-106">中[CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md)标志，用于指示上下文是否来自堆栈上的活动帧，或通过展开堆栈获取的上下文。</span><span class="sxs-lookup"><span data-stu-id="faed7-106">[in] A [CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="faed7-107">中缓冲区的已分配大小 `CONTEXT` 。</span><span class="sxs-lookup"><span data-stu-id="faed7-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="faed7-108">中`CONTEXT`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="faed7-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="faed7-109">返回值</span><span class="sxs-lookup"><span data-stu-id="faed7-109">Return Value</span></span>  
 <span data-ttu-id="faed7-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="faed7-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="faed7-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="faed7-111">HRESULT</span></span>|<span data-ttu-id="faed7-112">描述</span><span class="sxs-lookup"><span data-stu-id="faed7-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="faed7-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="faed7-113">S_OK</span></span>|<span data-ttu-id="faed7-114">`ICorDebugStackWalk`已成功设置对象的上下文。</span><span class="sxs-lookup"><span data-stu-id="faed7-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="faed7-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="faed7-115">E_FAIL</span></span>|<span data-ttu-id="faed7-116">`ICorDebugStackWalk`未设置对象的上下文。</span><span class="sxs-lookup"><span data-stu-id="faed7-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="faed7-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="faed7-117">E_INVALIDARG</span></span>|<span data-ttu-id="faed7-118">上下文为 null。</span><span class="sxs-lookup"><span data-stu-id="faed7-118">The context is null.</span></span>|  
|<span data-ttu-id="faed7-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="faed7-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="faed7-120">上下文缓冲区太小。</span><span class="sxs-lookup"><span data-stu-id="faed7-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="faed7-121">例外</span><span class="sxs-lookup"><span data-stu-id="faed7-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="faed7-122">备注</span><span class="sxs-lookup"><span data-stu-id="faed7-122">Remarks</span></span>  
 <span data-ttu-id="faed7-123">此方法不会更改线程的当前上下文。</span><span class="sxs-lookup"><span data-stu-id="faed7-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="faed7-124">将当前上下文设置为无效上下文可能会导致堆栈查看程序产生不可预知的结果。</span><span class="sxs-lookup"><span data-stu-id="faed7-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="faed7-125">可以通过立即调用[ICorDebugStackWalk：： GetContext](icordebugstackwalk-getcontext-method.md)方法来检索此上下文的精确按位副本。</span><span class="sxs-lookup"><span data-stu-id="faed7-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faed7-126">要求</span><span class="sxs-lookup"><span data-stu-id="faed7-126">Requirements</span></span>  
 <span data-ttu-id="faed7-127">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="faed7-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faed7-128">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="faed7-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="faed7-129">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="faed7-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="faed7-130">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faed7-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faed7-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="faed7-131">See also</span></span>

- [<span data-ttu-id="faed7-132">调试接口</span><span class="sxs-lookup"><span data-stu-id="faed7-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="faed7-133">调试</span><span class="sxs-lookup"><span data-stu-id="faed7-133">Debugging</span></span>](index.md)
