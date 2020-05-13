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
ms.openlocfilehash: 743b0c8016ca5c0401046166a770d857215429a3
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379221"
---
# <a name="icordebugstackwalkgetcontext-method"></a><span data-ttu-id="14b65-102">ICorDebugStackWalk::GetContext 方法</span><span class="sxs-lookup"><span data-stu-id="14b65-102">ICorDebugStackWalk::GetContext Method</span></span>
<span data-ttu-id="14b65-103">返回[ICorDebugStackWalk](icordebugstackwalk-interface.md)对象中的当前帧的上下文。</span><span class="sxs-lookup"><span data-stu-id="14b65-103">Returns the context for the current frame in the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14b65-104">语法</span><span class="sxs-lookup"><span data-stu-id="14b65-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14b65-105">参数</span><span class="sxs-lookup"><span data-stu-id="14b65-105">Parameters</span></span>  
 `contextFlags`  
 <span data-ttu-id="14b65-106">中指示上下文缓冲区的请求内容（在 WinNT 中定义）的标志。</span><span class="sxs-lookup"><span data-stu-id="14b65-106">[in] Flags that indicate the requested contents of the context buffer (defined in WinNT.h).</span></span>  
  
 `contextBufSize`  
 <span data-ttu-id="14b65-107">中上下文缓冲区的已分配大小。</span><span class="sxs-lookup"><span data-stu-id="14b65-107">[in] The allocated size of the context buffer.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="14b65-108">弄上下文的实际大小。</span><span class="sxs-lookup"><span data-stu-id="14b65-108">[out] The actual size of the context.</span></span> <span data-ttu-id="14b65-109">此值必须小于或等于上下文缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="14b65-109">This value must be less than or equal to the size of the context buffer.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="14b65-110">弄上下文缓冲区。</span><span class="sxs-lookup"><span data-stu-id="14b65-110">[out] The context buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14b65-111">返回值</span><span class="sxs-lookup"><span data-stu-id="14b65-111">Return Value</span></span>  
 <span data-ttu-id="14b65-112">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="14b65-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="14b65-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="14b65-113">HRESULT</span></span>|<span data-ttu-id="14b65-114">描述</span><span class="sxs-lookup"><span data-stu-id="14b65-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="14b65-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="14b65-115">S_OK</span></span>|<span data-ttu-id="14b65-116">当前帧的上下文已成功返回。</span><span class="sxs-lookup"><span data-stu-id="14b65-116">The context for the current frame was successfully returned.</span></span>|  
|<span data-ttu-id="14b65-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="14b65-117">E_FAIL</span></span>|<span data-ttu-id="14b65-118">未能返回上下文。</span><span class="sxs-lookup"><span data-stu-id="14b65-118">The context could not be returned.</span></span>|  
|<span data-ttu-id="14b65-119">HRESULT_FROM_WIN32 （ERROR_INSUFFICIENT 缓冲区）</span><span class="sxs-lookup"><span data-stu-id="14b65-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span></span>|<span data-ttu-id="14b65-120">上下文缓冲区太小。</span><span class="sxs-lookup"><span data-stu-id="14b65-120">The context buffer is too small.</span></span>|  
|<span data-ttu-id="14b65-121">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="14b65-121">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="14b65-122">帧指针已位于堆栈末尾;因此，不能访问其他帧。</span><span class="sxs-lookup"><span data-stu-id="14b65-122">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="14b65-123">例外</span><span class="sxs-lookup"><span data-stu-id="14b65-123">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14b65-124">备注</span><span class="sxs-lookup"><span data-stu-id="14b65-124">Remarks</span></span>  
 <span data-ttu-id="14b65-125">因为展开仅还原一个寄存器子集，如非易失性寄存器，所以在调用时，上下文可能与注册状态不完全匹配。</span><span class="sxs-lookup"><span data-stu-id="14b65-125">Because unwinding restores only a subset of the registers, such as non-volatile registers, the context may not exactly match the register state at the time of the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14b65-126">要求</span><span class="sxs-lookup"><span data-stu-id="14b65-126">Requirements</span></span>  
 <span data-ttu-id="14b65-127">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="14b65-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14b65-128">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14b65-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14b65-129">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14b65-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14b65-130">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14b65-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14b65-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="14b65-131">See also</span></span>

- [<span data-ttu-id="14b65-132">调试接口</span><span class="sxs-lookup"><span data-stu-id="14b65-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="14b65-133">调试</span><span class="sxs-lookup"><span data-stu-id="14b65-133">Debugging</span></span>](index.md)
