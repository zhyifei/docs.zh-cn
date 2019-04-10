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
ms.openlocfilehash: 91318ea596cc7d6c8a747901fea2749a64aa2623
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168111"
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="4f824-102">ICorDebugManagedCallback::Exception 方法</span><span class="sxs-lookup"><span data-stu-id="4f824-102">ICorDebugManagedCallback::Exception Method</span></span>
<span data-ttu-id="4f824-103">通知调试器已从托管代码中引发异常。</span><span class="sxs-lookup"><span data-stu-id="4f824-103">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f824-104">语法</span><span class="sxs-lookup"><span data-stu-id="4f824-104">Syntax</span></span>  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f824-105">参数</span><span class="sxs-lookup"><span data-stu-id="4f824-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="4f824-106">[in]指向表示异常的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="4f824-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="4f824-107">[in]指向表示异常的线程的 ICorDebugThread 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="4f824-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="4f824-108">[in]如果此值为`false`、 异常尚未已由应用程序处理; 否则为未经处理异常并将终止此过程。</span><span class="sxs-lookup"><span data-stu-id="4f824-108">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f824-109">备注</span><span class="sxs-lookup"><span data-stu-id="4f824-109">Remarks</span></span>  
 <span data-ttu-id="4f824-110">可以从线程对象中检索特定的异常。</span><span class="sxs-lookup"><span data-stu-id="4f824-110">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f824-111">要求</span><span class="sxs-lookup"><span data-stu-id="4f824-111">Requirements</span></span>  
 <span data-ttu-id="4f824-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4f824-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f824-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f824-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f824-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f824-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4f824-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="4f824-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4f824-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f824-116">See also</span></span>

- [<span data-ttu-id="4f824-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="4f824-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
