---
title: ICorDebugManagedCallback::Breakpoint 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Breakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Breakpoint
helpviewer_keywords:
- ICorDebugManagedCallback::Breakpoint method [.NET Framework debugging]
- Breakpoint method [.NET Framework debugging]
ms.assetid: 60b279b0-a726-46d2-8c53-76986a007ebb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8591cb7f8eec3d92100b49db553ed1b5b6533c17
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131063"
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="1e6bd-102">ICorDebugManagedCallback::Breakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="1e6bd-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="1e6bd-103">遇到断点时，会通知调试器。</span><span class="sxs-lookup"><span data-stu-id="1e6bd-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e6bd-104">语法</span><span class="sxs-lookup"><span data-stu-id="1e6bd-104">Syntax</span></span>  
  
```  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e6bd-105">参数</span><span class="sxs-lookup"><span data-stu-id="1e6bd-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="1e6bd-106">[in]指向一个 ICorDebugAppDomain 对象，表示包含断点的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="1e6bd-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="1e6bd-107">[in]指向一个 ICorDebugThread 对象，表示包含断点的线程的指针。</span><span class="sxs-lookup"><span data-stu-id="1e6bd-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="1e6bd-108">[in]指向一个 ICorDebugBreakpoint 对象，表示该断点的指针。</span><span class="sxs-lookup"><span data-stu-id="1e6bd-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e6bd-109">要求</span><span class="sxs-lookup"><span data-stu-id="1e6bd-109">Requirements</span></span>  
 <span data-ttu-id="1e6bd-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1e6bd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e6bd-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e6bd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e6bd-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e6bd-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1e6bd-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="1e6bd-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1e6bd-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e6bd-114">See also</span></span>

- [<span data-ttu-id="1e6bd-115">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="1e6bd-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
