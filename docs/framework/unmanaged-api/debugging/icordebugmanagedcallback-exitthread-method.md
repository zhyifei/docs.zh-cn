---
title: ICorDebugManagedCallback::ExitThread 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitThread
helpviewer_keywords:
- ExitThread method [.NET Framework debugging]
- ICorDebugManagedCallback::ExitThread method [.NET Framework debugging]
ms.assetid: 62db708b-6cf0-45c5-b897-4b5c75bd2505
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85247f2f3672e7827f4dd0c93e50cd5da914ee8f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755773"
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="9ae93-102">ICorDebugManagedCallback::ExitThread 方法</span><span class="sxs-lookup"><span data-stu-id="9ae93-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="9ae93-103">通知调试器执行托管的代码的线程已退出。</span><span class="sxs-lookup"><span data-stu-id="9ae93-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ae93-104">语法</span><span class="sxs-lookup"><span data-stu-id="9ae93-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ae93-105">参数</span><span class="sxs-lookup"><span data-stu-id="9ae93-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="9ae93-106">[in]指向一个 ICorDebugAppDomain 对象，表示包含托管的线程的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="9ae93-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="9ae93-107">[in]指向表示托管的线程的 ICorDebugThread 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="9ae93-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ae93-108">备注</span><span class="sxs-lookup"><span data-stu-id="9ae93-108">Remarks</span></span>  
 <span data-ttu-id="9ae93-109">一次`ExitThread`触发回调，该线程将不再显示在线程枚举中。</span><span class="sxs-lookup"><span data-stu-id="9ae93-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ae93-110">要求</span><span class="sxs-lookup"><span data-stu-id="9ae93-110">Requirements</span></span>  
 <span data-ttu-id="9ae93-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9ae93-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ae93-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ae93-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ae93-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ae93-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ae93-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ae93-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ae93-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ae93-115">See also</span></span>

- [<span data-ttu-id="9ae93-116">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="9ae93-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
