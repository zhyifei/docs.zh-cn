---
title: "IHostTaskManager::SetCLRTaskManager 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.SetCLRTaskManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::SetCLRTaskManager
helpviewer_keywords:
- IHostTaskManager::SetCLRTaskManager method [.NET Framework hosting]
- SetCLRTaskManager method [.NET Framework hosting]
ms.assetid: ec90ee83-bd4b-408b-9274-62a923ab86a1
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ec0d515ad4c0bc21e1036f20f17bf168d7af79d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="1c7c1-102">IHostTaskManager::SetCLRTaskManager 方法</span><span class="sxs-lookup"><span data-stu-id="1c7c1-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="1c7c1-103">为宿主提供的接口指针到[ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)由公共语言运行时 (CLR) 实现的实例。</span><span class="sxs-lookup"><span data-stu-id="1c7c1-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c7c1-104">语法</span><span class="sxs-lookup"><span data-stu-id="1c7c1-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c7c1-105">参数</span><span class="sxs-lookup"><span data-stu-id="1c7c1-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="1c7c1-106">[in]指向的指针`ICLRTaskManager`由公共语言运行时实现的实例。</span><span class="sxs-lookup"><span data-stu-id="1c7c1-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c7c1-107">返回值</span><span class="sxs-lookup"><span data-stu-id="1c7c1-107">Return Value</span></span>  
  
|<span data-ttu-id="1c7c1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1c7c1-108">HRESULT</span></span>|<span data-ttu-id="1c7c1-109">描述</span><span class="sxs-lookup"><span data-stu-id="1c7c1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1c7c1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1c7c1-110">S_OK</span></span>|<span data-ttu-id="1c7c1-111">`SetCLRTaskManager`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="1c7c1-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="1c7c1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1c7c1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1c7c1-113">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="1c7c1-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1c7c1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1c7c1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1c7c1-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="1c7c1-115">The call timed out.</span></span>|  
|<span data-ttu-id="1c7c1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1c7c1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1c7c1-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="1c7c1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1c7c1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1c7c1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1c7c1-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="1c7c1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1c7c1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1c7c1-120">E_FAIL</span></span>|<span data-ttu-id="1c7c1-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="1c7c1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1c7c1-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="1c7c1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1c7c1-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="1c7c1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c7c1-124">备注</span><span class="sxs-lookup"><span data-stu-id="1c7c1-124">Remarks</span></span>  
 <span data-ttu-id="1c7c1-125">在运行时调用`SetCLRTaskManager`以向主机提供的接口指针到`ICLRTaskManager`实例。</span><span class="sxs-lookup"><span data-stu-id="1c7c1-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c7c1-126">要求</span><span class="sxs-lookup"><span data-stu-id="1c7c1-126">Requirements</span></span>  
 <span data-ttu-id="1c7c1-127">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1c7c1-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c7c1-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1c7c1-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1c7c1-129">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1c7c1-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1c7c1-130">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c7c1-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c7c1-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c7c1-131">See Also</span></span>  
 [<span data-ttu-id="1c7c1-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="1c7c1-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="1c7c1-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="1c7c1-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="1c7c1-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="1c7c1-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="1c7c1-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="1c7c1-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
