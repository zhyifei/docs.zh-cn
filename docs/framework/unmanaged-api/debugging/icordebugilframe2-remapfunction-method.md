---
title: ICorDebugILFrame2::RemapFunction 方法
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.RemapFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbec4a4ba05a7e6d50f9740582415219eafb1e57
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64621473"
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="b430b-102">ICorDebugILFrame2::RemapFunction 方法</span><span class="sxs-lookup"><span data-stu-id="b430b-102">ICorDebugILFrame2::RemapFunction Method</span></span>
<span data-ttu-id="b430b-103">通过指定新的 Microsoft 中间语言 (MSIL) 偏移量来重新映射已编辑的函数</span><span class="sxs-lookup"><span data-stu-id="b430b-103">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b430b-104">语法</span><span class="sxs-lookup"><span data-stu-id="b430b-104">Syntax</span></span>  
  
```  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b430b-105">参数</span><span class="sxs-lookup"><span data-stu-id="b430b-105">Parameters</span></span>  
 `newILOffset`  
 <span data-ttu-id="b430b-106">[in]在指令指针应放置的堆栈帧的新 MSIL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="b430b-106">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="b430b-107">此值必须是序列点。</span><span class="sxs-lookup"><span data-stu-id="b430b-107">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="b430b-108">它是调用方的责任，以确保此值的有效性。</span><span class="sxs-lookup"><span data-stu-id="b430b-108">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="b430b-109">例如，MSIL 偏移量不是函数的边界之外时才有效。</span><span class="sxs-lookup"><span data-stu-id="b430b-109">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b430b-110">备注</span><span class="sxs-lookup"><span data-stu-id="b430b-110">Remarks</span></span>  
 <span data-ttu-id="b430b-111">当已编辑的帧的函数时，则调试器可以调用`RemapFunction`方法来交换中帧的函数的最新版本，因此可以执行。</span><span class="sxs-lookup"><span data-stu-id="b430b-111">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="b430b-112">执行代码将在给定的 MSIL 偏移量处开始。</span><span class="sxs-lookup"><span data-stu-id="b430b-112">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b430b-113">调用`RemapFunction`，例如调用[icordebugilframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)，将立即使失效与生成线程的堆栈跟踪相关的所有调试接口。</span><span class="sxs-lookup"><span data-stu-id="b430b-113">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="b430b-114">这些接口包括[ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)，ICorDebugILFrame、 ICorDebugInternalFrame 和 ICorDebugNativeFrame。</span><span class="sxs-lookup"><span data-stu-id="b430b-114">These interfaces include [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="b430b-115">`RemapFunction`仅在当前帧的上下文中并且仅在以下情况下，可以调用方法：</span><span class="sxs-lookup"><span data-stu-id="b430b-115">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
- <span data-ttu-id="b430b-116">之后的收据[ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md)不尚未一直在持续运行的回调。</span><span class="sxs-lookup"><span data-stu-id="b430b-116">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
- <span data-ttu-id="b430b-117">由于停止执行代码时[icordebugmanagedcallback:: Editandcontinueremap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md)此帧的事件。</span><span class="sxs-lookup"><span data-stu-id="b430b-117">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b430b-118">要求</span><span class="sxs-lookup"><span data-stu-id="b430b-118">Requirements</span></span>  
 <span data-ttu-id="b430b-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b430b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b430b-120">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b430b-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b430b-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b430b-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b430b-122">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b430b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
