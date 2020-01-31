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
ms.openlocfilehash: 35ea69d32ee9b994cc0bf91339c798edcd472f44
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788417"
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="11ab5-102">ICorDebugManagedCallback::CreateAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="11ab5-102">ICorDebugManagedCallback::CreateAppDomain Method</span></span>
<span data-ttu-id="11ab5-103">通知调试器已创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="11ab5-103">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11ab5-104">语法</span><span class="sxs-lookup"><span data-stu-id="11ab5-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11ab5-105">参数</span><span class="sxs-lookup"><span data-stu-id="11ab5-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="11ab5-106">中指向 ICorDebugProcess 对象的指针，该对象表示在其中创建应用程序域的进程。</span><span class="sxs-lookup"><span data-stu-id="11ab5-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="11ab5-107">中指向 ICorDebugAppDomain 对象的指针，该对象表示已创建的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="11ab5-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11ab5-108">需求</span><span class="sxs-lookup"><span data-stu-id="11ab5-108">Requirements</span></span>  
 <span data-ttu-id="11ab5-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="11ab5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11ab5-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11ab5-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11ab5-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11ab5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11ab5-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11ab5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11ab5-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11ab5-113">See also</span></span>

- [<span data-ttu-id="11ab5-114">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="11ab5-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
