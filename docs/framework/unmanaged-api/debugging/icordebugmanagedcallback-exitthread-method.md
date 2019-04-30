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
ms.openlocfilehash: 37815d8aead1ec89826c13db6f012f2cd17bc792
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988177"
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="97eb2-102">ICorDebugManagedCallback::ExitThread 方法</span><span class="sxs-lookup"><span data-stu-id="97eb2-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="97eb2-103">通知调试器执行托管的代码的线程已退出。</span><span class="sxs-lookup"><span data-stu-id="97eb2-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97eb2-104">语法</span><span class="sxs-lookup"><span data-stu-id="97eb2-104">Syntax</span></span>  
  
```  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97eb2-105">参数</span><span class="sxs-lookup"><span data-stu-id="97eb2-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="97eb2-106">[in]指向一个 ICorDebugAppDomain 对象，表示包含托管的线程的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="97eb2-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="97eb2-107">[in]指向表示托管的线程的 ICorDebugThread 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="97eb2-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97eb2-108">备注</span><span class="sxs-lookup"><span data-stu-id="97eb2-108">Remarks</span></span>  
 <span data-ttu-id="97eb2-109">一次`ExitThread`触发回调，该线程将不再显示在线程枚举中。</span><span class="sxs-lookup"><span data-stu-id="97eb2-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97eb2-110">要求</span><span class="sxs-lookup"><span data-stu-id="97eb2-110">Requirements</span></span>  
 <span data-ttu-id="97eb2-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="97eb2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97eb2-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97eb2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97eb2-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97eb2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97eb2-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97eb2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97eb2-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="97eb2-115">See also</span></span>

- [<span data-ttu-id="97eb2-116">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="97eb2-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
