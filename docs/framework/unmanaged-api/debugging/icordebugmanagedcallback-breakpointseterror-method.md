---
title: ICorDebugManagedCallback::BreakpointSetError 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.BreakpointSetError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::BreakpointSetError
helpviewer_keywords:
- BreakpointSetError method [.NET Framework debugging]
- ICorDebugManagedCallback::BreakpointSetError method [.NET Framework debugging]
ms.assetid: f2b773a4-c4d0-429c-9717-51d6e2ed86af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ae0838dd5f4dcfe95cd516b23fef3d5ca429031
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586349"
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a><span data-ttu-id="28199-102">ICorDebugManagedCallback::BreakpointSetError 方法</span><span class="sxs-lookup"><span data-stu-id="28199-102">ICorDebugManagedCallback::BreakpointSetError Method</span></span>
<span data-ttu-id="28199-103">通知调试器，公共语言运行时无法准确地绑定在实时 (JIT) 编译函数之前设置的断点。</span><span class="sxs-lookup"><span data-stu-id="28199-103">Notifies the debugger that the common language runtime was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28199-104">语法</span><span class="sxs-lookup"><span data-stu-id="28199-104">Syntax</span></span>  
  
```  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="28199-105">参数</span><span class="sxs-lookup"><span data-stu-id="28199-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="28199-106">[in]指向一个 ICorDebugAppDomain 对象，表示包含未绑定的断点的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="28199-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the unbound breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="28199-107">[in]指向一个 ICorDebugThread 对象，表示包含未绑定的断点的线程的指针。</span><span class="sxs-lookup"><span data-stu-id="28199-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the unbound breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="28199-108">[in]指向一个 ICorDebugBreakpoint 对象，表示未绑定的断点的指针。</span><span class="sxs-lookup"><span data-stu-id="28199-108">[in] A pointer to an ICorDebugBreakpoint object that represents the unbound breakpoint.</span></span>  
  
 `dwError`  
 <span data-ttu-id="28199-109">[in]一个整数，指示该错误。</span><span class="sxs-lookup"><span data-stu-id="28199-109">[in] An integer that indicates the error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28199-110">备注</span><span class="sxs-lookup"><span data-stu-id="28199-110">Remarks</span></span>  
 <span data-ttu-id="28199-111">给定的断点将永远不会被命中。</span><span class="sxs-lookup"><span data-stu-id="28199-111">The given breakpoint will never be hit.</span></span> <span data-ttu-id="28199-112">调试器应停用，并将其重新绑定。</span><span class="sxs-lookup"><span data-stu-id="28199-112">The debugger should deactivate and rebind it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28199-113">要求</span><span class="sxs-lookup"><span data-stu-id="28199-113">Requirements</span></span>  
 <span data-ttu-id="28199-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="28199-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28199-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28199-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28199-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28199-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28199-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28199-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28199-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="28199-118">See also</span></span>
- [<span data-ttu-id="28199-119">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="28199-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
