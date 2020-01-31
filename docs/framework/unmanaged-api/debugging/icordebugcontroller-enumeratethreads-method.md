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
ms.openlocfilehash: 815dc63a2dedecc613506b0f98702f58d6e7bd04
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783790"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a><span data-ttu-id="87d03-102">ICorDebugController::EnumerateThreads 方法</span><span class="sxs-lookup"><span data-stu-id="87d03-102">ICorDebugController::EnumerateThreads Method</span></span>
<span data-ttu-id="87d03-103">获取进程中活动托管线程的枚举器。</span><span class="sxs-lookup"><span data-stu-id="87d03-103">Gets an enumerator for the active managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87d03-104">语法</span><span class="sxs-lookup"><span data-stu-id="87d03-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87d03-105">参数</span><span class="sxs-lookup"><span data-stu-id="87d03-105">Parameters</span></span>  
 `ppThreads`  
 <span data-ttu-id="87d03-106">弄一个指向 "ICorDebugThreadEnum" 对象地址的指针，该对象表示在进程中处于活动状态的所有托管线程的枚举器。</span><span class="sxs-lookup"><span data-stu-id="87d03-106">[out] A pointer to the address of an "ICorDebugThreadEnum" object that represents an enumerator for all managed threads that are active in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87d03-107">备注</span><span class="sxs-lookup"><span data-stu-id="87d03-107">Remarks</span></span>  
 <span data-ttu-id="87d03-108">在调度了[ICorDebugManagedCallback：： CreateThread](icordebugmanagedcallback-createthread-method.md)回调之后以及在调度[ICorDebugManagedCallback：： ExitThread](icordebugmanagedcallback-exitthread-method.md)回调之前，线程被视为处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="87d03-108">A thread is considered active after the [ICorDebugManagedCallback::CreateThread](icordebugmanagedcallback-createthread-method.md) callback has been dispatched and before the [ICorDebugManagedCallback::ExitThread](icordebugmanagedcallback-exitthread-method.md) callback has been dispatched.</span></span> <span data-ttu-id="87d03-109">托管线程在其堆栈上可能不一定有任何托管帧。</span><span class="sxs-lookup"><span data-stu-id="87d03-109">A managed thread may not necessarily have any managed frames on its stack.</span></span> <span data-ttu-id="87d03-110">甚至可以在[ICorDebugManagedCallback：： CreateProcess](icordebugmanagedcallback-createprocess-method.md)回调之前枚举线程。</span><span class="sxs-lookup"><span data-stu-id="87d03-110">Threads can be enumerated even before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="87d03-111">枚举自然将为空。</span><span class="sxs-lookup"><span data-stu-id="87d03-111">The enumeration will naturally be empty.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87d03-112">需求</span><span class="sxs-lookup"><span data-stu-id="87d03-112">Requirements</span></span>  
 <span data-ttu-id="87d03-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="87d03-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87d03-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87d03-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87d03-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87d03-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87d03-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87d03-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d03-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87d03-117">See also</span></span>
