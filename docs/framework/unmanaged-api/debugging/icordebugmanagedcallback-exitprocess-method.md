---
title: ICorDebugManagedCallback::ExitProcess 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type:
- apiref
ms.openlocfilehash: 4518637eb47acf416a02c045f8ca6f8a90167277
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130778"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="1e549-102">ICorDebugManagedCallback::ExitProcess 方法</span><span class="sxs-lookup"><span data-stu-id="1e549-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="1e549-103">通知调试器进程已退出。</span><span class="sxs-lookup"><span data-stu-id="1e549-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e549-104">语法</span><span class="sxs-lookup"><span data-stu-id="1e549-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e549-105">参数</span><span class="sxs-lookup"><span data-stu-id="1e549-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="1e549-106">中指向表示进程的 ICorDebugProcess 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="1e549-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e549-107">备注</span><span class="sxs-lookup"><span data-stu-id="1e549-107">Remarks</span></span>  
 <span data-ttu-id="1e549-108">无法从 `ExitProcess` 事件继续。</span><span class="sxs-lookup"><span data-stu-id="1e549-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="1e549-109">此事件可能会在进程显示为停止时异步激发其他事件。</span><span class="sxs-lookup"><span data-stu-id="1e549-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="1e549-110">如果进程在停止时终止，通常是由某个外部强制导致的，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="1e549-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="1e549-111">如果公共语言运行时（CLR）已在调度托管回调，则此事件将被延迟，直到该回调返回。</span><span class="sxs-lookup"><span data-stu-id="1e549-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="1e549-112">`ExitProcess` 事件是唯一可保证在关闭时调用的退出/卸载事件。</span><span class="sxs-lookup"><span data-stu-id="1e549-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e549-113">要求</span><span class="sxs-lookup"><span data-stu-id="1e549-113">Requirements</span></span>  
 <span data-ttu-id="1e549-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1e549-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e549-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e549-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e549-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e549-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e549-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e549-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e549-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e549-118">See also</span></span>

- [<span data-ttu-id="1e549-119">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="1e549-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
