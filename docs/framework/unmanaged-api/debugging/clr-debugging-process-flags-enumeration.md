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
ms.openlocfilehash: 8321e5aeba435ca5f1398a9cb827a93ae821d686
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996354"
---
# <a name="clrdebuggingprocessflags-enumeration"></a><span data-ttu-id="fac15-102">CLR_DEBUGGING_PROCESS_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="fac15-102">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>
<span data-ttu-id="fac15-103">提供了使用的值[iclrdebugging:: Openvirtualprocess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="fac15-103">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fac15-104">语法</span><span class="sxs-lookup"><span data-stu-id="fac15-104">Syntax</span></span>  
  
```  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="fac15-105">成员</span><span class="sxs-lookup"><span data-stu-id="fac15-105">Members</span></span>  
  
|<span data-ttu-id="fac15-106">成员</span><span class="sxs-lookup"><span data-stu-id="fac15-106">Member</span></span>|<span data-ttu-id="fac15-107">描述</span><span class="sxs-lookup"><span data-stu-id="fac15-107">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="fac15-108">此运行时有一个非 catch 向上托管的调试器事件发送。</span><span class="sxs-lookup"><span data-stu-id="fac15-108">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="fac15-109">请参阅追赶和非 catch 向上事件之间的区别备注部分。</span><span class="sxs-lookup"><span data-stu-id="fac15-109">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="fac15-110">处于挂起状态的托管的事件是<xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType>请求。</span><span class="sxs-lookup"><span data-stu-id="fac15-110">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fac15-111">备注</span><span class="sxs-lookup"><span data-stu-id="fac15-111">Remarks</span></span>  
 <span data-ttu-id="fac15-112">追赶事件包括进程、 应用程序域、 程序集、 模块和最多的当前状态使调试器之后它已附加到进程, 的线程创建通知。</span><span class="sxs-lookup"><span data-stu-id="fac15-112">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="fac15-113">所指示的非 catch 向上事件`CLR_DEBUGGING_MANAGED_EVENT_PENDING`标记，包括所有其他调试器事件、 异常等以及托管调试助手 (MDA) 通知。</span><span class="sxs-lookup"><span data-stu-id="fac15-113">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="fac15-114">`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`标志可使运行时终止的异常和附加有托管的调试器，可以取消的请求之间进行区分。</span><span class="sxs-lookup"><span data-stu-id="fac15-114">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fac15-115">要求</span><span class="sxs-lookup"><span data-stu-id="fac15-115">Requirements</span></span>  
 <span data-ttu-id="fac15-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fac15-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fac15-117">**标头：** Metahost.idl Metahost.h</span><span class="sxs-lookup"><span data-stu-id="fac15-117">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="fac15-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fac15-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fac15-119">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fac15-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac15-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="fac15-120">See also</span></span>

- [<span data-ttu-id="fac15-121">调试枚举</span><span class="sxs-lookup"><span data-stu-id="fac15-121">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="fac15-122">调试</span><span class="sxs-lookup"><span data-stu-id="fac15-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
