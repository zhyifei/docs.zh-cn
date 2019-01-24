---
title: MDAInfo 结构
ms.date: 03/30/2017
api_name:
- MDAInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MDAInfo
helpviewer_keywords:
- MDAInfo structure [.NET Framework hosting]
ms.assetid: fb8c14f7-d461-43d1-8b47-adb6723b9b93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d48c3d701b0369ab00150625c26d94f4111b2d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607207"
---
# <a name="mdainfo-structure"></a><span data-ttu-id="96408-102">MDAInfo 结构</span><span class="sxs-lookup"><span data-stu-id="96408-102">MDAInfo Structure</span></span>
<span data-ttu-id="96408-103">详细介绍`Event_MDAFired`触发托管调试助手 (MDA) 创建的事件。</span><span class="sxs-lookup"><span data-stu-id="96408-103">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96408-104">语法</span><span class="sxs-lookup"><span data-stu-id="96408-104">Syntax</span></span>  
  
```  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="96408-105">成员</span><span class="sxs-lookup"><span data-stu-id="96408-105">Members</span></span>  
  
|<span data-ttu-id="96408-106">成员</span><span class="sxs-lookup"><span data-stu-id="96408-106">Member</span></span>|<span data-ttu-id="96408-107">描述</span><span class="sxs-lookup"><span data-stu-id="96408-107">Description</span></span>|  
|------------|-----------------|  
|`lpMDACaption`|<span data-ttu-id="96408-108">当前的 MDA 的标题。</span><span class="sxs-lookup"><span data-stu-id="96408-108">The title of the current MDA.</span></span> <span data-ttu-id="96408-109">标题描述触发失败的`Event_MDAFired`事件。</span><span class="sxs-lookup"><span data-stu-id="96408-109">The title describes the kind of failure that triggered the `Event_MDAFired` event.</span></span>|  
|`lpMDAMessage`|<span data-ttu-id="96408-110">提供当前 MDA 的输出消息。</span><span class="sxs-lookup"><span data-stu-id="96408-110">The output message provided by the current MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96408-111">备注</span><span class="sxs-lookup"><span data-stu-id="96408-111">Remarks</span></span>  
 <span data-ttu-id="96408-112">托管调试助手 (Mda) 是在运行时执行引擎中的调试辅助程序可与公共语言运行时 (CLR) 来执行任务，例如标识无效的条件结合或转储有关状态的其他信息引擎。</span><span class="sxs-lookup"><span data-stu-id="96408-112">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to perform tasks such as identifying invalid conditions in the runtime execution engine or dumping additional information about the state of the engine.</span></span> <span data-ttu-id="96408-113">Mda 会生成有关则很难捕获的事件的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="96408-113">MDAs generate XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="96408-114">它们将用于调试托管和非托管代码之间的转换非常有用。</span><span class="sxs-lookup"><span data-stu-id="96408-114">They are especially useful for debugging transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="96408-115">在运行时激发的事件触发创建 MDA 时采用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="96408-115">The runtime takes the following steps when an event that triggers the creation of an MDA is fired:</span></span>  
  
-   <span data-ttu-id="96408-116">如果主机尚未注册[IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)实例通过调用[iclroneventmanager:: Registeractiononevent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)接收通知`Event_MDAFired`事件，在运行时将继续进行其默认情况下，非托管的行为。</span><span class="sxs-lookup"><span data-stu-id="96408-116">If the host has not registered an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) instance by calling [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) to be notified of an `Event_MDAFired` event, the runtime proceeds with its default, non-hosted behavior.</span></span>  
  
-   <span data-ttu-id="96408-117">如果主机已注册此事件的处理程序，运行时检查是否将调试程序附加到进程。</span><span class="sxs-lookup"><span data-stu-id="96408-117">If the host has registered a handler for this event, the runtime checks to see whether a debugger is attached to the process.</span></span> <span data-ttu-id="96408-118">如果是，运行时将进入调试器。</span><span class="sxs-lookup"><span data-stu-id="96408-118">If it is, the runtime breaks into the debugger.</span></span> <span data-ttu-id="96408-119">当调试器会继续时，它调用到主机。</span><span class="sxs-lookup"><span data-stu-id="96408-119">When the debugger continues, it calls into the host.</span></span> <span data-ttu-id="96408-120">如果没有调试器已附加，则运行时调用`IActionOnCLREvent::OnEvent`，并将传递指向的指针`MDAInfo`实例作为`data`参数。</span><span class="sxs-lookup"><span data-stu-id="96408-120">If no debugger is attached, the runtime calls `IActionOnCLREvent::OnEvent` and passes a pointer to an `MDAInfo` instance as the `data` parameter.</span></span>  
  
 <span data-ttu-id="96408-121">主机可以激活 Mda，MDA 激活时收到通知。</span><span class="sxs-lookup"><span data-stu-id="96408-121">The host can choose to activate MDAs and to be notified when an MDA is activated.</span></span> <span data-ttu-id="96408-122">这会在主机重写默认行为并中止引发事件，以防止损坏进程状态的托管的线程的机会。</span><span class="sxs-lookup"><span data-stu-id="96408-122">This gives the host an opportunity to override default behavior and to abort the managed thread that raised the event, to prevent it from corrupting the process state.</span></span> <span data-ttu-id="96408-123">有关使用 Mda 的详细信息，请参阅[使用托管调试助手诊断错误](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)。</span><span class="sxs-lookup"><span data-stu-id="96408-123">For more information about using MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96408-124">要求</span><span class="sxs-lookup"><span data-stu-id="96408-124">Requirements</span></span>  
 <span data-ttu-id="96408-125">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="96408-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96408-126">**标头：** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="96408-126">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="96408-127">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="96408-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96408-128">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96408-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96408-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="96408-129">See also</span></span>
- [<span data-ttu-id="96408-130">承载结构</span><span class="sxs-lookup"><span data-stu-id="96408-130">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="96408-131">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="96408-131">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
