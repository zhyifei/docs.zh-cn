---
title: ICorDebugRuntimeUnwindableFrame 接口
ms.date: 03/30/2017
api_name:
- ICorDebugUnwindableFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnwindableFrame
helpviewer_keywords:
- ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type:
- apiref
ms.openlocfilehash: a7b0608e85411844828cebea34c0ce5ef5b1bd11
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379387"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="0387c-102">ICorDebugRuntimeUnwindableFrame 接口</span><span class="sxs-lookup"><span data-stu-id="0387c-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="0387c-103">提供对非托管方法的支持，这些方法需要公共语言运行时 (CLR) 来展开帧。</span><span class="sxs-lookup"><span data-stu-id="0387c-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0387c-104">备注</span><span class="sxs-lookup"><span data-stu-id="0387c-104">Remarks</span></span>  
 <span data-ttu-id="0387c-105">`ICorDebugRuntimeUnwindableFrame`是 ICorDebugFrame 接口的专用版本。</span><span class="sxs-lookup"><span data-stu-id="0387c-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="0387c-106">它由需要运行时展开当前堆栈上的帧的非托管方法使用。</span><span class="sxs-lookup"><span data-stu-id="0387c-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="0387c-107">现有的展开约定不起作用，因为它们不使用 JIT 编译代码。</span><span class="sxs-lookup"><span data-stu-id="0387c-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="0387c-108">当调试器发现不可展开帧时，它应使用[ICorDebugStackWalk：： Next](icordebugstackwalk-next-method.md)方法展开它，但它应执行检查。</span><span class="sxs-lookup"><span data-stu-id="0387c-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="0387c-109">当调试器收到时 `ICorDebugRuntimeUnwindableFrame` ，它可以调用[ICorDebugStackWalk：： GetContext](icordebugstackwalk-getcontext-method.md)方法来检索该帧的上下文。</span><span class="sxs-lookup"><span data-stu-id="0387c-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0387c-110">要求</span><span class="sxs-lookup"><span data-stu-id="0387c-110">Requirements</span></span>  
 <span data-ttu-id="0387c-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0387c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0387c-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0387c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0387c-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0387c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0387c-114">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0387c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0387c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="0387c-115">See also</span></span>

- [<span data-ttu-id="0387c-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="0387c-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0387c-117">调试</span><span class="sxs-lookup"><span data-stu-id="0387c-117">Debugging</span></span>](index.md)
