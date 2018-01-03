---
title: "ICorDebugManagedCallback::CreateProcess 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.CreateProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::CreateProcess
helpviewer_keywords:
- ICorDebugManagedCallback::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: 8e89d5ee-e4e3-4738-8302-0b7d1cf4846e
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 14c2219f1a328b3e48380c7c31f705b79da3b1ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="c34b1-102">ICorDebugManagedCallback::CreateProcess 方法</span><span class="sxs-lookup"><span data-stu-id="c34b1-102">ICorDebugManagedCallback::CreateProcess Method</span></span>
<span data-ttu-id="c34b1-103">附加进程或将其第一次启动时，请通知调试器。</span><span class="sxs-lookup"><span data-stu-id="c34b1-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c34b1-104">语法</span><span class="sxs-lookup"><span data-stu-id="c34b1-104">Syntax</span></span>  
  
```  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c34b1-105">参数</span><span class="sxs-lookup"><span data-stu-id="c34b1-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="c34b1-106">[in]指向一个 ICorDebugProcess 对象，表示附加到进程或启动的进程的指针。</span><span class="sxs-lookup"><span data-stu-id="c34b1-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c34b1-107">备注</span><span class="sxs-lookup"><span data-stu-id="c34b1-107">Remarks</span></span>  
 <span data-ttu-id="c34b1-108">在初始化公共语言运行时之前，不调用此方法。</span><span class="sxs-lookup"><span data-stu-id="c34b1-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="c34b1-109">大部分[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)方法将返回之前的 CORDBG_E_NOTREADY`CreateProcess`回调。</span><span class="sxs-lookup"><span data-stu-id="c34b1-109">Most of the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c34b1-110">惠?</span><span class="sxs-lookup"><span data-stu-id="c34b1-110">Requirements</span></span>  
 <span data-ttu-id="c34b1-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c34b1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c34b1-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c34b1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c34b1-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c34b1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c34b1-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c34b1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c34b1-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="c34b1-115">See Also</span></span>  
 [<span data-ttu-id="c34b1-116">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="c34b1-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
