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
ms.openlocfilehash: 43f585417ed52b92c23087c0f02fd188ee09ea7e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210210"
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="b65e4-102">ICorDebugILFrame2::RemapFunction 方法</span><span class="sxs-lookup"><span data-stu-id="b65e4-102">ICorDebugILFrame2::RemapFunction Method</span></span>
<span data-ttu-id="b65e4-103">通过指定新的 Microsoft 中间语言（MSIL）偏移量重新映射编辑的函数</span><span class="sxs-lookup"><span data-stu-id="b65e4-103">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b65e4-104">语法</span><span class="sxs-lookup"><span data-stu-id="b65e4-104">Syntax</span></span>  
  
```cpp  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b65e4-105">参数</span><span class="sxs-lookup"><span data-stu-id="b65e4-105">Parameters</span></span>  
 `newILOffset`  
 <span data-ttu-id="b65e4-106">中堆栈帧的新 MSIL 偏移量，应在该位置放置指令指针。</span><span class="sxs-lookup"><span data-stu-id="b65e4-106">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="b65e4-107">此值必须是一个序列点。</span><span class="sxs-lookup"><span data-stu-id="b65e4-107">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="b65e4-108">调用方负责确保此值的有效性。</span><span class="sxs-lookup"><span data-stu-id="b65e4-108">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="b65e4-109">例如，如果 MSIL 偏移量在函数的边界之外，则它是无效的。</span><span class="sxs-lookup"><span data-stu-id="b65e4-109">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b65e4-110">备注</span><span class="sxs-lookup"><span data-stu-id="b65e4-110">Remarks</span></span>  
 <span data-ttu-id="b65e4-111">编辑框架的函数后，调试器可以调用 `RemapFunction` 方法以在框架的函数的最新版本中进行交换，以便可以执行。</span><span class="sxs-lookup"><span data-stu-id="b65e4-111">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="b65e4-112">代码执行将以给定的 MSIL 偏移量开始。</span><span class="sxs-lookup"><span data-stu-id="b65e4-112">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b65e4-113">调用 `RemapFunction` （如调用[ICorDebugILFrame：： SetIP](icordebugilframe-setip-method.md)）会立即无效与为线程生成堆栈跟踪相关的所有调试接口。</span><span class="sxs-lookup"><span data-stu-id="b65e4-113">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="b65e4-114">这些接口包括[ICorDebugChain](icordebugchain-interface.md)、ICorDebugILFrame、ICorDebugInternalFrame 和 ICorDebugNativeFrame。</span><span class="sxs-lookup"><span data-stu-id="b65e4-114">These interfaces include [ICorDebugChain](icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="b65e4-115">`RemapFunction`方法只能在当前帧的上下文中调用，并且只能在以下情况之一中调用：</span><span class="sxs-lookup"><span data-stu-id="b65e4-115">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
- <span data-ttu-id="b65e4-116">在收到尚未继续的[ICorDebugManagedCallback2：： FunctionRemapOpportunity](icordebugmanagedcallback2-functionremapopportunity-method.md)回调之后。</span><span class="sxs-lookup"><span data-stu-id="b65e4-116">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
- <span data-ttu-id="b65e4-117">当代码执行由于此帧的[ICorDebugManagedCallback：： EditAndContinueRemap](icordebugmanagedcallback-editandcontinueremap-method.md)事件而停止时。</span><span class="sxs-lookup"><span data-stu-id="b65e4-117">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b65e4-118">要求</span><span class="sxs-lookup"><span data-stu-id="b65e4-118">Requirements</span></span>  
 <span data-ttu-id="b65e4-119">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b65e4-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b65e4-120">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b65e4-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b65e4-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b65e4-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b65e4-122">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b65e4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
