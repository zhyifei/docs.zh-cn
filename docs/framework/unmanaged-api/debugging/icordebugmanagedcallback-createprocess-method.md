---
title: ICorDebugManagedCallback::CreateProcess 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateProcess
helpviewer_keywords:
- ICorDebugManagedCallback::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: 8e89d5ee-e4e3-4738-8302-0b7d1cf4846e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36e26101a21471fd840a07deef9f5085a88f2730
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487026"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="2b39e-102">ICorDebugManagedCallback::CreateProcess 方法</span><span class="sxs-lookup"><span data-stu-id="2b39e-102">ICorDebugManagedCallback::CreateProcess Method</span></span>
<span data-ttu-id="2b39e-103">通知调试器已附加或第一次启动进程时。</span><span class="sxs-lookup"><span data-stu-id="2b39e-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b39e-104">语法</span><span class="sxs-lookup"><span data-stu-id="2b39e-104">Syntax</span></span>  
  
```  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b39e-105">参数</span><span class="sxs-lookup"><span data-stu-id="2b39e-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="2b39e-106">[in]指向表示已附加或启动的进程的 ICorDebugProcess 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="2b39e-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b39e-107">备注</span><span class="sxs-lookup"><span data-stu-id="2b39e-107">Remarks</span></span>  
 <span data-ttu-id="2b39e-108">初始化公共语言运行时之前，不调用此方法。</span><span class="sxs-lookup"><span data-stu-id="2b39e-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="2b39e-109">大部分[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)方法将返回之前 CORDBG_E_NOTREADY`CreateProcess`回调。</span><span class="sxs-lookup"><span data-stu-id="2b39e-109">Most of the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b39e-110">要求</span><span class="sxs-lookup"><span data-stu-id="2b39e-110">Requirements</span></span>  
 <span data-ttu-id="2b39e-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2b39e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b39e-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b39e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b39e-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b39e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b39e-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b39e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b39e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b39e-115">See also</span></span>
- [<span data-ttu-id="2b39e-116">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="2b39e-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
