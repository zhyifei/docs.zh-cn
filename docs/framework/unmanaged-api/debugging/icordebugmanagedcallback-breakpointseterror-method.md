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
ms.openlocfilehash: dae04e1809c1bb3260461086a4953b8b4e5cce52
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122573"
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a><span data-ttu-id="0e220-102">ICorDebugManagedCallback::BreakpointSetError 方法</span><span class="sxs-lookup"><span data-stu-id="0e220-102">ICorDebugManagedCallback::BreakpointSetError Method</span></span>
<span data-ttu-id="0e220-103">通知调试器，公共语言运行时无法准确绑定在实时（JIT）函数编译之前设置的断点。</span><span class="sxs-lookup"><span data-stu-id="0e220-103">Notifies the debugger that the common language runtime was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e220-104">语法</span><span class="sxs-lookup"><span data-stu-id="0e220-104">Syntax</span></span>  
  
```cpp  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e220-105">参数</span><span class="sxs-lookup"><span data-stu-id="0e220-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="0e220-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示包含未绑定断点的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="0e220-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the unbound breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="0e220-107">中指向 ICorDebugThread 对象的指针，该对象表示包含未绑定断点的线程。</span><span class="sxs-lookup"><span data-stu-id="0e220-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the unbound breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="0e220-108">中指向 ICorDebugBreakpoint 对象的指针，该对象表示未绑定的断点。</span><span class="sxs-lookup"><span data-stu-id="0e220-108">[in] A pointer to an ICorDebugBreakpoint object that represents the unbound breakpoint.</span></span>  
  
 `dwError`  
 <span data-ttu-id="0e220-109">中指示错误的整数。</span><span class="sxs-lookup"><span data-stu-id="0e220-109">[in] An integer that indicates the error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e220-110">备注</span><span class="sxs-lookup"><span data-stu-id="0e220-110">Remarks</span></span>  
 <span data-ttu-id="0e220-111">将永远不会命中给定的断点。</span><span class="sxs-lookup"><span data-stu-id="0e220-111">The given breakpoint will never be hit.</span></span> <span data-ttu-id="0e220-112">调试器应停用并将其重新绑定。</span><span class="sxs-lookup"><span data-stu-id="0e220-112">The debugger should deactivate and rebind it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e220-113">要求</span><span class="sxs-lookup"><span data-stu-id="0e220-113">Requirements</span></span>  
 <span data-ttu-id="0e220-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0e220-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e220-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e220-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e220-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e220-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e220-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e220-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e220-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e220-118">See also</span></span>

- [<span data-ttu-id="0e220-119">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="0e220-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
