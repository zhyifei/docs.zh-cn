---
title: ICorDebugController::Terminate 方法
ms.date: 03/30/2017
api_name:
- ICorDebugController.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee1c30809567097e67b6b1e40f5534429d748abd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964372"
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="37eef-102">ICorDebugController::Terminate 方法</span><span class="sxs-lookup"><span data-stu-id="37eef-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="37eef-103">用指定的退出代码终止进程。</span><span class="sxs-lookup"><span data-stu-id="37eef-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="37eef-104">此方法是 Win32 `TerminateProcess`函数的包装器。</span><span class="sxs-lookup"><span data-stu-id="37eef-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="37eef-105">因此, `Terminate`使用退出代码的方式与 Win32 `TerminateProcess`函数使用的方式相同。</span><span class="sxs-lookup"><span data-stu-id="37eef-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37eef-106">语法</span><span class="sxs-lookup"><span data-stu-id="37eef-106">Syntax</span></span>  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37eef-107">参数</span><span class="sxs-lookup"><span data-stu-id="37eef-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="37eef-108">中一个表示退出代码的数字值。</span><span class="sxs-lookup"><span data-stu-id="37eef-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="37eef-109">有效的数值是在 Winbase.h 中定义的。</span><span class="sxs-lookup"><span data-stu-id="37eef-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37eef-110">备注</span><span class="sxs-lookup"><span data-stu-id="37eef-110">Remarks</span></span>  
 <span data-ttu-id="37eef-111">如果在调用时`Terminate`停止该进程, 则应使用[ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)方法继续此过程, 以便调试器通过[ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)或[ICorDebugManagedCallback:: ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="37eef-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="37eef-112">此方法不是由应用程序域实现的。</span><span class="sxs-lookup"><span data-stu-id="37eef-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="37eef-113">也就是说, 它不是在<xref:System.AppDomain>级别实现的。</span><span class="sxs-lookup"><span data-stu-id="37eef-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37eef-114">要求</span><span class="sxs-lookup"><span data-stu-id="37eef-114">Requirements</span></span>  
 <span data-ttu-id="37eef-115">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="37eef-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37eef-116">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="37eef-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37eef-117">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37eef-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37eef-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37eef-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37eef-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="37eef-119">See also</span></span>
