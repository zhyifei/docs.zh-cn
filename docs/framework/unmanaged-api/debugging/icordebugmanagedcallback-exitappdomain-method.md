---
title: ICorDebugManagedCallback::ExitAppDomain 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitAppDomain
helpviewer_keywords:
- ICorDebugManagedCallback::ExitAppDomain method [.NET Framework debugging]
- ExitAppDomain method [.NET Framework debugging]
ms.assetid: d815486e-b3bd-4fe8-ba28-02abdb4d67ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f909eddde182a73709be9ca5cafec6285db46b4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412849"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="b0eca-102">ICorDebugManagedCallback::ExitAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="b0eca-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>
<span data-ttu-id="b0eca-103">通知调试器已退出应用程序域。</span><span class="sxs-lookup"><span data-stu-id="b0eca-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0eca-104">语法</span><span class="sxs-lookup"><span data-stu-id="b0eca-104">Syntax</span></span>  
  
```  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b0eca-105">参数</span><span class="sxs-lookup"><span data-stu-id="b0eca-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="b0eca-106">[in]指向一个表示包含给定应用程序域的过程的 ICorDebugProcess 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="b0eca-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="b0eca-107">[in]指向一个表示已退出的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="b0eca-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0eca-108">要求</span><span class="sxs-lookup"><span data-stu-id="b0eca-108">Requirements</span></span>  
 <span data-ttu-id="b0eca-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b0eca-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0eca-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0eca-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0eca-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0eca-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0eca-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0eca-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0eca-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0eca-113">See Also</span></span>  
 [<span data-ttu-id="b0eca-114">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="b0eca-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
