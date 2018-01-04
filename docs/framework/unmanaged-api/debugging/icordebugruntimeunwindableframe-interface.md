---
title: "ICorDebugRuntimeUnwindableFrame 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugUnwindableFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugUnwindableFrame
helpviewer_keywords: ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 80b4212691784d88c92235a5c5c65acaee165201
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="de85e-102">ICorDebugRuntimeUnwindableFrame 接口</span><span class="sxs-lookup"><span data-stu-id="de85e-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="de85e-103">提供对非托管方法的支持，这些方法需要公共语言运行时 (CLR) 来展开帧。</span><span class="sxs-lookup"><span data-stu-id="de85e-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de85e-104">备注</span><span class="sxs-lookup"><span data-stu-id="de85e-104">Remarks</span></span>  
 <span data-ttu-id="de85e-105">`ICorDebugRuntimeUnwindableFrame`ICorDebugFrame 接口的专用的版本。</span><span class="sxs-lookup"><span data-stu-id="de85e-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="de85e-106">它使用非托管需要运行时，若要展开当前堆栈上的某个帧的方法。</span><span class="sxs-lookup"><span data-stu-id="de85e-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="de85e-107">现有的展开约定无效，因为它们不使用 JIT 编译的代码。</span><span class="sxs-lookup"><span data-stu-id="de85e-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="de85e-108">当调试器发现不可展开的框架时，它应使用[icordebugstackwalk:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)方法来展开它，但它应执行检查本身。</span><span class="sxs-lookup"><span data-stu-id="de85e-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="de85e-109">当调试器收到`ICorDebugRuntimeUnwindableFrame`，它可以调用[icordebugstackwalk:: Getcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)方法来检索帧的上下文。</span><span class="sxs-lookup"><span data-stu-id="de85e-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de85e-110">惠?</span><span class="sxs-lookup"><span data-stu-id="de85e-110">Requirements</span></span>  
 <span data-ttu-id="de85e-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="de85e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de85e-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de85e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de85e-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de85e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de85e-114">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de85e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de85e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="de85e-115">See Also</span></span>  
 [<span data-ttu-id="de85e-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="de85e-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="de85e-117">调试</span><span class="sxs-lookup"><span data-stu-id="de85e-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
