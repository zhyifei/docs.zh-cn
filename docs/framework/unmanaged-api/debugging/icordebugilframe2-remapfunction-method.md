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
ms.openlocfilehash: f4f73b99b4cb48690a2a8611dbf5a5420adab5d4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794357"
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="b2978-102">ICorDebugILFrame2::RemapFunction 方法</span><span class="sxs-lookup"><span data-stu-id="b2978-102">ICorDebugILFrame2::RemapFunction Method</span></span>
<span data-ttu-id="b2978-103">通过指定新的 Microsoft 中间语言（MSIL）偏移量重新映射编辑的函数</span><span class="sxs-lookup"><span data-stu-id="b2978-103">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2978-104">语法</span><span class="sxs-lookup"><span data-stu-id="b2978-104">Syntax</span></span>  
  
```cpp  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2978-105">参数</span><span class="sxs-lookup"><span data-stu-id="b2978-105">Parameters</span></span>  
 `newILOffset`  
 <span data-ttu-id="b2978-106">中堆栈帧的新 MSIL 偏移量，应在该位置放置指令指针。</span><span class="sxs-lookup"><span data-stu-id="b2978-106">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="b2978-107">此值必须是一个序列点。</span><span class="sxs-lookup"><span data-stu-id="b2978-107">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="b2978-108">调用方负责确保此值的有效性。</span><span class="sxs-lookup"><span data-stu-id="b2978-108">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="b2978-109">例如，如果 MSIL 偏移量在函数的边界之外，则它是无效的。</span><span class="sxs-lookup"><span data-stu-id="b2978-109">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2978-110">备注</span><span class="sxs-lookup"><span data-stu-id="b2978-110">Remarks</span></span>  
 <span data-ttu-id="b2978-111">编辑框架的函数后，调试器可以调用 `RemapFunction` 方法来交换最新版本的框架函数以便可以执行该函数。</span><span class="sxs-lookup"><span data-stu-id="b2978-111">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="b2978-112">代码执行将以给定的 MSIL 偏移量开始。</span><span class="sxs-lookup"><span data-stu-id="b2978-112">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2978-113">调用 `RemapFunction`（如调用[ICorDebugILFrame：： SetIP](icordebugilframe-setip-method.md)）将立即无效与为线程生成堆栈跟踪相关的所有调试接口。</span><span class="sxs-lookup"><span data-stu-id="b2978-113">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="b2978-114">这些接口包括[ICorDebugChain](icordebugchain-interface.md)、ICorDebugILFrame、ICorDebugInternalFrame 和 ICorDebugNativeFrame。</span><span class="sxs-lookup"><span data-stu-id="b2978-114">These interfaces include [ICorDebugChain](icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="b2978-115">只能在当前帧的上下文中调用 `RemapFunction` 方法，并且只能在以下情况之一中调用：</span><span class="sxs-lookup"><span data-stu-id="b2978-115">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
- <span data-ttu-id="b2978-116">在收到尚未继续的[ICorDebugManagedCallback2：： FunctionRemapOpportunity](icordebugmanagedcallback2-functionremapopportunity-method.md)回调之后。</span><span class="sxs-lookup"><span data-stu-id="b2978-116">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
- <span data-ttu-id="b2978-117">当代码执行由于此帧的[ICorDebugManagedCallback：： EditAndContinueRemap](icordebugmanagedcallback-editandcontinueremap-method.md)事件而停止时。</span><span class="sxs-lookup"><span data-stu-id="b2978-117">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2978-118">需求</span><span class="sxs-lookup"><span data-stu-id="b2978-118">Requirements</span></span>  
 <span data-ttu-id="b2978-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b2978-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2978-120">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2978-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2978-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2978-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2978-122">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2978-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
