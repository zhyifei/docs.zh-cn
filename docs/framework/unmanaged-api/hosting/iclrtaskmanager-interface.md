---
title: ICLRTaskManager 接口
ms.date: 03/30/2017
api_name:
- ICLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager
helpviewer_keywords:
- ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 19ef7cb78791496de76e5741f8254ee88563c776
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763368"
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="e1659-102">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="e1659-102">ICLRTaskManager Interface</span></span>
<span data-ttu-id="e1659-103">提供了使宿主可以显式请求的公共语言运行时 (CLR) 的方法创建新的任务、 获取当前正在执行的任务，并设置地理语言和区域性的任务。</span><span class="sxs-lookup"><span data-stu-id="e1659-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1659-104">方法</span><span class="sxs-lookup"><span data-stu-id="e1659-104">Methods</span></span>  
  
|<span data-ttu-id="e1659-105">方法</span><span class="sxs-lookup"><span data-stu-id="e1659-105">Method</span></span>|<span data-ttu-id="e1659-106">描述</span><span class="sxs-lookup"><span data-stu-id="e1659-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1659-107">CreateTask 方法</span><span class="sxs-lookup"><span data-stu-id="e1659-107">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|<span data-ttu-id="e1659-108">显式请求 CLR 创建的新[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="e1659-108">Requests explicitly that the CLR create a new [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="e1659-109">GetCurrentTask 方法</span><span class="sxs-lookup"><span data-stu-id="e1659-109">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="e1659-110">获取`ICLRTask`实例，它表示当前正在执行的任务。</span><span class="sxs-lookup"><span data-stu-id="e1659-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="e1659-111">GetCurrentTaskType 方法</span><span class="sxs-lookup"><span data-stu-id="e1659-111">GetCurrentTaskType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="e1659-112">获取当前正在执行的任务的类型。</span><span class="sxs-lookup"><span data-stu-id="e1659-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="e1659-113">SetLocale 方法</span><span class="sxs-lookup"><span data-stu-id="e1659-113">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="e1659-114">通知 CLR 主机已修改当前正在执行的任务的区域设置标识符。</span><span class="sxs-lookup"><span data-stu-id="e1659-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="e1659-115">SetUILocale 方法</span><span class="sxs-lookup"><span data-stu-id="e1659-115">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="e1659-116">通知公共语言运行时主机已修改当前正在执行的任务的用户界面区域设置标识符。</span><span class="sxs-lookup"><span data-stu-id="e1659-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1659-117">备注</span><span class="sxs-lookup"><span data-stu-id="e1659-117">Remarks</span></span>  
 <span data-ttu-id="e1659-118">在托管环境中运行每个任务宿主端有两个表示形式 (的实例[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) 和 CLR 侧 (实例[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md))。</span><span class="sxs-lookup"><span data-stu-id="e1659-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span></span> <span data-ttu-id="e1659-119">在主机或 CLR 可以启动创建任务，但必须与相应的 CLR 端表示形式以确保在主机和关于此任务 CLR 之间的成功通信相关联的主机端表示形式。</span><span class="sxs-lookup"><span data-stu-id="e1659-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="e1659-120">必须创建和实例化操作系统线程上执行托管的代码之前的两个对象。</span><span class="sxs-lookup"><span data-stu-id="e1659-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1659-121">要求</span><span class="sxs-lookup"><span data-stu-id="e1659-121">Requirements</span></span>  
 <span data-ttu-id="e1659-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e1659-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1659-123">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e1659-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1659-124">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e1659-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1659-125">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1659-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1659-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1659-126">See also</span></span>

- [<span data-ttu-id="e1659-127">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="e1659-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e1659-128">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="e1659-128">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e1659-129">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="e1659-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="e1659-130">承载接口</span><span class="sxs-lookup"><span data-stu-id="e1659-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
