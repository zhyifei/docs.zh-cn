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
ms.openlocfilehash: 328c10c1895f65b43dc365b1be6b4ec5ef01e720
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777349"
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="32221-102">ICorDebugManagedCallback::Exception 方法</span><span class="sxs-lookup"><span data-stu-id="32221-102">ICorDebugManagedCallback::Exception Method</span></span>
<span data-ttu-id="32221-103">通知调试器已从托管代码引发了异常。</span><span class="sxs-lookup"><span data-stu-id="32221-103">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32221-104">语法</span><span class="sxs-lookup"><span data-stu-id="32221-104">Syntax</span></span>  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32221-105">参数</span><span class="sxs-lookup"><span data-stu-id="32221-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="32221-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示引发异常的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="32221-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="32221-107">中指向 ICorDebugThread 对象的指针，该对象表示引发异常的线程。</span><span class="sxs-lookup"><span data-stu-id="32221-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="32221-108">中如果 `false`此值，则应用程序尚未处理异常;否则，异常未处理，将终止进程。</span><span class="sxs-lookup"><span data-stu-id="32221-108">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32221-109">备注</span><span class="sxs-lookup"><span data-stu-id="32221-109">Remarks</span></span>  
 <span data-ttu-id="32221-110">可以从线程对象中检索特定的异常。</span><span class="sxs-lookup"><span data-stu-id="32221-110">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32221-111">需求</span><span class="sxs-lookup"><span data-stu-id="32221-111">Requirements</span></span>  
 <span data-ttu-id="32221-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="32221-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32221-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="32221-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="32221-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32221-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32221-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32221-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32221-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32221-116">See also</span></span>

- [<span data-ttu-id="32221-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="32221-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
