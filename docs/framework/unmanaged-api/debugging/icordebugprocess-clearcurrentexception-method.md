---
title: ICorDebugProcess::ClearCurrentException 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ClearCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ClearCurrentException
helpviewer_keywords:
- ClearCurrentException method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::ClearCurrentException method [.NET Framework debugging]
ms.assetid: 9e02ee1a-e495-4578-bfb5-b946274bede7
topic_type:
- apiref
ms.openlocfilehash: 37a7d8fa4439d52db3cddfff22ac6580b19af58a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128912"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="72525-102">ICorDebugProcess::ClearCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="72525-102">ICorDebugProcess::ClearCurrentException Method</span></span>
<span data-ttu-id="72525-103">清除给定线程上的当前非托管异常。</span><span class="sxs-lookup"><span data-stu-id="72525-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72525-104">语法</span><span class="sxs-lookup"><span data-stu-id="72525-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72525-105">参数</span><span class="sxs-lookup"><span data-stu-id="72525-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="72525-106">中将清除当前非托管异常的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="72525-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72525-107">备注</span><span class="sxs-lookup"><span data-stu-id="72525-107">Remarks</span></span>  
 <span data-ttu-id="72525-108">在线程报告了应被调试对象忽略的非托管异常之前，请在调用[ICorDebugController：： Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)之前调用此方法。</span><span class="sxs-lookup"><span data-stu-id="72525-108">Call this method before calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="72525-109">这会清除给定线程上未完成的带内（IB）和带外（OOB）事件。</span><span class="sxs-lookup"><span data-stu-id="72525-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="72525-110">自动清除所有 OOB 断点和单步例外。</span><span class="sxs-lookup"><span data-stu-id="72525-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="72525-111">使用[ICorDebugThread2：： InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)来截获线程上的当前托管异常。</span><span class="sxs-lookup"><span data-stu-id="72525-111">Use [ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72525-112">要求</span><span class="sxs-lookup"><span data-stu-id="72525-112">Requirements</span></span>  
 <span data-ttu-id="72525-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="72525-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72525-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72525-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72525-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72525-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72525-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72525-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
