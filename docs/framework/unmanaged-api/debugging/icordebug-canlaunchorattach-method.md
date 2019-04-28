---
title: ICorDebug::CanLaunchOrAttach 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0cf0065f1ed12ad3a37819b0a15d734a2b51ff5b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697772"
---
# <a name="icordebugcanlaunchorattach-method"></a><span data-ttu-id="ba619-102">ICorDebug::CanLaunchOrAttach 方法</span><span class="sxs-lookup"><span data-stu-id="ba619-102">ICorDebug::CanLaunchOrAttach Method</span></span>
<span data-ttu-id="ba619-103">返回一个 HRESULT，指示是否可以在当前的计算机和运行时配置的上下文中启动一个新的进程或附加到指定的现有进程。</span><span class="sxs-lookup"><span data-stu-id="ba619-103">Returns an HRESULT that indicates whether launching a new process or attaching to the specified existing process is possible within the context of the current machine and runtime configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba619-104">语法</span><span class="sxs-lookup"><span data-stu-id="ba619-104">Syntax</span></span>  
  
```  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba619-105">参数</span><span class="sxs-lookup"><span data-stu-id="ba619-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="ba619-106">[in]现有的进程的 ID。</span><span class="sxs-lookup"><span data-stu-id="ba619-106">[in] The ID of an existing process.</span></span>  
  
 `win32DebuggingEnabled`  
 <span data-ttu-id="ba619-107">[in]传入`true`如果打算使用 Win32 调试启用，启动或 Win32 调试已启用; 否则为附加传递`false`。</span><span class="sxs-lookup"><span data-stu-id="ba619-107">[in] Pass in `true` if you plan to launch with Win32 debugging enabled, or to attach with Win32 debugging enabled; otherwise, pass `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba619-108">返回值</span><span class="sxs-lookup"><span data-stu-id="ba619-108">Return Value</span></span>  
 <span data-ttu-id="ba619-109">如果调试服务确定启动新进程或附加到给定的进程，则返回 S_OK 提供有关当前的计算机和运行时配置的信息。</span><span class="sxs-lookup"><span data-stu-id="ba619-109">S_OK if the debugging services determine that launching a new process or attaching to the given process is possible, given the information about the current machine and runtime configuration.</span></span> <span data-ttu-id="ba619-110">可能的 HRESULT 值为：</span><span class="sxs-lookup"><span data-stu-id="ba619-110">Possible HRESULT values are:</span></span>  
  
- <span data-ttu-id="ba619-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ba619-111">S_OK</span></span>  
  
- <span data-ttu-id="ba619-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span><span class="sxs-lookup"><span data-stu-id="ba619-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span></span>  
  
- <span data-ttu-id="ba619-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span><span class="sxs-lookup"><span data-stu-id="ba619-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span></span>  
  
- <span data-ttu-id="ba619-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span><span class="sxs-lookup"><span data-stu-id="ba619-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba619-115">备注</span><span class="sxs-lookup"><span data-stu-id="ba619-115">Remarks</span></span>  
 <span data-ttu-id="ba619-116">此方法是仅用于提供信息。</span><span class="sxs-lookup"><span data-stu-id="ba619-116">This method is purely informational.</span></span> <span data-ttu-id="ba619-117">接口不会妨碍您启动或附加到进程，而不考虑值返回`CanLaunchOrAttach`。</span><span class="sxs-lookup"><span data-stu-id="ba619-117">The interface will not stop you from launching or attaching to a process, regardless of the value returned by `CanLaunchOrAttach`.</span></span>  
  
 <span data-ttu-id="ba619-118">如果你打算使用 Win32 调试启用了启动或启用 Win32 调试附加，则传递`true`为`win32DebuggingEnabled`。</span><span class="sxs-lookup"><span data-stu-id="ba619-118">If you plan to launch with Win32 debugging enabled or attach with Win32 debugging enabled, pass `true` for `win32DebuggingEnabled`.</span></span> <span data-ttu-id="ba619-119">通过返回的 HRESULT`CanLaunchOrAttach`如果使用此选项可能不同。</span><span class="sxs-lookup"><span data-stu-id="ba619-119">The HRESULT returned by `CanLaunchOrAttach` might differ if you use this option.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba619-120">要求</span><span class="sxs-lookup"><span data-stu-id="ba619-120">Requirements</span></span>  
 <span data-ttu-id="ba619-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ba619-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba619-122">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba619-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba619-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba619-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba619-124">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba619-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba619-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba619-125">See also</span></span>

- [<span data-ttu-id="ba619-126">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="ba619-126">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
