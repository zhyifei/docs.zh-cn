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
ms.openlocfilehash: 4380b8a3803e164aab7318821a9dbde32ecc3a0b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781743"
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a><span data-ttu-id="e8dab-102">ICorDebugManagedCallback::ExitProcess 方法</span><span class="sxs-lookup"><span data-stu-id="e8dab-102">ICorDebugManagedCallback::ExitProcess Method</span></span>
<span data-ttu-id="e8dab-103">通知调试器进程已退出。</span><span class="sxs-lookup"><span data-stu-id="e8dab-103">Notifies the debugger that a process has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8dab-104">语法</span><span class="sxs-lookup"><span data-stu-id="e8dab-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8dab-105">参数</span><span class="sxs-lookup"><span data-stu-id="e8dab-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="e8dab-106">中指向表示进程的 ICorDebugProcess 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="e8dab-106">[in] A pointer to an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8dab-107">备注</span><span class="sxs-lookup"><span data-stu-id="e8dab-107">Remarks</span></span>  
 <span data-ttu-id="e8dab-108">无法从 `ExitProcess` 事件继续。</span><span class="sxs-lookup"><span data-stu-id="e8dab-108">You cannot continue from an `ExitProcess` event.</span></span> <span data-ttu-id="e8dab-109">此事件可能会在进程显示为停止时异步激发其他事件。</span><span class="sxs-lookup"><span data-stu-id="e8dab-109">This event may fire asynchronously to other events while the process appears to be stopped.</span></span> <span data-ttu-id="e8dab-110">如果进程在停止时终止，通常是由某个外部强制导致的，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="e8dab-110">This can occur if the process terminates while stopped, usually due to some external force.</span></span>  
  
 <span data-ttu-id="e8dab-111">如果公共语言运行时（CLR）已在调度托管回调，则此事件将被延迟，直到该回调返回。</span><span class="sxs-lookup"><span data-stu-id="e8dab-111">If the common language runtime (CLR) is already dispatching a managed callback, this event will be delayed until after that callback has returned.</span></span>  
  
 <span data-ttu-id="e8dab-112">`ExitProcess` 事件是唯一可保证在关闭时调用的退出/卸载事件。</span><span class="sxs-lookup"><span data-stu-id="e8dab-112">The `ExitProcess` event is the only exit/unload event that is guaranteed to get called on shutdown.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8dab-113">需求</span><span class="sxs-lookup"><span data-stu-id="e8dab-113">Requirements</span></span>  
 <span data-ttu-id="e8dab-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e8dab-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8dab-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8dab-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8dab-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8dab-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8dab-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8dab-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8dab-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8dab-118">See also</span></span>

- [<span data-ttu-id="e8dab-119">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="e8dab-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
