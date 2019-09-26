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
ms.openlocfilehash: 292f6953fad0d65b368642543af107c73ec42ab5
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274115"
---
# <a name="clr_debugging_process_flags-enumeration"></a><span data-ttu-id="c53a9-102">CLR_DEBUGGING_PROCESS_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="c53a9-102">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>
<span data-ttu-id="c53a9-103">提供[ICLRDebugging：： OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md)方法使用的值。</span><span class="sxs-lookup"><span data-stu-id="c53a9-103">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c53a9-104">语法</span><span class="sxs-lookup"><span data-stu-id="c53a9-104">Syntax</span></span>  
  
```cpp  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="c53a9-105">成员</span><span class="sxs-lookup"><span data-stu-id="c53a9-105">Members</span></span>  
  
|<span data-ttu-id="c53a9-106">成员</span><span class="sxs-lookup"><span data-stu-id="c53a9-106">Member</span></span>|<span data-ttu-id="c53a9-107">描述</span><span class="sxs-lookup"><span data-stu-id="c53a9-107">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="c53a9-108">此运行时有一个要发送的非追赶托管调试器事件。</span><span class="sxs-lookup"><span data-stu-id="c53a9-108">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="c53a9-109">请参阅 "备注" 部分，了解追赶事件与非追赶事件之间的区别。</span><span class="sxs-lookup"><span data-stu-id="c53a9-109">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="c53a9-110">挂起的托管事件是<xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType>请求。</span><span class="sxs-lookup"><span data-stu-id="c53a9-110">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c53a9-111">备注</span><span class="sxs-lookup"><span data-stu-id="c53a9-111">Remarks</span></span>  
 <span data-ttu-id="c53a9-112">追赶事件包括进程、应用程序域、程序集、模块和线程创建通知，这会使调试器在附加到进程后进入当前状态。</span><span class="sxs-lookup"><span data-stu-id="c53a9-112">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="c53a9-113">`CLR_DEBUGGING_MANAGED_EVENT_PENDING`标记指示的非追赶事件包含所有其他调试器事件，例如异常和托管调试助手（MDA）通知。</span><span class="sxs-lookup"><span data-stu-id="c53a9-113">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="c53a9-114">该`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`标志使运行时能够区分终止异常和请求以附加可取消的托管调试器。</span><span class="sxs-lookup"><span data-stu-id="c53a9-114">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c53a9-115">要求</span><span class="sxs-lookup"><span data-stu-id="c53a9-115">Requirements</span></span>  
 <span data-ttu-id="c53a9-116">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c53a9-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c53a9-117">**标头：** Metahost，Metahost</span><span class="sxs-lookup"><span data-stu-id="c53a9-117">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="c53a9-118">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c53a9-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c53a9-119">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c53a9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c53a9-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="c53a9-120">See also</span></span>

- [<span data-ttu-id="c53a9-121">调试枚举</span><span class="sxs-lookup"><span data-stu-id="c53a9-121">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="c53a9-122">调试</span><span class="sxs-lookup"><span data-stu-id="c53a9-122">Debugging</span></span>](index.md)
