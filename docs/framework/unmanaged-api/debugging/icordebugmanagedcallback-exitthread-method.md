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
ms.openlocfilehash: 24b01fecc7947d14e36b4411a58d200667b0f2a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415537"
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="24066-102">ICorDebugManagedCallback::ExitThread 方法</span><span class="sxs-lookup"><span data-stu-id="24066-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="24066-103">通知调试器正在执行托管的代码的线程已退出。</span><span class="sxs-lookup"><span data-stu-id="24066-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24066-104">语法</span><span class="sxs-lookup"><span data-stu-id="24066-104">Syntax</span></span>  
  
```  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="24066-105">参数</span><span class="sxs-lookup"><span data-stu-id="24066-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="24066-106">[in]指向一个表示包含托管的线程的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="24066-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="24066-107">[in]指向表示托管的线程的 ICorDebugThread 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="24066-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24066-108">备注</span><span class="sxs-lookup"><span data-stu-id="24066-108">Remarks</span></span>  
 <span data-ttu-id="24066-109">一次`ExitThread`激发回调，线程将不再显示在线程枚举中。</span><span class="sxs-lookup"><span data-stu-id="24066-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24066-110">要求</span><span class="sxs-lookup"><span data-stu-id="24066-110">Requirements</span></span>  
 <span data-ttu-id="24066-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="24066-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24066-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24066-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24066-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24066-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24066-114">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24066-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24066-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="24066-115">See Also</span></span>  
 [<span data-ttu-id="24066-116">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="24066-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
