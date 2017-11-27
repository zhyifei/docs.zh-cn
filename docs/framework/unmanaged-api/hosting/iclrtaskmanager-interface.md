---
title: "ICLRTaskManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTaskManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTaskManager
helpviewer_keywords: ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3144338ddce262aaa6772f588a4f1a652cc57e01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskmanager-interface"></a><span data-ttu-id="a59f7-102">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="a59f7-102">ICLRTaskManager Interface</span></span>
<span data-ttu-id="a59f7-103">提供使该主机可显式请求公共语言运行时 (CLR) 的方法创建新任务、 获取当前正在执行的任务，并设置地理语言和任务的区域性。</span><span class="sxs-lookup"><span data-stu-id="a59f7-103">Provides methods that allow the host to request explicitly that the common language runtime (CLR) create a new task, get the currently executing task, and set the geographic language and culture for the task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a59f7-104">方法</span><span class="sxs-lookup"><span data-stu-id="a59f7-104">Methods</span></span>  
  
|<span data-ttu-id="a59f7-105">方法</span><span class="sxs-lookup"><span data-stu-id="a59f7-105">Method</span></span>|<span data-ttu-id="a59f7-106">描述</span><span class="sxs-lookup"><span data-stu-id="a59f7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a59f7-107">CreateTask 方法</span><span class="sxs-lookup"><span data-stu-id="a59f7-107">CreateTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|<span data-ttu-id="a59f7-108">显式请求 CLR 创建一个新[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="a59f7-108">Requests explicitly that the CLR create a new [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>|  
|[<span data-ttu-id="a59f7-109">GetCurrentTask 方法</span><span class="sxs-lookup"><span data-stu-id="a59f7-109">GetCurrentTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|<span data-ttu-id="a59f7-110">获取`ICLRTask`实例，表示当前正在执行的任务。</span><span class="sxs-lookup"><span data-stu-id="a59f7-110">Gets the `ICLRTask` instance that represents the task that is currently executing.</span></span>|  
|[<span data-ttu-id="a59f7-111">GetCurrentTaskType 方法</span><span class="sxs-lookup"><span data-stu-id="a59f7-111">GetCurrentTaskType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|<span data-ttu-id="a59f7-112">获取当前正在执行的任务的类型。</span><span class="sxs-lookup"><span data-stu-id="a59f7-112">Gets the type of the task that is currently executing.</span></span>|  
|[<span data-ttu-id="a59f7-113">SetLocale 方法</span><span class="sxs-lookup"><span data-stu-id="a59f7-113">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|<span data-ttu-id="a59f7-114">通知宿主已修改当前正在执行的任务的区域设置标识符的 CLR。</span><span class="sxs-lookup"><span data-stu-id="a59f7-114">Notifies the CLR that the host has modified the locale identifier on the currently executing task.</span></span>|  
|[<span data-ttu-id="a59f7-115">SetUILocale 方法</span><span class="sxs-lookup"><span data-stu-id="a59f7-115">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|<span data-ttu-id="a59f7-116">通知公共语言运行时主机已修改当前正在执行的任务的用户界面区域设置标识符。</span><span class="sxs-lookup"><span data-stu-id="a59f7-116">Notifies the common language runtime that the host has modified the user interface locale identifier on the currently executing task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a59f7-117">备注</span><span class="sxs-lookup"><span data-stu-id="a59f7-117">Remarks</span></span>  
 <span data-ttu-id="a59f7-118">在托管环境中运行每个任务在主机端有这两个表示形式 (实例[IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) 和 CLR 一端 (实例[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md))。</span><span class="sxs-lookup"><span data-stu-id="a59f7-118">Each task that is running in a hosted environment has representations both on the host side (an instance of [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) and on the CLR side (an instance of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)).</span></span> <span data-ttu-id="a59f7-119">在主机或 CLR 可以启动创建任务，但必须与相应的 CLR 端表示形式，以确保主机和关于此任务 CLR 之间的成功通信相关联的主机端表示。</span><span class="sxs-lookup"><span data-stu-id="a59f7-119">Either the host or the CLR can initiate the creation of a task, but the host-side representation must be associated with a corresponding CLR-side representation to ensure successful communication between the host and the CLR regarding the task.</span></span> <span data-ttu-id="a59f7-120">必须创建和实例化之前可以在操作系统线程上执行托管的代码的两个对象。</span><span class="sxs-lookup"><span data-stu-id="a59f7-120">The two objects must be created and instantiated before managed code can execute on an operating system thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a59f7-121">要求</span><span class="sxs-lookup"><span data-stu-id="a59f7-121">Requirements</span></span>  
 <span data-ttu-id="a59f7-122">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a59f7-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a59f7-123">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a59f7-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a59f7-124">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a59f7-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a59f7-125">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a59f7-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a59f7-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a59f7-126">See Also</span></span>  
 [<span data-ttu-id="a59f7-127">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="a59f7-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="a59f7-128">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="a59f7-128">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="a59f7-129">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="a59f7-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="a59f7-130">承载接口</span><span class="sxs-lookup"><span data-stu-id="a59f7-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
