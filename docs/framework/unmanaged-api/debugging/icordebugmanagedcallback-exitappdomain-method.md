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
ms.openlocfilehash: aed6ccd938761385aafd21802829bd741847b4ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110235"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="d72f1-102">ICorDebugManagedCallback::ExitAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="d72f1-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>
<span data-ttu-id="d72f1-103">通知调试器已退出应用程序域。</span><span class="sxs-lookup"><span data-stu-id="d72f1-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d72f1-104">语法</span><span class="sxs-lookup"><span data-stu-id="d72f1-104">Syntax</span></span>  
  
```  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d72f1-105">参数</span><span class="sxs-lookup"><span data-stu-id="d72f1-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="d72f1-106">[in]指向表示包含给定的应用程序域的流程 ICorDebugProcess 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="d72f1-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="d72f1-107">[in]指向表示已退出应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="d72f1-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d72f1-108">要求</span><span class="sxs-lookup"><span data-stu-id="d72f1-108">Requirements</span></span>  
 <span data-ttu-id="d72f1-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d72f1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d72f1-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d72f1-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d72f1-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d72f1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d72f1-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d72f1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d72f1-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d72f1-113">See also</span></span>

- [<span data-ttu-id="d72f1-114">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="d72f1-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
