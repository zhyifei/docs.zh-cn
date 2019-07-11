---
title: WAIT_OPTION 枚举
ms.date: 03/30/2017
api_name:
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eda866c1a1f1f69f0d042ccfde3dfad293df9b37
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776507"
---
# <a name="waitoption-enumeration"></a><span data-ttu-id="0442b-102">WAIT_OPTION 枚举</span><span class="sxs-lookup"><span data-stu-id="0442b-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="0442b-103">包含指示请求的公共语言运行时 (CLR) 块操作时应采取的操作主机的值。</span><span class="sxs-lookup"><span data-stu-id="0442b-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0442b-104">语法</span><span class="sxs-lookup"><span data-stu-id="0442b-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="0442b-105">成员</span><span class="sxs-lookup"><span data-stu-id="0442b-105">Members</span></span>  
  
|<span data-ttu-id="0442b-106">成员</span><span class="sxs-lookup"><span data-stu-id="0442b-106">Member</span></span>|<span data-ttu-id="0442b-107">描述</span><span class="sxs-lookup"><span data-stu-id="0442b-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="0442b-108">通知主机如果 CLR 调用该任务应被唤醒[ihosttask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="0442b-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="0442b-109">通知主机，如果线程被阻止，它必须发送当前 OS 线程上的信息。</span><span class="sxs-lookup"><span data-stu-id="0442b-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="0442b-110">在运行时指定此值仅在上<xref:System.Threading.ApartmentState.STA>线程。</span><span class="sxs-lookup"><span data-stu-id="0442b-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="0442b-111">通知宿主不能中断指定的同步请求主机。</span><span class="sxs-lookup"><span data-stu-id="0442b-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="0442b-112">也就是说，不能返回主机`HOST_E_DEADLOCK`。</span><span class="sxs-lookup"><span data-stu-id="0442b-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0442b-113">备注</span><span class="sxs-lookup"><span data-stu-id="0442b-113">Remarks</span></span>  
 <span data-ttu-id="0442b-114">[Ihosttaskmanager:: Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)并[ihosttaskmanager:: Switchtotask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)方法都采用这种类型的参数。</span><span class="sxs-lookup"><span data-stu-id="0442b-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0442b-115">要求</span><span class="sxs-lookup"><span data-stu-id="0442b-115">Requirements</span></span>  
 <span data-ttu-id="0442b-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0442b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0442b-117">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0442b-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0442b-118">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0442b-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0442b-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0442b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0442b-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="0442b-120">See also</span></span>

- [<span data-ttu-id="0442b-121">承载枚举</span><span class="sxs-lookup"><span data-stu-id="0442b-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
