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
ms.openlocfilehash: 28b9fb5a25981e5e37a5f1bbb797baeac45e0028
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793565"
---
# <a name="icordebugcanlaunchorattach-method"></a><span data-ttu-id="a027f-102">ICorDebug::CanLaunchOrAttach 方法</span><span class="sxs-lookup"><span data-stu-id="a027f-102">ICorDebug::CanLaunchOrAttach Method</span></span>
<span data-ttu-id="a027f-103">返回一个 HRESULT，它指示是否可以在当前计算机和运行时配置的上下文中启动新进程或附加到指定的现有进程。</span><span class="sxs-lookup"><span data-stu-id="a027f-103">Returns an HRESULT that indicates whether launching a new process or attaching to the specified existing process is possible within the context of the current machine and runtime configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a027f-104">语法</span><span class="sxs-lookup"><span data-stu-id="a027f-104">Syntax</span></span>  
  
```cpp  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a027f-105">参数</span><span class="sxs-lookup"><span data-stu-id="a027f-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="a027f-106">中现有进程的 ID。</span><span class="sxs-lookup"><span data-stu-id="a027f-106">[in] The ID of an existing process.</span></span>  
  
 `win32DebuggingEnabled`  
 <span data-ttu-id="a027f-107">中如果计划在启用 Win32 调试的情况下启动或附加到已启用 Win32 调试，则传入 `true`;否则，传递 `false`。</span><span class="sxs-lookup"><span data-stu-id="a027f-107">[in] Pass in `true` if you plan to launch with Win32 debugging enabled, or to attach with Win32 debugging enabled; otherwise, pass `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a027f-108">返回值</span><span class="sxs-lookup"><span data-stu-id="a027f-108">Return Value</span></span>  
 <span data-ttu-id="a027f-109">在给定有关当前计算机和运行时配置的信息的情况下，如果调试服务确定启动新进程或附加到给定进程，则 S_OK。</span><span class="sxs-lookup"><span data-stu-id="a027f-109">S_OK if the debugging services determine that launching a new process or attaching to the given process is possible, given the information about the current machine and runtime configuration.</span></span> <span data-ttu-id="a027f-110">可能的 HRESULT 值为：</span><span class="sxs-lookup"><span data-stu-id="a027f-110">Possible HRESULT values are:</span></span>  
  
- <span data-ttu-id="a027f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a027f-111">S_OK</span></span>  
  
- <span data-ttu-id="a027f-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span><span class="sxs-lookup"><span data-stu-id="a027f-112">CORDBG_E_DEBUGGING_NOT_POSSIBLE</span></span>  
  
- <span data-ttu-id="a027f-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span><span class="sxs-lookup"><span data-stu-id="a027f-113">CORDBG_E_KERNEL_DEBUGGER_PRESENT</span></span>  
  
- <span data-ttu-id="a027f-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span><span class="sxs-lookup"><span data-stu-id="a027f-114">CORDBG_E_KERNEL_DEBUGGER_ENABLED</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a027f-115">备注</span><span class="sxs-lookup"><span data-stu-id="a027f-115">Remarks</span></span>  
 <span data-ttu-id="a027f-116">此方法纯信息性。</span><span class="sxs-lookup"><span data-stu-id="a027f-116">This method is purely informational.</span></span> <span data-ttu-id="a027f-117">无论 `CanLaunchOrAttach`返回的值是什么，接口都不会阻止你启动或附加到进程。</span><span class="sxs-lookup"><span data-stu-id="a027f-117">The interface will not stop you from launching or attaching to a process, regardless of the value returned by `CanLaunchOrAttach`.</span></span>  
  
 <span data-ttu-id="a027f-118">如果计划在启用 Win32 调试的情况下启动或附加启用了 Win32 调试，请为 `win32DebuggingEnabled`传递 `true`。</span><span class="sxs-lookup"><span data-stu-id="a027f-118">If you plan to launch with Win32 debugging enabled or attach with Win32 debugging enabled, pass `true` for `win32DebuggingEnabled`.</span></span> <span data-ttu-id="a027f-119">如果使用此选项，`CanLaunchOrAttach` 返回的 HRESULT 可能不同。</span><span class="sxs-lookup"><span data-stu-id="a027f-119">The HRESULT returned by `CanLaunchOrAttach` might differ if you use this option.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a027f-120">需求</span><span class="sxs-lookup"><span data-stu-id="a027f-120">Requirements</span></span>  
 <span data-ttu-id="a027f-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a027f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a027f-122">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a027f-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a027f-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a027f-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a027f-124">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a027f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a027f-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a027f-125">See also</span></span>

- [<span data-ttu-id="a027f-126">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="a027f-126">ICorDebug Interface</span></span>](icordebug-interface.md)
