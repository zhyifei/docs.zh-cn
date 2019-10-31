---
title: ICorDebugManagedCallback::DebuggerError 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.DebuggerError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type:
- apiref
ms.openlocfilehash: c03be2405e1ab0287a2921b6e2e293862c67a193
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137377"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="8ceed-102">ICorDebugManagedCallback::DebuggerError 方法</span><span class="sxs-lookup"><span data-stu-id="8ceed-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="8ceed-103">通知调试器在尝试处理来自公共语言运行时（CLR）的事件时出错。</span><span class="sxs-lookup"><span data-stu-id="8ceed-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ceed-104">语法</span><span class="sxs-lookup"><span data-stu-id="8ceed-104">Syntax</span></span>  
  
```cpp  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ceed-105">参数</span><span class="sxs-lookup"><span data-stu-id="8ceed-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="8ceed-106">中一个指向 "ICorDebugProcess" 对象的指针，该对象表示发生事件的进程。</span><span class="sxs-lookup"><span data-stu-id="8ceed-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="8ceed-107">中从事件处理程序返回的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="8ceed-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="8ceed-108">中一个整数，指定 CLR 错误。</span><span class="sxs-lookup"><span data-stu-id="8ceed-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ceed-109">备注</span><span class="sxs-lookup"><span data-stu-id="8ceed-109">Remarks</span></span>  
 <span data-ttu-id="8ceed-110">根据错误的性质，此过程可能会置于直通模式下。</span><span class="sxs-lookup"><span data-stu-id="8ceed-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="8ceed-111">`DebugError` 回调指示调试服务由于错误而被禁用，因此调试器应向用户提供错误消息。</span><span class="sxs-lookup"><span data-stu-id="8ceed-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="8ceed-112">[ICorDebugProcess：： GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)可以安全调用，但所有其他方法（包括[ICorDebug：： Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)）都不应调用。</span><span class="sxs-lookup"><span data-stu-id="8ceed-112">[ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="8ceed-113">调试器应使用操作系统工具来终止进程。</span><span class="sxs-lookup"><span data-stu-id="8ceed-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ceed-114">要求</span><span class="sxs-lookup"><span data-stu-id="8ceed-114">Requirements</span></span>  
 <span data-ttu-id="8ceed-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8ceed-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ceed-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ceed-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ceed-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ceed-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ceed-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ceed-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ceed-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ceed-119">See also</span></span>

- [<span data-ttu-id="8ceed-120">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="8ceed-120">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
