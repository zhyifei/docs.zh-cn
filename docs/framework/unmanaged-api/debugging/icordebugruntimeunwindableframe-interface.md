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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf6bc73683a6c37ceaaffc635a58803b71c3b6cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134194"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="aab89-102">ICorDebugRuntimeUnwindableFrame 接口</span><span class="sxs-lookup"><span data-stu-id="aab89-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="aab89-103">提供对非托管方法的支持，这些方法需要公共语言运行时 (CLR) 来展开帧。</span><span class="sxs-lookup"><span data-stu-id="aab89-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aab89-104">备注</span><span class="sxs-lookup"><span data-stu-id="aab89-104">Remarks</span></span>  
 `ICorDebugRuntimeUnwindableFrame` <span data-ttu-id="aab89-105">ICorDebugFrame 接口的专用的版本。</span><span class="sxs-lookup"><span data-stu-id="aab89-105">is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="aab89-106">它可供需要展开当前堆栈帧运行时的非托管方法。</span><span class="sxs-lookup"><span data-stu-id="aab89-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="aab89-107">无法运行现有的展开约定，因为它们不使用 JIT 编译的代码。</span><span class="sxs-lookup"><span data-stu-id="aab89-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="aab89-108">当调试器发现不可展开帧时，它应使用[icordebugstackwalk:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)方法来展开它，但它应执行检查本身。</span><span class="sxs-lookup"><span data-stu-id="aab89-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="aab89-109">当调试器收到`ICorDebugRuntimeUnwindableFrame`，它可以调用[icordebugstackwalk:: Getcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)方法来检索帧的上下文。</span><span class="sxs-lookup"><span data-stu-id="aab89-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aab89-110">要求</span><span class="sxs-lookup"><span data-stu-id="aab89-110">Requirements</span></span>  
 <span data-ttu-id="aab89-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aab89-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aab89-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aab89-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aab89-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aab89-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="aab89-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="aab89-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="aab89-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="aab89-115">See also</span></span>

- [<span data-ttu-id="aab89-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="aab89-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="aab89-117">调试</span><span class="sxs-lookup"><span data-stu-id="aab89-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
