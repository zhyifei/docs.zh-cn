---
title: ICorDebugController::EnumerateThreads 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73b84179717e4b96a5c3637b85ae936a23bbf42d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748863"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="d2b7c-102">ICorDebugController::EnumerateThreads 方法</span><span class="sxs-lookup"><span data-stu-id="d2b7c-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="d2b7c-103">获取进程中活动的托管线程的枚举数。</span><span class="sxs-lookup"><span data-stu-id="d2b7c-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2b7c-104">语法</span><span class="sxs-lookup"><span data-stu-id="d2b7c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2b7c-105">参数</span><span class="sxs-lookup"><span data-stu-id="d2b7c-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="d2b7c-106">[out]指向一个"ICorDebugThreadEnum"对象，表示进程中处于活动状态的所有托管线程的枚举器的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="d2b7c-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2b7c-107">备注</span><span class="sxs-lookup"><span data-stu-id="d2b7c-107">Remarks</span></span>  
 <span data-ttu-id="d2b7c-108">一个线程被视为活动后[icordebugmanagedcallback:: Createthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md)调度回调之前[icordebugmanagedcallback:: Exitthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md)调度回调.</span><span class="sxs-lookup"><span data-stu-id="d2b7c-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="d2b7c-109">托管的线程可能不一定包含任何托管的帧的堆栈上。</span><span class="sxs-lookup"><span data-stu-id="d2b7c-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="d2b7c-110">即使之前枚举线程[icordebugmanagedcallback:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="d2b7c-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="d2b7c-111">枚举自然地将为空。</span><span class="sxs-lookup"><span data-stu-id="d2b7c-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2b7c-112">要求</span><span class="sxs-lookup"><span data-stu-id="d2b7c-112">Requirements</span></span>  
 <span data-ttu-id="d2b7c-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d2b7c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2b7c-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2b7c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2b7c-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2b7c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2b7c-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2b7c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2b7c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2b7c-117">See also</span></span>
