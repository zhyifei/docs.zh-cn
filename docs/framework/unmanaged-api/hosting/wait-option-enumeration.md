---
title: "WAIT_OPTION 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: WAIT_OPTION
api_location: mscoree.dll
api_type: COM
f1_keywords: WAIT_OPTION
helpviewer_keywords: WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 143c191592efe8cfea8049f0dd5dc05a5bd4192f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="waitoption-enumeration"></a><span data-ttu-id="d2373-102">WAIT_OPTION 枚举</span><span class="sxs-lookup"><span data-stu-id="d2373-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="d2373-103">包含值，用于指示是否公共语言运行时 (CLR) 块中请求的操作，应采取的措施主机。</span><span class="sxs-lookup"><span data-stu-id="d2373-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2373-104">语法</span><span class="sxs-lookup"><span data-stu-id="d2373-104">Syntax</span></span>  
  
```  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="d2373-105">成员</span><span class="sxs-lookup"><span data-stu-id="d2373-105">Members</span></span>  
  
|<span data-ttu-id="d2373-106">成员</span><span class="sxs-lookup"><span data-stu-id="d2373-106">Member</span></span>|<span data-ttu-id="d2373-107">描述</span><span class="sxs-lookup"><span data-stu-id="d2373-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="d2373-108">通知宿主任务应被唤醒，如果 CLR 调用[ihosttask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d2373-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="d2373-109">通知主机，如果线程被阻止，它必须发送当前的操作系统线程上的消息。</span><span class="sxs-lookup"><span data-stu-id="d2373-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="d2373-110">运行时指定此值仅在上<xref:System.Threading.ApartmentState.STA>线程。</span><span class="sxs-lookup"><span data-stu-id="d2373-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="d2373-111">通知主机宿主无法中断指定的同步请求。</span><span class="sxs-lookup"><span data-stu-id="d2373-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="d2373-112">主机不能返回，即`HOST_E_DEADLOCK`。</span><span class="sxs-lookup"><span data-stu-id="d2373-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2373-113">备注</span><span class="sxs-lookup"><span data-stu-id="d2373-113">Remarks</span></span>  
 <span data-ttu-id="d2373-114">[Ihosttaskmanager:: Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)和[ihosttaskmanager:: Switchtotask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)方法都执行此类型的参数。</span><span class="sxs-lookup"><span data-stu-id="d2373-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2373-115">惠?</span><span class="sxs-lookup"><span data-stu-id="d2373-115">Requirements</span></span>  
 <span data-ttu-id="d2373-116">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d2373-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2373-117">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d2373-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d2373-118">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d2373-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2373-119">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2373-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2373-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2373-120">See Also</span></span>  
 [<span data-ttu-id="d2373-121">承载枚举</span><span class="sxs-lookup"><span data-stu-id="d2373-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
