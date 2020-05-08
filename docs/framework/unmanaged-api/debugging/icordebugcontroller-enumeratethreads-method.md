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
ms.openlocfilehash: 4d69f13d4716b43c815148ff0fe4aa087b57c6e5
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892752"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="62404-102">ICorDebugController::EnumerateThreads 方法</span><span class="sxs-lookup"><span data-stu-id="62404-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="62404-103">获取进程中活动托管线程的枚举器。</span><span class="sxs-lookup"><span data-stu-id="62404-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62404-104">语法</span><span class="sxs-lookup"><span data-stu-id="62404-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62404-105">参数</span><span class="sxs-lookup"><span data-stu-id="62404-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="62404-106">弄一个指向 "ICorDebugThreadEnum" 对象地址的指针，该对象表示在进程中处于活动状态的所有托管线程的枚举器。</span><span class="sxs-lookup"><span data-stu-id="62404-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62404-107">备注</span><span class="sxs-lookup"><span data-stu-id="62404-107">Remarks</span></span>  
 <span data-ttu-id="62404-108">在调度了[ICorDebugManagedCallback：： CreateThread](icordebugmanagedcallback-createthread-method.md)回调之后以及在调度[ICorDebugManagedCallback：： ExitThread](icordebugmanagedcallback-exitthread-method.md)回调之前，线程被视为处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="62404-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="62404-109">托管线程在其堆栈上可能不一定有任何托管帧。</span><span class="sxs-lookup"><span data-stu-id="62404-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="62404-110">甚至可以在[ICorDebugManagedCallback：： CreateProcess](icordebugmanagedcallback-createprocess-method.md)回调之前枚举线程。</span><span class="sxs-lookup"><span data-stu-id="62404-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="62404-111">枚举自然将为空。</span><span class="sxs-lookup"><span data-stu-id="62404-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62404-112">要求</span><span class="sxs-lookup"><span data-stu-id="62404-112">Requirements</span></span>  
 <span data-ttu-id="62404-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="62404-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62404-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62404-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62404-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62404-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62404-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62404-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62404-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62404-117">See also</span></span>
