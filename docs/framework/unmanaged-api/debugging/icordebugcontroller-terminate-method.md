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
ms.openlocfilehash: 851a127c117b826c271dd021c41cfdb36045a1ff
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783745"
---
# <a name="icordebugcontrollerterminate-method"></a><span data-ttu-id="846d6-102">ICorDebugController::Terminate 方法</span><span class="sxs-lookup"><span data-stu-id="846d6-102">ICorDebugController::Terminate Method</span></span>
<span data-ttu-id="846d6-103">用指定的退出代码终止进程。</span><span class="sxs-lookup"><span data-stu-id="846d6-103">Terminates the process with the specified exit code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="846d6-104">此方法是 Win32 `TerminateProcess` 函数的包装器。</span><span class="sxs-lookup"><span data-stu-id="846d6-104">This method is a wrapper for the Win32 `TerminateProcess` function.</span></span> <span data-ttu-id="846d6-105">因此，`Terminate` 以 Win32 `TerminateProcess` 函数使用的相同方式使用退出代码。</span><span class="sxs-lookup"><span data-stu-id="846d6-105">Thus, `Terminate` uses the exit code in the same way that the Win32 `TerminateProcess` function uses it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="846d6-106">语法</span><span class="sxs-lookup"><span data-stu-id="846d6-106">Syntax</span></span>  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="846d6-107">参数</span><span class="sxs-lookup"><span data-stu-id="846d6-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="846d6-108">中一个表示退出代码的数字值。</span><span class="sxs-lookup"><span data-stu-id="846d6-108">[in] A numeric value that is the exit code.</span></span> <span data-ttu-id="846d6-109">有效的数值是在 Winbase.h 中定义的。</span><span class="sxs-lookup"><span data-stu-id="846d6-109">The valid numeric values are defined in Winbase.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="846d6-110">备注</span><span class="sxs-lookup"><span data-stu-id="846d6-110">Remarks</span></span>  
 <span data-ttu-id="846d6-111">如果在调用 `Terminate` 时停止该进程，则应使用[ICorDebugController：： Continue](icordebugcontroller-continue-method.md)方法继续此过程，以便调试器通过[ICorDebugManagedCallback：： ExitProcess](icordebugmanagedcallback-exitprocess-method.md)或[ICorDebugManagedCallback：： ExitAppDomain](icordebugmanagedcallback-exitappdomain-method.md)回调接收终止确认。</span><span class="sxs-lookup"><span data-stu-id="846d6-111">If the process is stopped when `Terminate` is called, the process should be continued by using the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method so that the debugger receives confirmation of the termination through the [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) or [ICorDebugManagedCallback::ExitAppDomain](icordebugmanagedcallback-exitappdomain-method.md) callback.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="846d6-112">此方法不是由应用程序域实现的。</span><span class="sxs-lookup"><span data-stu-id="846d6-112">This method is not implemented by an application domain.</span></span> <span data-ttu-id="846d6-113">也就是说，它不是在 <xref:System.AppDomain> 级别实现的。</span><span class="sxs-lookup"><span data-stu-id="846d6-113">That is, it is not implemented at the <xref:System.AppDomain> level.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="846d6-114">需求</span><span class="sxs-lookup"><span data-stu-id="846d6-114">Requirements</span></span>  
 <span data-ttu-id="846d6-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="846d6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="846d6-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="846d6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="846d6-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="846d6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="846d6-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="846d6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="846d6-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="846d6-119">See also</span></span>
