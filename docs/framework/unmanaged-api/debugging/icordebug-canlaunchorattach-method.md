---
title: "ICorDebug::CanLaunchOrAttach 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebug.CanLaunchOrAttach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CanLaunchOrAttach
helpviewer_keywords:
- ICorDebug::CanLaunchOrAttach method [.NET Framework debugging]
- CanLaunchOrAttach method [.NET Framework debugging]
ms.assetid: ca7723db-7c07-4cdd-bd92-fba34928b623
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 62ebdb178ef7aaa16bcc163e42662e1d69f1f6f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcanlaunchorattach-method"></a><span data-ttu-id="289c7-102">ICorDebug::CanLaunchOrAttach 方法</span><span class="sxs-lookup"><span data-stu-id="289c7-102">ICorDebug::CanLaunchOrAttach Method</span></span>
<span data-ttu-id="289c7-103">返回一个 HRESULT，指示是否可以在当前的计算机和运行时配置的上下文中启动新的进程或附加到指定的现有进程。</span><span class="sxs-lookup"><span data-stu-id="289c7-103">Returns an HRESULT that indicates whether launching a new process or attaching to the specified existing process is possible within the context of the current machine and runtime configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="289c7-104">语法</span><span class="sxs-lookup"><span data-stu-id="289c7-104">Syntax</span></span>  
  
```  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="289c7-105">参数</span><span class="sxs-lookup"><span data-stu-id="289c7-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="289c7-106">[in]现有的进程 ID。</span><span class="sxs-lookup"><span data-stu-id="289c7-106">[in] The ID of an existing process.</span></span>  
  
 `win32DebuggingEnabled`  
 <span data-ttu-id="289c7-107">[in]传入`true`如果打算使用 Win32 调试启用，启动的虚拟机或模板，若要使用 Win32 调试启用的; 否则为附加传递`false`。</span><span class="sxs-lookup"><span data-stu-id="289c7-107">[in] Pass in `true` if you plan to launch with Win32 debugging enabled, or to attach with Win32 debugging enabled; otherwise, pass `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="289c7-108">返回值</span><span class="sxs-lookup"><span data-stu-id="289c7-108">Return Value</span></span>  
 <span data-ttu-id="289c7-109">如果调试服务确定启动新的进程或附加到给定的进程，则为 S_OK 是有可能，提供有关当前的计算机和运行时配置的信息。</span><span class="sxs-lookup"><span data-stu-id="289c7-109">S_OK if the debugging services determine that launching a new process or attaching to the given process is possible, given the information about the current machine and runtime configuration.</span></span> <span data-ttu-id="289c7-110">可能的 HRESULT 值有：</span><span class="sxs-lookup"><span data-stu-id="289c7-110">Possible HRESULT values are:</span></span>  
  
-   <span data-ttu-id="289c7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="289c7-111">S_OK</span></span>  
  
-   <span data-ttu-id="289c7-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span><span class="sxs-lookup"><span data-stu-id="289c7-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span></span>  
  
-   <span data-ttu-id="289c7-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span><span class="sxs-lookup"><span data-stu-id="289c7-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span></span>  
  
-   <span data-ttu-id="289c7-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span><span class="sxs-lookup"><span data-stu-id="289c7-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="289c7-115">备注</span><span class="sxs-lookup"><span data-stu-id="289c7-115">Remarks</span></span>  
 <span data-ttu-id="289c7-116">此方法是仅用于提供信息。</span><span class="sxs-lookup"><span data-stu-id="289c7-116">This method is purely informational.</span></span> <span data-ttu-id="289c7-117">接口不会停止你启动和附加到进程，而不考虑值返回的`CanLaunchOrAttach`。</span><span class="sxs-lookup"><span data-stu-id="289c7-117">The interface will not stop you from launching or attaching to a process, regardless of the value returned by `CanLaunchOrAttach`.</span></span>  
  
 <span data-ttu-id="289c7-118">如果你打算使用 Win32 调试启用启动或使用 Win32 调试启用附加，则传递`true`为`win32DebuggingEnabled`。</span><span class="sxs-lookup"><span data-stu-id="289c7-118">If you plan to launch with Win32 debugging enabled or attach with Win32 debugging enabled, pass `true` for `win32DebuggingEnabled`.</span></span> <span data-ttu-id="289c7-119">通过返回的 HRESULT`CanLaunchOrAttach`可能会与不同，如果使用此选项。</span><span class="sxs-lookup"><span data-stu-id="289c7-119">The HRESULT returned by `CanLaunchOrAttach` might differ if you use this option.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="289c7-120">惠?</span><span class="sxs-lookup"><span data-stu-id="289c7-120">Requirements</span></span>  
 <span data-ttu-id="289c7-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="289c7-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="289c7-122">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="289c7-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="289c7-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="289c7-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="289c7-124">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="289c7-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="289c7-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="289c7-125">See Also</span></span>  
 [<span data-ttu-id="289c7-126">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="289c7-126">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
