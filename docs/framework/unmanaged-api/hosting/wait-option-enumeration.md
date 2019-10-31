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
ms.openlocfilehash: 9ecfb551b55551e5f6cc7e7e9ffb55e5a96259ee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141513"
---
# <a name="wait_option-enumeration"></a><span data-ttu-id="56e6b-102">WAIT_OPTION 枚举</span><span class="sxs-lookup"><span data-stu-id="56e6b-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="56e6b-103">包含一些值，这些值指示当公共语言运行时（CLR）块请求的操作时宿主应执行的操作。</span><span class="sxs-lookup"><span data-stu-id="56e6b-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56e6b-104">语法</span><span class="sxs-lookup"><span data-stu-id="56e6b-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="56e6b-105">Members</span><span class="sxs-lookup"><span data-stu-id="56e6b-105">Members</span></span>  
  
|<span data-ttu-id="56e6b-106">成员</span><span class="sxs-lookup"><span data-stu-id="56e6b-106">Member</span></span>|<span data-ttu-id="56e6b-107">描述</span><span class="sxs-lookup"><span data-stu-id="56e6b-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="56e6b-108">如果 CLR 调用[IHostTask：： Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)方法，则通知宿主应唤醒任务。</span><span class="sxs-lookup"><span data-stu-id="56e6b-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="56e6b-109">当线程被阻止时，通知宿主必须在当前 OS 线程上抽取消息。</span><span class="sxs-lookup"><span data-stu-id="56e6b-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="56e6b-110">运行时仅在 <xref:System.Threading.ApartmentState.STA> 线程上指定此值。</span><span class="sxs-lookup"><span data-stu-id="56e6b-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="56e6b-111">向宿主通知指定的同步请求无法被宿主中断。</span><span class="sxs-lookup"><span data-stu-id="56e6b-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="56e6b-112">也就是说，主机不能返回 `HOST_E_DEADLOCK`。</span><span class="sxs-lookup"><span data-stu-id="56e6b-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56e6b-113">备注</span><span class="sxs-lookup"><span data-stu-id="56e6b-113">Remarks</span></span>  
 <span data-ttu-id="56e6b-114">[IHostTaskManager：： Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)和[IHostTaskManager：： SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)方法都采用此类型的参数。</span><span class="sxs-lookup"><span data-stu-id="56e6b-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56e6b-115">要求</span><span class="sxs-lookup"><span data-stu-id="56e6b-115">Requirements</span></span>  
 <span data-ttu-id="56e6b-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="56e6b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56e6b-117">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="56e6b-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="56e6b-118">**库：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="56e6b-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="56e6b-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56e6b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56e6b-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="56e6b-120">See also</span></span>

- [<span data-ttu-id="56e6b-121">承载枚举</span><span class="sxs-lookup"><span data-stu-id="56e6b-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
