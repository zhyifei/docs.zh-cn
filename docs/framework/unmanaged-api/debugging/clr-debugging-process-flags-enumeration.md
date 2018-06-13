---
title: CLR_DEBUGGING_PROCESS_FLAGS 枚举
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_PROCESS_FLAGS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords:
- CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dff6b245c80050a5e85561b8bba6aa9ba8199ba8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407061"
---
# <a name="clrdebuggingprocessflags-enumeration"></a><span data-ttu-id="f79e4-102">CLR_DEBUGGING_PROCESS_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="f79e4-102">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>
<span data-ttu-id="f79e4-103">提供使用的值[iclrdebugging:: Openvirtualprocess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="f79e4-103">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f79e4-104">语法</span><span class="sxs-lookup"><span data-stu-id="f79e4-104">Syntax</span></span>  
  
```  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="f79e4-105">成员</span><span class="sxs-lookup"><span data-stu-id="f79e4-105">Members</span></span>  
  
|<span data-ttu-id="f79e4-106">成员</span><span class="sxs-lookup"><span data-stu-id="f79e4-106">Member</span></span>|<span data-ttu-id="f79e4-107">描述</span><span class="sxs-lookup"><span data-stu-id="f79e4-107">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="f79e4-108">此运行时有一个非 catch 向上托管的调试器事件发送。</span><span class="sxs-lookup"><span data-stu-id="f79e4-108">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="f79e4-109">请参阅追赶和非 catch 向上事件之间的区别备注部分。</span><span class="sxs-lookup"><span data-stu-id="f79e4-109">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="f79e4-110">处于挂起状态的托管的事件是<xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType>请求。</span><span class="sxs-lookup"><span data-stu-id="f79e4-110">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f79e4-111">备注</span><span class="sxs-lookup"><span data-stu-id="f79e4-111">Remarks</span></span>  
 <span data-ttu-id="f79e4-112">弥补性事件包括进程、 应用程序域、 程序集、 模块和将调试器移到当前状态后已附加到进程的线程创建通知。</span><span class="sxs-lookup"><span data-stu-id="f79e4-112">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="f79e4-113">非 catch 向上事件，这由`CLR_DEBUGGING_MANAGED_EVENT_PENDING`标记，包括所有其他调试器事件，如异常以及托管调试助手 (MDA) 通知。</span><span class="sxs-lookup"><span data-stu-id="f79e4-113">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="f79e4-114">`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`标志允许运行时终止的异常和附加托管的调试器可以取消的请求有差异。</span><span class="sxs-lookup"><span data-stu-id="f79e4-114">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f79e4-115">要求</span><span class="sxs-lookup"><span data-stu-id="f79e4-115">Requirements</span></span>  
 <span data-ttu-id="f79e4-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f79e4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f79e4-117">**标头：** Metahost.idl、 Metahost.h</span><span class="sxs-lookup"><span data-stu-id="f79e4-117">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="f79e4-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f79e4-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f79e4-119">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f79e4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f79e4-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="f79e4-120">See Also</span></span>  
 [<span data-ttu-id="f79e4-121">调试枚举</span><span class="sxs-lookup"><span data-stu-id="f79e4-121">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="f79e4-122">调试</span><span class="sxs-lookup"><span data-stu-id="f79e4-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
