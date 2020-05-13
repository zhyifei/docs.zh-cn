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
ms.openlocfilehash: 2d0461709accf1a9300c072b62bd58734cb33fb8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209807"
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="dbc5e-102">ICorDebugManagedCallback::Exception 方法</span><span class="sxs-lookup"><span data-stu-id="dbc5e-102">ICorDebugManagedCallback::Exception Method</span></span>
<span data-ttu-id="dbc5e-103">通知调试器已从托管代码引发了异常。</span><span class="sxs-lookup"><span data-stu-id="dbc5e-103">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbc5e-104">语法</span><span class="sxs-lookup"><span data-stu-id="dbc5e-104">Syntax</span></span>  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbc5e-105">参数</span><span class="sxs-lookup"><span data-stu-id="dbc5e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="dbc5e-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示引发异常的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="dbc5e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="dbc5e-107">中指向 ICorDebugThread 对象的指针，该对象表示引发异常的线程。</span><span class="sxs-lookup"><span data-stu-id="dbc5e-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="dbc5e-108">中如果此值为 `false` ，则应用程序尚未处理异常; 否则，异常未得到处理，将终止进程。</span><span class="sxs-lookup"><span data-stu-id="dbc5e-108">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbc5e-109">备注</span><span class="sxs-lookup"><span data-stu-id="dbc5e-109">Remarks</span></span>  
 <span data-ttu-id="dbc5e-110">可以从线程对象中检索特定的异常。</span><span class="sxs-lookup"><span data-stu-id="dbc5e-110">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbc5e-111">要求</span><span class="sxs-lookup"><span data-stu-id="dbc5e-111">Requirements</span></span>  
 <span data-ttu-id="dbc5e-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dbc5e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbc5e-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbc5e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbc5e-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbc5e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbc5e-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbc5e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbc5e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="dbc5e-116">See also</span></span>

- [<span data-ttu-id="dbc5e-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="dbc5e-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
