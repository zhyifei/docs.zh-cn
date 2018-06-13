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
ms.openlocfilehash: 8cc437f63621c451c0af796513d4646fe0668c00
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418374"
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a><span data-ttu-id="e4dde-102">ICorDebugManagedCallback::BreakpointSetError 方法</span><span class="sxs-lookup"><span data-stu-id="e4dde-102">ICorDebugManagedCallback::BreakpointSetError Method</span></span>
<span data-ttu-id="e4dde-103">通知调试器，公共语言运行时无法准确地绑定在实时 (JIT) 编译函数之前设置的断点。</span><span class="sxs-lookup"><span data-stu-id="e4dde-103">Notifies the debugger that the common language runtime was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4dde-104">语法</span><span class="sxs-lookup"><span data-stu-id="e4dde-104">Syntax</span></span>  
  
```  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e4dde-105">参数</span><span class="sxs-lookup"><span data-stu-id="e4dde-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="e4dde-106">[in]指向一个表示应用程序域中包含未绑定的断点的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="e4dde-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the unbound breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="e4dde-107">[in]指向一个 ICorDebugThread 对象，表示包含未绑定的断点的线程的指针。</span><span class="sxs-lookup"><span data-stu-id="e4dde-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the unbound breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="e4dde-108">[in]指向一个表示未绑定的断点的 ICorDebugBreakpoint 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="e4dde-108">[in] A pointer to an ICorDebugBreakpoint object that represents the unbound breakpoint.</span></span>  
  
 `dwError`  
 <span data-ttu-id="e4dde-109">[in]一个整数，指示错误。</span><span class="sxs-lookup"><span data-stu-id="e4dde-109">[in] An integer that indicates the error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4dde-110">备注</span><span class="sxs-lookup"><span data-stu-id="e4dde-110">Remarks</span></span>  
 <span data-ttu-id="e4dde-111">给定的断点将永远不会被命中。</span><span class="sxs-lookup"><span data-stu-id="e4dde-111">The given breakpoint will never be hit.</span></span> <span data-ttu-id="e4dde-112">调试器应停用，并将其重新绑定。</span><span class="sxs-lookup"><span data-stu-id="e4dde-112">The debugger should deactivate and rebind it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4dde-113">要求</span><span class="sxs-lookup"><span data-stu-id="e4dde-113">Requirements</span></span>  
 <span data-ttu-id="e4dde-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e4dde-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4dde-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4dde-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4dde-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4dde-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4dde-117">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4dde-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4dde-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4dde-118">See Also</span></span>  
 [<span data-ttu-id="e4dde-119">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="e4dde-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
