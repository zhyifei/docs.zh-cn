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
ms.openlocfilehash: 7bfa71ccff4a65e72a6b548a09d27648b67c0ae5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781856"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="823e2-102">ICorDebugManagedCallback::ExitAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="823e2-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>
<span data-ttu-id="823e2-103">通知调试器应用程序域已退出。</span><span class="sxs-lookup"><span data-stu-id="823e2-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="823e2-104">语法</span><span class="sxs-lookup"><span data-stu-id="823e2-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="823e2-105">参数</span><span class="sxs-lookup"><span data-stu-id="823e2-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="823e2-106">中指向 ICorDebugProcess 对象的指针，该对象表示包含给定应用程序域的进程。</span><span class="sxs-lookup"><span data-stu-id="823e2-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="823e2-107">中指向 ICorDebugAppDomain 对象的指针，该对象表示已退出的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="823e2-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="823e2-108">需求</span><span class="sxs-lookup"><span data-stu-id="823e2-108">Requirements</span></span>  
 <span data-ttu-id="823e2-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="823e2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="823e2-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="823e2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="823e2-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="823e2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="823e2-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="823e2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="823e2-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="823e2-113">See also</span></span>

- [<span data-ttu-id="823e2-114">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="823e2-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
