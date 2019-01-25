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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4e7b62b7eb038d553b28fbd6422175d511df88d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540541"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="f5d47-102">ICorDebugManagedCallback::ExitProcess 方法</span><span class="sxs-lookup"><span data-stu-id="f5d47-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="f5d47-103">通知调试器进程已退出。</span><span class="sxs-lookup"><span data-stu-id="f5d47-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5d47-104">语法</span><span class="sxs-lookup"><span data-stu-id="f5d47-104">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5d47-105">参数</span><span class="sxs-lookup"><span data-stu-id="f5d47-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="f5d47-106">[in]指向表示流程 ICorDebugProcess 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="f5d47-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5d47-107">备注</span><span class="sxs-lookup"><span data-stu-id="f5d47-107">Remarks</span></span>  
 <span data-ttu-id="f5d47-108">无法继续从`ExitProcess`事件。</span><span class="sxs-lookup"><span data-stu-id="f5d47-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="f5d47-109">此事件可能会与其他事件以异步方式激发，而过程似乎已停止。</span><span class="sxs-lookup"><span data-stu-id="f5d47-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="f5d47-110">如果在进程终止时停止，通常由于某种外部因素，这可能发生。</span><span class="sxs-lookup"><span data-stu-id="f5d47-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="f5d47-111">如果公共语言运行时 (CLR) 已经在调度托管的回调，将会延迟此事件，直到该回调返回。</span><span class="sxs-lookup"><span data-stu-id="f5d47-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="f5d47-112">`ExitProcess`事件是保证在关闭调用的唯一退出/卸载事件。</span><span class="sxs-lookup"><span data-stu-id="f5d47-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5d47-113">要求</span><span class="sxs-lookup"><span data-stu-id="f5d47-113">Requirements</span></span>  
 <span data-ttu-id="f5d47-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f5d47-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5d47-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5d47-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5d47-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5d47-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5d47-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5d47-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5d47-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5d47-118">See also</span></span>
- [<span data-ttu-id="f5d47-119">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="f5d47-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
