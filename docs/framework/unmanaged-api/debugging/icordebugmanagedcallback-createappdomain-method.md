---
title: "ICorDebugManagedCallback::CreateAppDomain 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugManagedCallback.CreateAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateAppDomain
helpviewer_keywords:
- CreateAppDomain method [.NET Framework debugging]
- ICorDebugManagedCallback::CreateAppDomain method [.NET Framework debugging]
ms.assetid: 48d410d7-6749-4125-a8fd-f9562c7088e9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f0f9b6322ee391edaba73e0c222b75aa86eee7e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="1a4fc-102">ICorDebugManagedCallback::CreateAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="1a4fc-102">ICorDebugManagedCallback::CreateAppDomain Method</span></span>
<span data-ttu-id="1a4fc-103">通知调试器已创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="1a4fc-103">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a4fc-104">语法</span><span class="sxs-lookup"><span data-stu-id="1a4fc-104">Syntax</span></span>  
  
```  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a4fc-105">参数</span><span class="sxs-lookup"><span data-stu-id="1a4fc-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="1a4fc-106">[in]指向一个表示在其中创建应用程序域的过程的 ICorDebugProcess 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="1a4fc-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="1a4fc-107">[in]指向一个表示已创建的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="1a4fc-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a4fc-108">惠?</span><span class="sxs-lookup"><span data-stu-id="1a4fc-108">Requirements</span></span>  
 <span data-ttu-id="1a4fc-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1a4fc-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a4fc-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a4fc-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a4fc-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a4fc-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a4fc-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a4fc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a4fc-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a4fc-113">See Also</span></span>  
 [<span data-ttu-id="1a4fc-114">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="1a4fc-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
