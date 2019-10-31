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
ms.openlocfilehash: 21da69d4bff0f17eb607dda45fb7dbafea8c59f7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128772"
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="3efc1-102">ICorDebugProcess::IsOSSuspended 方法</span><span class="sxs-lookup"><span data-stu-id="3efc1-102">ICorDebugProcess::IsOSSuspended Method</span></span>
<span data-ttu-id="3efc1-103">获取一个值，该值指示是否由于调试器停止此进程而挂起了指定线程。</span><span class="sxs-lookup"><span data-stu-id="3efc1-103">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3efc1-104">语法</span><span class="sxs-lookup"><span data-stu-id="3efc1-104">Syntax</span></span>  
  
```cpp  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3efc1-105">参数</span><span class="sxs-lookup"><span data-stu-id="3efc1-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="3efc1-106">中相关线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="3efc1-106">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="3efc1-107">弄一个指向布尔值的指针，如果指定线程已挂起，则该指针 `true`;否则为 `false``pbSuspended`。</span><span class="sxs-lookup"><span data-stu-id="3efc1-107">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise \*`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3efc1-108">备注</span><span class="sxs-lookup"><span data-stu-id="3efc1-108">Remarks</span></span>  
 <span data-ttu-id="3efc1-109">当由于调试器停止此进程而暂停指定的线程时，指定线程的 Win32 挂起计数将递增1。</span><span class="sxs-lookup"><span data-stu-id="3efc1-109">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="3efc1-110">如果调试器用户界面（UI）向用户显示线程的操作系统（OS）挂起计数，则可能需要考虑此信息。</span><span class="sxs-lookup"><span data-stu-id="3efc1-110">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="3efc1-111">`IsOSSuspended` 方法仅在非托管调试的上下文中有意义。</span><span class="sxs-lookup"><span data-stu-id="3efc1-111">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="3efc1-112">在托管调试期间，线程会以协作方式暂停，而不是由 OS 挂起。</span><span class="sxs-lookup"><span data-stu-id="3efc1-112">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3efc1-113">要求</span><span class="sxs-lookup"><span data-stu-id="3efc1-113">Requirements</span></span>  
 <span data-ttu-id="3efc1-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3efc1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3efc1-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3efc1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3efc1-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3efc1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3efc1-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3efc1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
