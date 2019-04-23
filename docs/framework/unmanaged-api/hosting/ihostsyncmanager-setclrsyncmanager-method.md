---
title: IHostSyncManager::SetCLRSyncManager 方法
ms.date: 03/30/2017
api_name:
- IHostSyncManager.SetCLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::SetCLRSyncManager
helpviewer_keywords:
- IHostSyncManager::SetCLRSyncManager method [.NET Framework hosting]
- SetCLRSyncManager method [.NET Framework hosting]
ms.assetid: 2b8bbe76-a45d-4989-bacb-11df42f8798c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5006e171e2d5bbdd0d9d4a484299b1860c079b3f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105789"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="244fc-102">IHostSyncManager::SetCLRSyncManager 方法</span><span class="sxs-lookup"><span data-stu-id="244fc-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="244fc-103">集[ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)要关联与当前实例[IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="244fc-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="244fc-104">语法</span><span class="sxs-lookup"><span data-stu-id="244fc-104">Syntax</span></span>  
  
```  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="244fc-105">参数</span><span class="sxs-lookup"><span data-stu-id="244fc-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="244fc-106">[in]一个指向`ICLRSyncManager`由公共语言运行时 (CLR) 提供的实例。</span><span class="sxs-lookup"><span data-stu-id="244fc-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="244fc-107">返回值</span><span class="sxs-lookup"><span data-stu-id="244fc-107">Return Value</span></span>  
  
|<span data-ttu-id="244fc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="244fc-108">HRESULT</span></span>|<span data-ttu-id="244fc-109">描述</span><span class="sxs-lookup"><span data-stu-id="244fc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="244fc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="244fc-110">S_OK</span></span>|<span data-ttu-id="244fc-111">`SetCLRSyncManager` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="244fc-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="244fc-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="244fc-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="244fc-113">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="244fc-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="244fc-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="244fc-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="244fc-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="244fc-115">The call timed out.</span></span>|  
|<span data-ttu-id="244fc-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="244fc-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="244fc-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="244fc-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="244fc-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="244fc-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="244fc-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="244fc-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="244fc-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="244fc-120">E_FAIL</span></span>|<span data-ttu-id="244fc-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="244fc-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="244fc-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="244fc-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="244fc-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="244fc-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="244fc-124">备注</span><span class="sxs-lookup"><span data-stu-id="244fc-124">Remarks</span></span>  
 <span data-ttu-id="244fc-125">为了便于在主机和 CLR 之间的通信，承载接口通常成对出现。</span><span class="sxs-lookup"><span data-stu-id="244fc-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="244fc-126">由主机实现的对中的一个成员和由 CLR 实现其他成员。</span><span class="sxs-lookup"><span data-stu-id="244fc-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="244fc-127">主机端实现中，作为`IHostSyncManager`接口对应于`ICLRSyncManager`由 CLR 实现的接口。</span><span class="sxs-lookup"><span data-stu-id="244fc-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="244fc-128">CLR 调用`SetCLRSyncManager`提供`ICLRSyncManager`为要将与当前相关联的主机实例`IHostSyncManager`实例。</span><span class="sxs-lookup"><span data-stu-id="244fc-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="244fc-129">要求</span><span class="sxs-lookup"><span data-stu-id="244fc-129">Requirements</span></span>  
 <span data-ttu-id="244fc-130">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="244fc-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="244fc-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="244fc-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="244fc-132">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="244fc-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="244fc-133">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="244fc-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="244fc-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="244fc-134">See also</span></span>

- [<span data-ttu-id="244fc-135">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="244fc-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="244fc-136">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="244fc-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
