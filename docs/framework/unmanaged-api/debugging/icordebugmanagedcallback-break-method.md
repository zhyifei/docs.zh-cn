---
title: ICorDebugManagedCallback::Break 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Break
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Break
helpviewer_keywords:
- Break method [.NET Framework debugging]
- ICorDebugManagedCallback::Break method [.NET Framework debugging]
ms.assetid: 7d78a301-82b3-43b2-9d65-3cda3285ae97
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83524b24fd05969fa4f45fd742d1df955c441d44
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732383"
---
# <a name="icordebugmanagedcallbackbreak-method"></a><span data-ttu-id="4925d-102">ICorDebugManagedCallback::Break 方法</span><span class="sxs-lookup"><span data-stu-id="4925d-102">ICorDebugManagedCallback::Break Method</span></span>
<span data-ttu-id="4925d-103">通知调试器时<xref:System.Reflection.Emit.OpCodes.Break>执行代码流中的指令。</span><span class="sxs-lookup"><span data-stu-id="4925d-103">Notifies the debugger when a <xref:System.Reflection.Emit.OpCodes.Break> instruction in the code stream is executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4925d-104">语法</span><span class="sxs-lookup"><span data-stu-id="4925d-104">Syntax</span></span>  
  
```  
HRESULT Break (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4925d-105">参数</span><span class="sxs-lookup"><span data-stu-id="4925d-105">Parameters</span></span>  
 `pAppDOmain`  
 <span data-ttu-id="4925d-106">[in]指向一个 ICorDebugAppDomain 对象，表示包含 break 指令的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="4925d-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the break instruction.</span></span>  
  
 `thread`  
 <span data-ttu-id="4925d-107">[in]指向表示，包含 break 指令的线程的 ICorDebugThread 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="4925d-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the break instruction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4925d-108">要求</span><span class="sxs-lookup"><span data-stu-id="4925d-108">Requirements</span></span>  
 <span data-ttu-id="4925d-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4925d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4925d-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4925d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4925d-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4925d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4925d-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4925d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4925d-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="4925d-113">See also</span></span>
- [<span data-ttu-id="4925d-114">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="4925d-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
