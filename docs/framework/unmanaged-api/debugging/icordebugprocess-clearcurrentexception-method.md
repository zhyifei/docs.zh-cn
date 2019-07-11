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
ms.openlocfilehash: 2ad7dd3ae0e547933fdf7d579116dccc62ae579c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766142"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="4bd28-102">ICorDebugProcess::ClearCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="4bd28-102">ICorDebugProcess::ClearCurrentException Method</span></span>
<span data-ttu-id="4bd28-103">清除给定线程上当前的非托管的异常。</span><span class="sxs-lookup"><span data-stu-id="4bd28-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bd28-104">语法</span><span class="sxs-lookup"><span data-stu-id="4bd28-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bd28-105">参数</span><span class="sxs-lookup"><span data-stu-id="4bd28-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="4bd28-106">[in]将被清除当前的非托管的异常的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="4bd28-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4bd28-107">备注</span><span class="sxs-lookup"><span data-stu-id="4bd28-107">Remarks</span></span>  
 <span data-ttu-id="4bd28-108">调用此方法之前调用[icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)当一个线程已报告的调试对象应该忽略非托管的异常。</span><span class="sxs-lookup"><span data-stu-id="4bd28-108">Call this method before calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="4bd28-109">这将清除未完成的带内 (IB) 和给定的线程上的带外 (OOB) 事件。</span><span class="sxs-lookup"><span data-stu-id="4bd28-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="4bd28-110">自动清除所有 OOB 断点和单步异常。</span><span class="sxs-lookup"><span data-stu-id="4bd28-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="4bd28-111">使用[ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)截获当前托管线程上的异常。</span><span class="sxs-lookup"><span data-stu-id="4bd28-111">Use [ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bd28-112">要求</span><span class="sxs-lookup"><span data-stu-id="4bd28-112">Requirements</span></span>  
 <span data-ttu-id="4bd28-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4bd28-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bd28-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4bd28-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4bd28-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bd28-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bd28-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bd28-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
