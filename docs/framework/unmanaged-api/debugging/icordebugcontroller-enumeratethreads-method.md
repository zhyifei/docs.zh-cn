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
ms.openlocfilehash: 291f6c05171b5e507afaa70537aafdc9002a506e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125411"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="bbcd7-102">ICorDebugController::EnumerateThreads 方法</span><span class="sxs-lookup"><span data-stu-id="bbcd7-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="bbcd7-103">获取进程中活动托管线程的枚举器。</span><span class="sxs-lookup"><span data-stu-id="bbcd7-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbcd7-104">语法</span><span class="sxs-lookup"><span data-stu-id="bbcd7-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbcd7-105">参数</span><span class="sxs-lookup"><span data-stu-id="bbcd7-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="bbcd7-106">弄一个指向 "ICorDebugThreadEnum" 对象地址的指针，该对象表示在进程中处于活动状态的所有托管线程的枚举器。</span><span class="sxs-lookup"><span data-stu-id="bbcd7-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbcd7-107">备注</span><span class="sxs-lookup"><span data-stu-id="bbcd7-107">Remarks</span></span>  
 <span data-ttu-id="bbcd7-108">在调度了[ICorDebugManagedCallback：： CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md)回调之后以及在调度[ICorDebugManagedCallback：： ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md)回调之前，线程被视为处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="bbcd7-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="bbcd7-109">托管线程在其堆栈上可能不一定有任何托管帧。</span><span class="sxs-lookup"><span data-stu-id="bbcd7-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="bbcd7-110">甚至可以在[ICorDebugManagedCallback：： CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)回调之前枚举线程。</span><span class="sxs-lookup"><span data-stu-id="bbcd7-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="bbcd7-111">枚举自然将为空。</span><span class="sxs-lookup"><span data-stu-id="bbcd7-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbcd7-112">要求</span><span class="sxs-lookup"><span data-stu-id="bbcd7-112">Requirements</span></span>  
 <span data-ttu-id="bbcd7-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bbcd7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbcd7-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bbcd7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bbcd7-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbcd7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbcd7-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbcd7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbcd7-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="bbcd7-117">See also</span></span>
