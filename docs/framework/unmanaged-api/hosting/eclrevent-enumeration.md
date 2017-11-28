---
title: "EClrEvent 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EClrEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: EClrEvent
helpviewer_keywords: EClrEvent enumeration [.NET Framework hosting]
ms.assetid: 7c36a7c2-75a2-4971-bc23-abf54c812154
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0585cea00865f4798c57ef5276076c2b0a5ff284
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="eclrevent-enumeration"></a><span data-ttu-id="e25a8-102">EClrEvent 枚举</span><span class="sxs-lookup"><span data-stu-id="e25a8-102">EClrEvent Enumeration</span></span>
<span data-ttu-id="e25a8-103">描述主机可为其注册回调的公共语言运行时 (CLR) 事件。</span><span class="sxs-lookup"><span data-stu-id="e25a8-103">Describes the common language runtime (CLR) events for which the host can register callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e25a8-104">语法</span><span class="sxs-lookup"><span data-stu-id="e25a8-104">Syntax</span></span>  
  
```  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a><span data-ttu-id="e25a8-105">成员</span><span class="sxs-lookup"><span data-stu-id="e25a8-105">Members</span></span>  
  
|<span data-ttu-id="e25a8-106">成员</span><span class="sxs-lookup"><span data-stu-id="e25a8-106">Member</span></span>|<span data-ttu-id="e25a8-107">描述</span><span class="sxs-lookup"><span data-stu-id="e25a8-107">Description</span></span>|  
|------------|-----------------|  
|`Event_ClrDisabled`|<span data-ttu-id="e25a8-108">指定错误的 CLR。</span><span class="sxs-lookup"><span data-stu-id="e25a8-108">Specifies a fatal CLR error.</span></span>|  
|`Event_DomainUnload`|<span data-ttu-id="e25a8-109">指定的特定卸载<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="e25a8-109">Specifies the unloading of a particular <xref:System.AppDomain>.</span></span>|  
|`Event_MDAFired`|<span data-ttu-id="e25a8-110">指定已生成托管调试助手 (MDA) 消息。</span><span class="sxs-lookup"><span data-stu-id="e25a8-110">Specifies that a Managed Debugging Assistant (MDA) message has been generated.</span></span>|  
|`Event_StackOverflow`|<span data-ttu-id="e25a8-111">指定发生堆栈溢出错误。</span><span class="sxs-lookup"><span data-stu-id="e25a8-111">Specifies that a stack overflow error has occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e25a8-112">备注</span><span class="sxs-lookup"><span data-stu-id="e25a8-112">Remarks</span></span>  
 <span data-ttu-id="e25a8-113">宿主可以注册任何通过所述的事件类型的回调`EClrEvent`通过调用的方法[ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="e25a8-113">The host can register callbacks for any of the event types described by `EClrEvent` by calling methods of the [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) interface.</span></span> <span data-ttu-id="e25a8-114">主机通过调用此接口获取指向[iclrcontrol:: Getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e25a8-114">The host gets a pointer to this interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
 <span data-ttu-id="e25a8-115">`Event_CLRDisabled`和`Event_DomainUnload`不止一次和从不同的线程，以卸载或禁用 CLR 发出信号，则可以引发事件。</span><span class="sxs-lookup"><span data-stu-id="e25a8-115">The `Event_CLRDisabled` and `Event_DomainUnload` events can be raised more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
 <span data-ttu-id="e25a8-116">`Event_MDAFired`事件引发的创建[MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)实例，其中包含 MDA 消息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e25a8-116">The `Event_MDAFired` event raises the creation of an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the details of the MDA message.</span></span> <span data-ttu-id="e25a8-117">有关 Mda 的详细信息，请参阅[使用托管调试助手诊断错误](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)。</span><span class="sxs-lookup"><span data-stu-id="e25a8-117">For more information about MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e25a8-118">要求</span><span class="sxs-lookup"><span data-stu-id="e25a8-118">Requirements</span></span>  
 <span data-ttu-id="e25a8-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e25a8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e25a8-120">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e25a8-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e25a8-121">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e25a8-121">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e25a8-122">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e25a8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e25a8-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e25a8-123">See Also</span></span>  
 [<span data-ttu-id="e25a8-124">IActionOnCLREvent 接口</span><span class="sxs-lookup"><span data-stu-id="e25a8-124">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="e25a8-125">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="e25a8-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="e25a8-126">承载枚举</span><span class="sxs-lookup"><span data-stu-id="e25a8-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
