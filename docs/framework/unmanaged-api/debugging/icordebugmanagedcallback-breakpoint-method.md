---
title: "ICorDebugManagedCallback::Breakpoint 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.Breakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::Breakpoint
helpviewer_keywords:
- ICorDebugManagedCallback::Breakpoint method [.NET Framework debugging]
- Breakpoint method [.NET Framework debugging]
ms.assetid: 60b279b0-a726-46d2-8c53-76986a007ebb
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d7b0c521f1b2c5a2c258738239696ad48d4e9350
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="018a0-102">ICorDebugManagedCallback::Breakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="018a0-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="018a0-103">遇到断点时，请通知调试器。</span><span class="sxs-lookup"><span data-stu-id="018a0-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="018a0-104">语法</span><span class="sxs-lookup"><span data-stu-id="018a0-104">Syntax</span></span>  
  
```  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="018a0-105">参数</span><span class="sxs-lookup"><span data-stu-id="018a0-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="018a0-106">[in]指向一个表示应用程序域中包含断点的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="018a0-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="018a0-107">[in]指向一个 ICorDebugThread 对象，表示包含断点的线程的指针。</span><span class="sxs-lookup"><span data-stu-id="018a0-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="018a0-108">[in]指向一个表示该断点的 ICorDebugBreakpoint 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="018a0-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="018a0-109">惠?</span><span class="sxs-lookup"><span data-stu-id="018a0-109">Requirements</span></span>  
 <span data-ttu-id="018a0-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="018a0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="018a0-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="018a0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="018a0-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="018a0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="018a0-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="018a0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="018a0-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="018a0-114">See Also</span></span>  
 [<span data-ttu-id="018a0-115">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="018a0-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
