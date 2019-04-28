---
title: EClrEvent 枚举
ms.date: 03/30/2017
api_name:
- EClrEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrEvent
helpviewer_keywords:
- EClrEvent enumeration [.NET Framework hosting]
ms.assetid: 7c36a7c2-75a2-4971-bc23-abf54c812154
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13d564be68d6b49a1616be97710312f33f828d48
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628654"
---
# <a name="eclrevent-enumeration"></a><span data-ttu-id="7336a-102">EClrEvent 枚举</span><span class="sxs-lookup"><span data-stu-id="7336a-102">EClrEvent Enumeration</span></span>
<span data-ttu-id="7336a-103">描述主机可为其注册回调的公共语言运行时 (CLR) 事件。</span><span class="sxs-lookup"><span data-stu-id="7336a-103">Describes the common language runtime (CLR) events for which the host can register callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7336a-104">语法</span><span class="sxs-lookup"><span data-stu-id="7336a-104">Syntax</span></span>  
  
```  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a><span data-ttu-id="7336a-105">成员</span><span class="sxs-lookup"><span data-stu-id="7336a-105">Members</span></span>  
  
|<span data-ttu-id="7336a-106">成员</span><span class="sxs-lookup"><span data-stu-id="7336a-106">Member</span></span>|<span data-ttu-id="7336a-107">描述</span><span class="sxs-lookup"><span data-stu-id="7336a-107">Description</span></span>|  
|------------|-----------------|  
|`Event_ClrDisabled`|<span data-ttu-id="7336a-108">指定错误的 CLR。</span><span class="sxs-lookup"><span data-stu-id="7336a-108">Specifies a fatal CLR error.</span></span>|  
|`Event_DomainUnload`|<span data-ttu-id="7336a-109">指定卸载特定<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="7336a-109">Specifies the unloading of a particular <xref:System.AppDomain>.</span></span>|  
|`Event_MDAFired`|<span data-ttu-id="7336a-110">指定已生成的托管调试助手 (MDA) 消息。</span><span class="sxs-lookup"><span data-stu-id="7336a-110">Specifies that a Managed Debugging Assistant (MDA) message has been generated.</span></span>|  
|`Event_StackOverflow`|<span data-ttu-id="7336a-111">指定已发生堆栈溢出错误。</span><span class="sxs-lookup"><span data-stu-id="7336a-111">Specifies that a stack overflow error has occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7336a-112">备注</span><span class="sxs-lookup"><span data-stu-id="7336a-112">Remarks</span></span>  
 <span data-ttu-id="7336a-113">宿主可以注册任何所描述的事件类型的回调`EClrEvent`通过调用的方法[ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="7336a-113">The host can register callbacks for any of the event types described by `EClrEvent` by calling methods of the [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) interface.</span></span> <span data-ttu-id="7336a-114">主机通过调用此接口获取指向[iclrcontrol:: Getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="7336a-114">The host gets a pointer to this interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
 <span data-ttu-id="7336a-115">`Event_CLRDisabled`和`Event_DomainUnload`不止一次和来自不同线程发出信号卸载或禁用 CLR 可以引发事件。</span><span class="sxs-lookup"><span data-stu-id="7336a-115">The `Event_CLRDisabled` and `Event_DomainUnload` events can be raised more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
 <span data-ttu-id="7336a-116">`Event_MDAFired`事件引发的创建[MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)实例，它包含 MDA 消息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7336a-116">The `Event_MDAFired` event raises the creation of an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the details of the MDA message.</span></span> <span data-ttu-id="7336a-117">Mda 的详细信息，请参阅[使用托管调试助手诊断错误](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)。</span><span class="sxs-lookup"><span data-stu-id="7336a-117">For more information about MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7336a-118">要求</span><span class="sxs-lookup"><span data-stu-id="7336a-118">Requirements</span></span>  
 <span data-ttu-id="7336a-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7336a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7336a-120">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7336a-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7336a-121">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7336a-121">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7336a-122">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7336a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7336a-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="7336a-123">See also</span></span>

- [<span data-ttu-id="7336a-124">IActionOnCLREvent 接口</span><span class="sxs-lookup"><span data-stu-id="7336a-124">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="7336a-125">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="7336a-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="7336a-126">承载枚举</span><span class="sxs-lookup"><span data-stu-id="7336a-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
