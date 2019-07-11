---
title: ICorDebugManagedCallback::Exception 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Exception
helpviewer_keywords:
- Exception method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::Exception method [.NET Framework debugging]
ms.assetid: ab18a509-dff3-4930-b585-bd15e0414176
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e944a6debf790907b75760c8856ae3a365a84650
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759621"
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="04f53-102">ICorDebugManagedCallback::Exception 方法</span><span class="sxs-lookup"><span data-stu-id="04f53-102">ICorDebugManagedCallback::Exception Method</span></span>
<span data-ttu-id="04f53-103">通知调试器已从托管代码中引发异常。</span><span class="sxs-lookup"><span data-stu-id="04f53-103">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04f53-104">语法</span><span class="sxs-lookup"><span data-stu-id="04f53-104">Syntax</span></span>  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04f53-105">参数</span><span class="sxs-lookup"><span data-stu-id="04f53-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="04f53-106">[in]指向表示异常的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="04f53-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="04f53-107">[in]指向表示异常的线程的 ICorDebugThread 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="04f53-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="04f53-108">[in]如果此值为`false`、 异常尚未已由应用程序处理; 否则为未经处理异常并将终止此过程。</span><span class="sxs-lookup"><span data-stu-id="04f53-108">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04f53-109">备注</span><span class="sxs-lookup"><span data-stu-id="04f53-109">Remarks</span></span>  
 <span data-ttu-id="04f53-110">可以从线程对象中检索特定的异常。</span><span class="sxs-lookup"><span data-stu-id="04f53-110">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04f53-111">要求</span><span class="sxs-lookup"><span data-stu-id="04f53-111">Requirements</span></span>  
 <span data-ttu-id="04f53-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="04f53-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04f53-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04f53-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04f53-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04f53-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04f53-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04f53-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04f53-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="04f53-116">See also</span></span>

- [<span data-ttu-id="04f53-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="04f53-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
