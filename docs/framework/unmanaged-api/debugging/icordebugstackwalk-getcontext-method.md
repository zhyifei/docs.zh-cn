---
title: ICorDebugStackWalk::GetContext 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bba1e6c113fb4caa0db8963e238d3eceba0cc8ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224853"
---
# <a name="icordebugstackwalkgetcontext-method"></a><span data-ttu-id="9736d-102">ICorDebugStackWalk::GetContext 方法</span><span class="sxs-lookup"><span data-stu-id="9736d-102">ICorDebugStackWalk::GetContext Method</span></span>
<span data-ttu-id="9736d-103">返回的上下文中的当前帧[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="9736d-103">Returns the context for the current frame in the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9736d-104">语法</span><span class="sxs-lookup"><span data-stu-id="9736d-104">Syntax</span></span>  
  
```  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9736d-105">参数</span><span class="sxs-lookup"><span data-stu-id="9736d-105">Parameters</span></span>  
 `contextFlags`  
 <span data-ttu-id="9736d-106">[in]指示请求 （在 WinNT.h 中定义） 的上下文缓冲区的内容的标志。</span><span class="sxs-lookup"><span data-stu-id="9736d-106">[in] Flags that indicate the requested contents of the context buffer (defined in WinNT.h).</span></span>  
  
 `contextBufSize`  
 <span data-ttu-id="9736d-107">[in]已分配的上下文缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="9736d-107">[in] The allocated size of the context buffer.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="9736d-108">[out]上下文的实际大小。</span><span class="sxs-lookup"><span data-stu-id="9736d-108">[out] The actual size of the context.</span></span> <span data-ttu-id="9736d-109">此值必须小于或等于上下文缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="9736d-109">This value must be less than or equal to the size of the context buffer.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="9736d-110">[out]上下文缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="9736d-110">[out] The context buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9736d-111">返回值</span><span class="sxs-lookup"><span data-stu-id="9736d-111">Return Value</span></span>  
 <span data-ttu-id="9736d-112">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="9736d-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9736d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9736d-113">HRESULT</span></span>|<span data-ttu-id="9736d-114">描述</span><span class="sxs-lookup"><span data-stu-id="9736d-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9736d-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="9736d-115">S_OK</span></span>|<span data-ttu-id="9736d-116">成功地返回当前帧的上下文。</span><span class="sxs-lookup"><span data-stu-id="9736d-116">The context for the current frame was successfully returned.</span></span>|  
|<span data-ttu-id="9736d-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9736d-117">E_FAIL</span></span>|<span data-ttu-id="9736d-118">不会返回上下文。</span><span class="sxs-lookup"><span data-stu-id="9736d-118">The context could not be returned.</span></span>|  
|<span data-ttu-id="9736d-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span><span class="sxs-lookup"><span data-stu-id="9736d-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span></span>|<span data-ttu-id="9736d-120">上下文缓冲区因过小。</span><span class="sxs-lookup"><span data-stu-id="9736d-120">The context buffer is too small.</span></span>|  
|<span data-ttu-id="9736d-121">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="9736d-121">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="9736d-122">帧指针已末尾的堆栈;因此，可以不访问任何其他帧。</span><span class="sxs-lookup"><span data-stu-id="9736d-122">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="9736d-123">Exceptions</span><span class="sxs-lookup"><span data-stu-id="9736d-123">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9736d-124">备注</span><span class="sxs-lookup"><span data-stu-id="9736d-124">Remarks</span></span>  
 <span data-ttu-id="9736d-125">因为展开还原寄存器中，例如非易失寄存器的一个子集上下文在调用时可能不完全匹配的注册状态。</span><span class="sxs-lookup"><span data-stu-id="9736d-125">Because unwinding restores only a subset of the registers, such as non-volatile registers, the context may not exactly match the register state at the time of the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9736d-126">要求</span><span class="sxs-lookup"><span data-stu-id="9736d-126">Requirements</span></span>  
 <span data-ttu-id="9736d-127">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9736d-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9736d-128">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9736d-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9736d-129">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9736d-129">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9736d-130">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="9736d-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9736d-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="9736d-131">See also</span></span>

- [<span data-ttu-id="9736d-132">调试接口</span><span class="sxs-lookup"><span data-stu-id="9736d-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9736d-133">调试</span><span class="sxs-lookup"><span data-stu-id="9736d-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
