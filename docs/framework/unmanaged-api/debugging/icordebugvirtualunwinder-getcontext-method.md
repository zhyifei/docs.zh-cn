---
title: ICorDebugVirtualUnwinder::GetContext 方法
ms.date: 03/30/2017
ms.assetid: fe502a76-3068-47e5-a0a0-85ccb72dfac3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a554efc89c1242537bec7de074220cbec95ecdd2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481122"
---
# <a name="icordebugvirtualunwindergetcontext-method"></a><span data-ttu-id="71212-102">ICorDebugVirtualUnwinder::GetContext 方法</span><span class="sxs-lookup"><span data-stu-id="71212-102">ICorDebugVirtualUnwinder::GetContext Method</span></span>
<span data-ttu-id="71212-103">获取此展开器的当前上下文。</span><span class="sxs-lookup"><span data-stu-id="71212-103">Gets the current context of this unwinder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71212-104">语法</span><span class="sxs-lookup"><span data-stu-id="71212-104">Syntax</span></span>  
  
```  
HRESULT GetContext(  
   [in] ULONG32 contextFlags,  
   [in] ULONG32 cbContextBuf,  
   [out] ULONG32* contextSize,  
   [out, size_is(cbContextBuf)] BYTE contextBuf[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71212-105">参数</span><span class="sxs-lookup"><span data-stu-id="71212-105">Parameters</span></span>  
 `contextFlags`  
 <span data-ttu-id="71212-106">[in] 指定要返回上下文的哪些部分的标记（在 WinNT.h 中定义）。</span><span class="sxs-lookup"><span data-stu-id="71212-106">[in] Flags that specify which parts of the context to return (defined in WinNT.h).</span></span>  
  
 `cbContextBuf`  
 <span data-ttu-id="71212-107">[in] `contextBuf` 中的字节数。</span><span class="sxs-lookup"><span data-stu-id="71212-107">[in] The number of bytes in `contextBuf`.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="71212-108">[out] 指向实际写入 `contextBuf` 的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="71212-108">[out] A pointer to the number of bytes actually written to `contextBuf`.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="71212-109">[out] 包含此开卷机当前上下文的字节数组。</span><span class="sxs-lookup"><span data-stu-id="71212-109">[out] A byte array that contains the current context of this unwinder.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71212-110">返回值</span><span class="sxs-lookup"><span data-stu-id="71212-110">Return Value</span></span>  
 <span data-ttu-id="71212-111">由 mscordbi 接收到的任何失败的 HRESULT 都被视为是致命的，并将导致 ICorDebug API 返回 `CORDBG_E_DATA_TARGET_ERROR`。</span><span class="sxs-lookup"><span data-stu-id="71212-111">Any failing HRESULT value received by mscordbi is considered fatal and will cause ICorDebug APIs to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71212-112">备注</span><span class="sxs-lookup"><span data-stu-id="71212-112">Remarks</span></span>  
 <span data-ttu-id="71212-113">设置初始值`contextBuf`参数通过调用返回的上下文缓冲区[icordebugstackwalk:: Getcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="71212-113">You set the initial value of the `contextBuf` argument to the context buffer returned by calling the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71212-114">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="71212-114">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="71212-115">因为回退可能仅还原寄存器子集（例如非易失性寄存器），所以在实际方法调用时，上下文可能并不与寄存器状态完全匹配。</span><span class="sxs-lookup"><span data-stu-id="71212-115">Because unwinding may only restore a subset of the registers, such as the non-volatile registers only, the context may not exactly match the register state at the time of the actual method call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71212-116">要求</span><span class="sxs-lookup"><span data-stu-id="71212-116">Requirements</span></span>  
 <span data-ttu-id="71212-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="71212-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71212-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71212-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71212-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71212-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71212-120">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71212-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71212-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="71212-121">See also</span></span>
- [<span data-ttu-id="71212-122">ICorDebugMemoryBuffer 接口</span><span class="sxs-lookup"><span data-stu-id="71212-122">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="71212-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="71212-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
