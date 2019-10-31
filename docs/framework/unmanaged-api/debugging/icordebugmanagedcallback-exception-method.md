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
ms.openlocfilehash: af2dab65629093401219f1016538b912bee4d067
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130828"
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="5d10e-102">ICorDebugManagedCallback::Exception 方法</span><span class="sxs-lookup"><span data-stu-id="5d10e-102">ICorDebugManagedCallback::Exception Method</span></span>
<span data-ttu-id="5d10e-103">通知调试器已从托管代码引发了异常。</span><span class="sxs-lookup"><span data-stu-id="5d10e-103">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d10e-104">语法</span><span class="sxs-lookup"><span data-stu-id="5d10e-104">Syntax</span></span>  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d10e-105">参数</span><span class="sxs-lookup"><span data-stu-id="5d10e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5d10e-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示引发异常的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="5d10e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="5d10e-107">中指向 ICorDebugThread 对象的指针，该对象表示引发异常的线程。</span><span class="sxs-lookup"><span data-stu-id="5d10e-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="5d10e-108">中如果 `false`此值，则应用程序尚未处理异常;否则，异常未处理，将终止进程。</span><span class="sxs-lookup"><span data-stu-id="5d10e-108">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d10e-109">备注</span><span class="sxs-lookup"><span data-stu-id="5d10e-109">Remarks</span></span>  
 <span data-ttu-id="5d10e-110">可以从线程对象中检索特定的异常。</span><span class="sxs-lookup"><span data-stu-id="5d10e-110">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d10e-111">要求</span><span class="sxs-lookup"><span data-stu-id="5d10e-111">Requirements</span></span>  
 <span data-ttu-id="5d10e-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5d10e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d10e-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d10e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d10e-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d10e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d10e-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d10e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d10e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d10e-116">See also</span></span>

- [<span data-ttu-id="5d10e-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="5d10e-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
