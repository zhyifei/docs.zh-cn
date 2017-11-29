---
title: "ICorDebugController::Terminate 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.Terminate
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fb3831e2640de8ad34299695b571cb4071974bd6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="f2adb-102">ICorDebugController::Terminate 方法</span><span class="sxs-lookup"><span data-stu-id="f2adb-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="f2adb-103">终止指定的退出代码的进程。</span><span class="sxs-lookup"><span data-stu-id="f2adb-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2adb-104">此方法是 Win32 的包装器`TerminateProcess`函数。</span><span class="sxs-lookup"><span data-stu-id="f2adb-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="f2adb-105">因此，`Terminate`在同一个中使用的退出代码的方式 Win32`TerminateProcess`函数使用它。</span><span class="sxs-lookup"><span data-stu-id="f2adb-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2adb-106">语法</span><span class="sxs-lookup"><span data-stu-id="f2adb-106">Syntax</span></span>  
  
```  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2adb-107">参数</span><span class="sxs-lookup"><span data-stu-id="f2adb-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="f2adb-108">[in]数字值，退出代码。</span><span class="sxs-lookup"><span data-stu-id="f2adb-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="f2adb-109">Winbase.h 中定义的有效的数字值。</span><span class="sxs-lookup"><span data-stu-id="f2adb-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2adb-110">备注</span><span class="sxs-lookup"><span data-stu-id="f2adb-110">Remarks</span></span>  
 <span data-ttu-id="f2adb-111">如果该进程已停止时`Terminate`是调用，该过程继续使用[icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)方法，以便调试器接收确认通过终止[Icordebugmanagedcallback:: Exitprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)或[icordebugmanagedcallback:: Exitappdomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="f2adb-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2adb-112">此方法由不实现应用程序域。</span><span class="sxs-lookup"><span data-stu-id="f2adb-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="f2adb-113">也就是说，未实现在<xref:System.AppDomain>级别。</span><span class="sxs-lookup"><span data-stu-id="f2adb-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2adb-114">要求</span><span class="sxs-lookup"><span data-stu-id="f2adb-114">Requirements</span></span>  
 <span data-ttu-id="f2adb-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f2adb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2adb-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2adb-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2adb-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2adb-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2adb-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2adb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2adb-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2adb-119">See Also</span></span>  
 
