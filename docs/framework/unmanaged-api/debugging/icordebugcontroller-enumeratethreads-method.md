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
ms.openlocfilehash: 17ba15553d2e7dcd2090870eaab54b4c680631f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749340"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="eeb80-102">ICorDebugController::EnumerateThreads 方法</span><span class="sxs-lookup"><span data-stu-id="eeb80-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="eeb80-103">获取进程中活动的托管线程的枚举数。</span><span class="sxs-lookup"><span data-stu-id="eeb80-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeb80-104">语法</span><span class="sxs-lookup"><span data-stu-id="eeb80-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eeb80-105">参数</span><span class="sxs-lookup"><span data-stu-id="eeb80-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="eeb80-106">[out]指向一个"ICorDebugThreadEnum"对象，表示进程中处于活动状态的所有托管线程的枚举器的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="eeb80-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eeb80-107">备注</span><span class="sxs-lookup"><span data-stu-id="eeb80-107">Remarks</span></span>  
 <span data-ttu-id="eeb80-108">一个线程被视为活动后[icordebugmanagedcallback:: Createthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md)调度回调之前[icordebugmanagedcallback:: Exitthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md)调度回调.</span><span class="sxs-lookup"><span data-stu-id="eeb80-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="eeb80-109">托管的线程可能不一定包含任何托管的帧的堆栈上。</span><span class="sxs-lookup"><span data-stu-id="eeb80-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="eeb80-110">即使之前枚举线程[icordebugmanagedcallback:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="eeb80-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="eeb80-111">枚举自然地将为空。</span><span class="sxs-lookup"><span data-stu-id="eeb80-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eeb80-112">要求</span><span class="sxs-lookup"><span data-stu-id="eeb80-112">Requirements</span></span>  
 <span data-ttu-id="eeb80-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eeb80-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eeb80-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eeb80-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eeb80-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eeb80-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eeb80-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eeb80-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeb80-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="eeb80-117">See also</span></span>
