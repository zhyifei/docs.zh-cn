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
ms.openlocfilehash: 2b65a621541f2b4a800f6b3708a6b257374c5866
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419814"
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="994d1-102">ICorDebugProcess::IsOSSuspended 方法</span><span class="sxs-lookup"><span data-stu-id="994d1-102">ICorDebugProcess::IsOSSuspended Method</span></span>
<span data-ttu-id="994d1-103">获取一个值，该值指示指定的线程是否已挂起由于调试器停止此过程。</span><span class="sxs-lookup"><span data-stu-id="994d1-103">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="994d1-104">语法</span><span class="sxs-lookup"><span data-stu-id="994d1-104">Syntax</span></span>  
  
```  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="994d1-105">参数</span><span class="sxs-lookup"><span data-stu-id="994d1-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="994d1-106">[in]问题的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="994d1-106">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="994d1-107">[out]一个布尔值，是一个指向`true`如果指定的线程已挂起; 否则为 \*`pbSuspended`是`false`。</span><span class="sxs-lookup"><span data-stu-id="994d1-107">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise \*`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="994d1-108">备注</span><span class="sxs-lookup"><span data-stu-id="994d1-108">Remarks</span></span>  
 <span data-ttu-id="994d1-109">当指定的线程已被暂停由于调试器停止此过程中时，指定的线程的 Win32 挂起计数就会递增 1。</span><span class="sxs-lookup"><span data-stu-id="994d1-109">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="994d1-110">调试器用户界面 (UI) 可能要将此信息打包在帐户，如果该命令显示操作系统 (OS) 挂起的用户的线程计数。</span><span class="sxs-lookup"><span data-stu-id="994d1-110">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="994d1-111">`IsOSSuspended`方法有意义仅在非托管调试上下文中。</span><span class="sxs-lookup"><span data-stu-id="994d1-111">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="994d1-112">托管在调试期间，线程是以协作方式挂起而不是操作系统挂起。</span><span class="sxs-lookup"><span data-stu-id="994d1-112">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="994d1-113">要求</span><span class="sxs-lookup"><span data-stu-id="994d1-113">Requirements</span></span>  
 <span data-ttu-id="994d1-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="994d1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="994d1-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="994d1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="994d1-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="994d1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="994d1-117">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="994d1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
