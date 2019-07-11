---
title: ICorDebugProcess::IsOSSuspended 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 275f62c8211f71f067d310dd4b3af2ddb11e93d7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755457"
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="70f80-102">ICorDebugProcess::IsOSSuspended 方法</span><span class="sxs-lookup"><span data-stu-id="70f80-102">ICorDebugProcess::IsOSSuspended Method</span></span>
<span data-ttu-id="70f80-103">获取一个值，该值指示指定的线程是否已挂起由于调试器停止此进程。</span><span class="sxs-lookup"><span data-stu-id="70f80-103">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70f80-104">语法</span><span class="sxs-lookup"><span data-stu-id="70f80-104">Syntax</span></span>  
  
```cpp  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70f80-105">参数</span><span class="sxs-lookup"><span data-stu-id="70f80-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="70f80-106">[in]有问题的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="70f80-106">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="70f80-107">[out]一个布尔值，是一个指向`true`如果指定的线程已挂起; 否则为 \*`pbSuspended`是`false`。</span><span class="sxs-lookup"><span data-stu-id="70f80-107">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise \*`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70f80-108">备注</span><span class="sxs-lookup"><span data-stu-id="70f80-108">Remarks</span></span>  
 <span data-ttu-id="70f80-109">如果指定的线程已挂起由于调试器停止此进程，指定的线程的 Win32 挂起计数会递增 1。</span><span class="sxs-lookup"><span data-stu-id="70f80-109">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="70f80-110">调试器用户界面 (UI) 可能需要考虑此信息，如果该命令显示操作系统 (OS) 挂起对用户线程的计数。</span><span class="sxs-lookup"><span data-stu-id="70f80-110">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="70f80-111">`IsOSSuspended`方法仅在中有意义的非托管调试上下文。</span><span class="sxs-lookup"><span data-stu-id="70f80-111">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="70f80-112">托管在调试期间，线程是以协作方式挂起而不是 OS 挂起。</span><span class="sxs-lookup"><span data-stu-id="70f80-112">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70f80-113">要求</span><span class="sxs-lookup"><span data-stu-id="70f80-113">Requirements</span></span>  
 <span data-ttu-id="70f80-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="70f80-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70f80-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70f80-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70f80-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70f80-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70f80-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70f80-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
