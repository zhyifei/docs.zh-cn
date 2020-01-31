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
ms.openlocfilehash: 9953d0f3e1a4d4cd935918f0e5721e474453ca7d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791911"
---
# <a name="icordebugstackwalkgetcontext-method"></a><span data-ttu-id="606ac-102">ICorDebugStackWalk::GetContext 方法</span><span class="sxs-lookup"><span data-stu-id="606ac-102">ICorDebugStackWalk::GetContext Method</span></span>
<span data-ttu-id="606ac-103">返回[ICorDebugStackWalk](icordebugstackwalk-interface.md)对象中的当前帧的上下文。</span><span class="sxs-lookup"><span data-stu-id="606ac-103">Returns the context for the current frame in the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="606ac-104">语法</span><span class="sxs-lookup"><span data-stu-id="606ac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="606ac-105">参数</span><span class="sxs-lookup"><span data-stu-id="606ac-105">Parameters</span></span>  
 `contextFlags`  
 <span data-ttu-id="606ac-106">中指示上下文缓冲区的请求内容（在 WinNT 中定义）的标志。</span><span class="sxs-lookup"><span data-stu-id="606ac-106">[in] Flags that indicate the requested contents of the context buffer (defined in WinNT.h).</span></span>  
  
 `contextBufSize`  
 <span data-ttu-id="606ac-107">中上下文缓冲区的已分配大小。</span><span class="sxs-lookup"><span data-stu-id="606ac-107">[in] The allocated size of the context buffer.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="606ac-108">弄上下文的实际大小。</span><span class="sxs-lookup"><span data-stu-id="606ac-108">[out] The actual size of the context.</span></span> <span data-ttu-id="606ac-109">此值必须小于或等于上下文缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="606ac-109">This value must be less than or equal to the size of the context buffer.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="606ac-110">弄上下文缓冲区。</span><span class="sxs-lookup"><span data-stu-id="606ac-110">[out] The context buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="606ac-111">返回值</span><span class="sxs-lookup"><span data-stu-id="606ac-111">Return Value</span></span>  
 <span data-ttu-id="606ac-112">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="606ac-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="606ac-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="606ac-113">HRESULT</span></span>|<span data-ttu-id="606ac-114">描述</span><span class="sxs-lookup"><span data-stu-id="606ac-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="606ac-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="606ac-115">S_OK</span></span>|<span data-ttu-id="606ac-116">当前帧的上下文已成功返回。</span><span class="sxs-lookup"><span data-stu-id="606ac-116">The context for the current frame was successfully returned.</span></span>|  
|<span data-ttu-id="606ac-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="606ac-117">E_FAIL</span></span>|<span data-ttu-id="606ac-118">未能返回上下文。</span><span class="sxs-lookup"><span data-stu-id="606ac-118">The context could not be returned.</span></span>|  
|<span data-ttu-id="606ac-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span><span class="sxs-lookup"><span data-stu-id="606ac-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span></span>|<span data-ttu-id="606ac-120">上下文缓冲区太小。</span><span class="sxs-lookup"><span data-stu-id="606ac-120">The context buffer is too small.</span></span>|  
|<span data-ttu-id="606ac-121">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="606ac-121">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="606ac-122">帧指针已位于堆栈末尾;因此，不能访问其他帧。</span><span class="sxs-lookup"><span data-stu-id="606ac-122">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="606ac-123">异常</span><span class="sxs-lookup"><span data-stu-id="606ac-123">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="606ac-124">备注</span><span class="sxs-lookup"><span data-stu-id="606ac-124">Remarks</span></span>  
 <span data-ttu-id="606ac-125">因为展开仅还原一个寄存器子集，如非易失性寄存器，所以在调用时，上下文可能与注册状态不完全匹配。</span><span class="sxs-lookup"><span data-stu-id="606ac-125">Because unwinding restores only a subset of the registers, such as non-volatile registers, the context may not exactly match the register state at the time of the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="606ac-126">需求</span><span class="sxs-lookup"><span data-stu-id="606ac-126">Requirements</span></span>  
 <span data-ttu-id="606ac-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="606ac-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="606ac-128">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="606ac-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="606ac-129">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="606ac-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="606ac-130">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="606ac-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="606ac-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="606ac-131">See also</span></span>

- [<span data-ttu-id="606ac-132">调试接口</span><span class="sxs-lookup"><span data-stu-id="606ac-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="606ac-133">调试</span><span class="sxs-lookup"><span data-stu-id="606ac-133">Debugging</span></span>](index.md)
