---
title: "ICorDebugController::EnumerateThreads 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugController.EnumerateThreads
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 61d96aa6c8ae4a50c3afbcd84033244208e2444d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="9ea54-102">ICorDebugController::EnumerateThreads 方法</span><span class="sxs-lookup"><span data-stu-id="9ea54-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="9ea54-103">在过程中获取活动的托管线程的枚举数。</span><span class="sxs-lookup"><span data-stu-id="9ea54-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ea54-104">语法</span><span class="sxs-lookup"><span data-stu-id="9ea54-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ea54-105">参数</span><span class="sxs-lookup"><span data-stu-id="9ea54-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="9ea54-106">[out]指向一个表示进程中处于活动状态的所有托管线程的枚举数"ICorDebugThreadEnum"对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="9ea54-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ea54-107">备注</span><span class="sxs-lookup"><span data-stu-id="9ea54-107">Remarks</span></span>  
 <span data-ttu-id="9ea54-108">线程将被视为活动后[icordebugmanagedcallback:: Createthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md)调度回调和之前[icordebugmanagedcallback:: Exitthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md)调度回调.</span><span class="sxs-lookup"><span data-stu-id="9ea54-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="9ea54-109">托管的线程不一定要包含任何托管的帧的堆栈上。</span><span class="sxs-lookup"><span data-stu-id="9ea54-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="9ea54-110">线程可以甚至之前枚举[icordebugmanagedcallback:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="9ea54-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="9ea54-111">在枚举自然地将为空。</span><span class="sxs-lookup"><span data-stu-id="9ea54-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ea54-112">惠?</span><span class="sxs-lookup"><span data-stu-id="9ea54-112">Requirements</span></span>  
 <span data-ttu-id="9ea54-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9ea54-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ea54-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ea54-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ea54-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ea54-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ea54-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ea54-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ea54-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ea54-117">See Also</span></span>  
 
