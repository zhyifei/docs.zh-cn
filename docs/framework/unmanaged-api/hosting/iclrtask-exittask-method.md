---
title: "ICLRTask::ExitTask 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.ExitTask
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::ExitTask
helpviewer_keywords:
- ExitTask method [.NET Framework hosting]
- ICLRTask::ExitTask method [.NET Framework hosting]
ms.assetid: 746c85a6-4b33-4f72-a2e9-379fdf2e96af
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a954987e3a4c63827dafd5145ddb33aae22fa27
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="1d33f-102">ICLRTask::ExitTask 方法</span><span class="sxs-lookup"><span data-stu-id="1d33f-102">ICLRTask::ExitTask Method</span></span>
<span data-ttu-id="1d33f-103">通知当前所表示任务公共语言运行时 (CLR) [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例即将结束，并尝试正常关闭的任务。</span><span class="sxs-lookup"><span data-stu-id="1d33f-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d33f-104">语法</span><span class="sxs-lookup"><span data-stu-id="1d33f-104">Syntax</span></span>  
  
```  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1d33f-105">返回值</span><span class="sxs-lookup"><span data-stu-id="1d33f-105">Return Value</span></span>  
  
|<span data-ttu-id="1d33f-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1d33f-106">HRESULT</span></span>|<span data-ttu-id="1d33f-107">描述</span><span class="sxs-lookup"><span data-stu-id="1d33f-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1d33f-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d33f-108">S_OK</span></span>|<span data-ttu-id="1d33f-109">`ExitTask`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="1d33f-109">`ExitTask` returned successfully.</span></span>|  
|<span data-ttu-id="1d33f-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1d33f-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1d33f-111">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="1d33f-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1d33f-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1d33f-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1d33f-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="1d33f-113">The call timed out.</span></span>|  
|<span data-ttu-id="1d33f-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1d33f-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1d33f-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="1d33f-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1d33f-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1d33f-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1d33f-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="1d33f-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1d33f-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1d33f-118">E_FAIL</span></span>|<span data-ttu-id="1d33f-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="1d33f-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1d33f-120">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="1d33f-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1d33f-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="1d33f-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d33f-122">备注</span><span class="sxs-lookup"><span data-stu-id="1d33f-122">Remarks</span></span>  
 <span data-ttu-id="1d33f-123">`ExitTask`尝试干净关闭的任务，请在以类似于从非托管的类型库分离线程。</span><span class="sxs-lookup"><span data-stu-id="1d33f-123">`ExitTask` attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d33f-124">要求</span><span class="sxs-lookup"><span data-stu-id="1d33f-124">Requirements</span></span>  
 <span data-ttu-id="1d33f-125">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1d33f-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d33f-126">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1d33f-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d33f-127">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1d33f-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d33f-128">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d33f-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d33f-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d33f-129">See Also</span></span>  
 [<span data-ttu-id="1d33f-130">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="1d33f-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="1d33f-131">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="1d33f-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="1d33f-132">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="1d33f-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="1d33f-133">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="1d33f-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
