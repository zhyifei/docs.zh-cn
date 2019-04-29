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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f014f9213a4b9a2d5119af9a6dceebb9a9d54b52
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775593"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="1fead-102">ICorDebugProcess::ClearCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="1fead-102">ICorDebugProcess::ClearCurrentException Method</span></span>
<span data-ttu-id="1fead-103">清除给定线程上当前的非托管的异常。</span><span class="sxs-lookup"><span data-stu-id="1fead-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fead-104">语法</span><span class="sxs-lookup"><span data-stu-id="1fead-104">Syntax</span></span>  
  
```  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fead-105">参数</span><span class="sxs-lookup"><span data-stu-id="1fead-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="1fead-106">[in]将被清除当前的非托管的异常的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="1fead-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fead-107">备注</span><span class="sxs-lookup"><span data-stu-id="1fead-107">Remarks</span></span>  
 <span data-ttu-id="1fead-108">调用此方法之前调用[icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)当一个线程已报告的调试对象应该忽略非托管的异常。</span><span class="sxs-lookup"><span data-stu-id="1fead-108">Call this method before calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="1fead-109">这将清除未完成的带内 (IB) 和给定的线程上的带外 (OOB) 事件。</span><span class="sxs-lookup"><span data-stu-id="1fead-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="1fead-110">自动清除所有 OOB 断点和单步异常。</span><span class="sxs-lookup"><span data-stu-id="1fead-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="1fead-111">使用[ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)截获当前托管线程上的异常。</span><span class="sxs-lookup"><span data-stu-id="1fead-111">Use [ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fead-112">要求</span><span class="sxs-lookup"><span data-stu-id="1fead-112">Requirements</span></span>  
 <span data-ttu-id="1fead-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1fead-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fead-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1fead-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fead-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fead-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fead-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fead-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
