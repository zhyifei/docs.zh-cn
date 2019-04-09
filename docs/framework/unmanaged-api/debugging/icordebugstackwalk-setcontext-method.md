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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7306ee61d750ae256c93c049819a23d3d61f7297
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116462"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="c706e-102">ICorDebugStackWalk::SetContext 方法</span><span class="sxs-lookup"><span data-stu-id="c706e-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="c706e-103">集[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)到有效的线程的上下文对象的当前上下文。</span><span class="sxs-lookup"><span data-stu-id="c706e-103">Sets the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c706e-104">语法</span><span class="sxs-lookup"><span data-stu-id="c706e-104">Syntax</span></span>  
  
```  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c706e-105">参数</span><span class="sxs-lookup"><span data-stu-id="c706e-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="c706e-106">[in]一个[CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md)指示上下文是从活动堆栈帧，还是通过展开堆栈获取上下文的标志。</span><span class="sxs-lookup"><span data-stu-id="c706e-106">[in] A [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="c706e-107">[in]已分配的大小`CONTEXT`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="c706e-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="c706e-108">[in]`CONTEXT`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="c706e-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c706e-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c706e-109">Return Value</span></span>  
 <span data-ttu-id="c706e-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="c706e-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c706e-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c706e-111">HRESULT</span></span>|<span data-ttu-id="c706e-112">描述</span><span class="sxs-lookup"><span data-stu-id="c706e-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c706e-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c706e-113">S_OK</span></span>|<span data-ttu-id="c706e-114">`ICorDebugStackWalk`已成功设置对象的上下文。</span><span class="sxs-lookup"><span data-stu-id="c706e-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="c706e-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c706e-115">E_FAIL</span></span>|<span data-ttu-id="c706e-116">`ICorDebugStackWalk`未设置对象的上下文。</span><span class="sxs-lookup"><span data-stu-id="c706e-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="c706e-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c706e-117">E_INVALIDARG</span></span>|<span data-ttu-id="c706e-118">上下文为 null。</span><span class="sxs-lookup"><span data-stu-id="c706e-118">The context is null.</span></span>|  
|<span data-ttu-id="c706e-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="c706e-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="c706e-120">上下文缓冲区因过小。</span><span class="sxs-lookup"><span data-stu-id="c706e-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="c706e-121">Exceptions</span><span class="sxs-lookup"><span data-stu-id="c706e-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c706e-122">备注</span><span class="sxs-lookup"><span data-stu-id="c706e-122">Remarks</span></span>  
 <span data-ttu-id="c706e-123">此方法不会更改线程的当前上下文。</span><span class="sxs-lookup"><span data-stu-id="c706e-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="c706e-124">从堆栈查看器，将当前上下文设置为无效的上下文可能会导致不可预知的结果。</span><span class="sxs-lookup"><span data-stu-id="c706e-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="c706e-125">可以通过立即调用检索此上下文中的一个精确的按位副本[icordebugstackwalk:: Getcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="c706e-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c706e-126">要求</span><span class="sxs-lookup"><span data-stu-id="c706e-126">Requirements</span></span>  
 <span data-ttu-id="c706e-127">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c706e-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c706e-128">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c706e-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c706e-129">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c706e-129">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c706e-130">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="c706e-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c706e-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="c706e-131">See also</span></span>

- [<span data-ttu-id="c706e-132">调试接口</span><span class="sxs-lookup"><span data-stu-id="c706e-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c706e-133">调试</span><span class="sxs-lookup"><span data-stu-id="c706e-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
