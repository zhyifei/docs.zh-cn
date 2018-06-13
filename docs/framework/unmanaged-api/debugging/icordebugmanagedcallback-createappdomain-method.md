---
title: ICorDebugManagedCallback::CreateAppDomain 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdac4b5b7a4a64a5fc939a7d35718ef276717fe7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415423"
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="64da0-102">ICorDebugManagedCallback::CreateAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="64da0-102">ICorDebugManagedCallback::CreateAppDomain Method</span></span>
<span data-ttu-id="64da0-103">通知调试器已创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="64da0-103">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64da0-104">语法</span><span class="sxs-lookup"><span data-stu-id="64da0-104">Syntax</span></span>  
  
```  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64da0-105">参数</span><span class="sxs-lookup"><span data-stu-id="64da0-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="64da0-106">[in]指向一个表示在其中创建应用程序域的过程的 ICorDebugProcess 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="64da0-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="64da0-107">[in]指向一个表示已创建的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="64da0-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64da0-108">要求</span><span class="sxs-lookup"><span data-stu-id="64da0-108">Requirements</span></span>  
 <span data-ttu-id="64da0-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="64da0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64da0-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64da0-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64da0-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64da0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64da0-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64da0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64da0-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="64da0-113">See Also</span></span>  
 [<span data-ttu-id="64da0-114">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="64da0-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
