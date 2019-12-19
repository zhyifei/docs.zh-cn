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
ms.openlocfilehash: 9a2f513d40d722f1b0aad823ac7c0d93bda5615f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123261"
---
# <a name="mdainfo-structure"></a><span data-ttu-id="2fbb5-102">MDAInfo 结构</span><span class="sxs-lookup"><span data-stu-id="2fbb5-102">MDAInfo Structure</span></span>
<span data-ttu-id="2fbb5-103">提供有关 `Event_MDAFired` 事件的详细信息，该事件可触发托管调试助手（MDA）的创建。</span><span class="sxs-lookup"><span data-stu-id="2fbb5-103">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fbb5-104">语法</span><span class="sxs-lookup"><span data-stu-id="2fbb5-104">Syntax</span></span>  
  
```cpp  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="2fbb5-105">Members</span><span class="sxs-lookup"><span data-stu-id="2fbb5-105">Members</span></span>  
  
|<span data-ttu-id="2fbb5-106">成员</span><span class="sxs-lookup"><span data-stu-id="2fbb5-106">Member</span></span>|<span data-ttu-id="2fbb5-107">描述</span><span class="sxs-lookup"><span data-stu-id="2fbb5-107">Description</span></span>|  
|------------|-----------------|  
|`lpMDACaption`|<span data-ttu-id="2fbb5-108">当前 MDA 的标题。</span><span class="sxs-lookup"><span data-stu-id="2fbb5-108">The title of the current MDA.</span></span> <span data-ttu-id="2fbb5-109">标题描述触发 `Event_MDAFired` 事件的故障类型。</span><span class="sxs-lookup"><span data-stu-id="2fbb5-109">The title describes the kind of failure that triggered the `Event_MDAFired` event.</span></span>|  
|`lpMDAMessage`|<span data-ttu-id="2fbb5-110">当前 MDA 提供的输出消息。</span><span class="sxs-lookup"><span data-stu-id="2fbb5-110">The output message provided by the current MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fbb5-111">备注</span><span class="sxs-lookup"><span data-stu-id="2fbb5-111">Remarks</span></span>  
 <span data-ttu-id="2fbb5-112">托管调试助手（Mda）是调试辅助工具，可与公共语言运行时（CLR）结合使用来执行任务，例如，在运行时执行引擎中标识无效条件或转储有关的状态的其他信息搜索引擎优化.</span><span class="sxs-lookup"><span data-stu-id="2fbb5-112">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to perform tasks such as identifying invalid conditions in the runtime execution engine or dumping additional information about the state of the engine.</span></span> <span data-ttu-id="2fbb5-113">Mda 生成的 XML 消息与其他难以捕获的事件有关。</span><span class="sxs-lookup"><span data-stu-id="2fbb5-113">MDAs generate XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="2fbb5-114">它们对于调试托管代码和非托管代码之间的转换特别有用。</span><span class="sxs-lookup"><span data-stu-id="2fbb5-114">They are especially useful for debugging transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="2fbb5-115">触发创建 MDA 的事件时，运行时将执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="2fbb5-115">The runtime takes the following steps when an event that triggers the creation of an MDA is fired:</span></span>  
  
- <span data-ttu-id="2fbb5-116">如果主机尚未通过调用 [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) 来注册 [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) `Event_MDAFired` 事件的通知，则运行时将继续默认的非托管行为。</span><span class="sxs-lookup"><span data-stu-id="2fbb5-116">If the host has not registered an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) instance by calling [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) to be notified of an `Event_MDAFired` event, the runtime proceeds with its default, non-hosted behavior.</span></span>  
  
- <span data-ttu-id="2fbb5-117">如果主机注册了此事件的处理程序，则运行时将进行检查以确定调试器是否已附加到进程。</span><span class="sxs-lookup"><span data-stu-id="2fbb5-117">If the host has registered a handler for this event, the runtime checks to see whether a debugger is attached to the process.</span></span> <span data-ttu-id="2fbb5-118">如果为，则运行时会中断调试器。</span><span class="sxs-lookup"><span data-stu-id="2fbb5-118">If it is, the runtime breaks into the debugger.</span></span> <span data-ttu-id="2fbb5-119">调试器继续时，它会调入宿主。</span><span class="sxs-lookup"><span data-stu-id="2fbb5-119">When the debugger continues, it calls into the host.</span></span> <span data-ttu-id="2fbb5-120">如果未附加任何调试器，则运行时将调用 `IActionOnCLREvent::OnEvent`，并将一个指针作为 `data` 参数传递到 `MDAInfo` 实例。</span><span class="sxs-lookup"><span data-stu-id="2fbb5-120">If no debugger is attached, the runtime calls `IActionOnCLREvent::OnEvent` and passes a pointer to an `MDAInfo` instance as the `data` parameter.</span></span>  
  
 <span data-ttu-id="2fbb5-121">宿主可以选择激活 mda，并在激活 MDA 时获得通知。</span><span class="sxs-lookup"><span data-stu-id="2fbb5-121">The host can choose to activate MDAs and to be notified when an MDA is activated.</span></span> <span data-ttu-id="2fbb5-122">这使宿主有机会覆盖默认行为，并中止引发事件的托管线程，以防止其损坏进程状态。</span><span class="sxs-lookup"><span data-stu-id="2fbb5-122">This gives the host an opportunity to override default behavior and to abort the managed thread that raised the event, to prevent it from corrupting the process state.</span></span> <span data-ttu-id="2fbb5-123">有关使用 Mda 的详细信息，请参阅[使用托管调试助手诊断错误](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)。</span><span class="sxs-lookup"><span data-stu-id="2fbb5-123">For more information about using MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fbb5-124">要求</span><span class="sxs-lookup"><span data-stu-id="2fbb5-124">Requirements</span></span>  
 <span data-ttu-id="2fbb5-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2fbb5-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fbb5-126">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2fbb5-126">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="2fbb5-127">**库：** 作为资源包括在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="2fbb5-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2fbb5-128">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fbb5-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fbb5-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2fbb5-129">See also</span></span>

- [<span data-ttu-id="2fbb5-130">承载结构</span><span class="sxs-lookup"><span data-stu-id="2fbb5-130">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="2fbb5-131">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="2fbb5-131">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
