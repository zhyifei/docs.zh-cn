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
ms.openlocfilehash: 9c08a790d4dad748e5d09271bd870add22255b4a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132611"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="fa33d-102">IHostSyncManager::SetCLRSyncManager 方法</span><span class="sxs-lookup"><span data-stu-id="fa33d-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="fa33d-103">设置要与当前[IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)实例关联的[ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="fa33d-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa33d-104">语法</span><span class="sxs-lookup"><span data-stu-id="fa33d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa33d-105">参数</span><span class="sxs-lookup"><span data-stu-id="fa33d-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="fa33d-106">中指向由公共语言运行时（CLR）提供的 `ICLRSyncManager` 实例的指针。</span><span class="sxs-lookup"><span data-stu-id="fa33d-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa33d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="fa33d-107">Return Value</span></span>  
  
|<span data-ttu-id="fa33d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fa33d-108">HRESULT</span></span>|<span data-ttu-id="fa33d-109">描述</span><span class="sxs-lookup"><span data-stu-id="fa33d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fa33d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fa33d-110">S_OK</span></span>|<span data-ttu-id="fa33d-111">`SetCLRSyncManager` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="fa33d-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="fa33d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fa33d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fa33d-113">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="fa33d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fa33d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fa33d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fa33d-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="fa33d-115">The call timed out.</span></span>|  
|<span data-ttu-id="fa33d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fa33d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fa33d-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="fa33d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fa33d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fa33d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fa33d-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="fa33d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fa33d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fa33d-120">E_FAIL</span></span>|<span data-ttu-id="fa33d-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="fa33d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fa33d-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="fa33d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fa33d-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="fa33d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa33d-124">备注</span><span class="sxs-lookup"><span data-stu-id="fa33d-124">Remarks</span></span>  
 <span data-ttu-id="fa33d-125">为了便于主机与 CLR 之间的通信，宿主接口通常成对出现。</span><span class="sxs-lookup"><span data-stu-id="fa33d-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="fa33d-126">该对的一个成员由主机实现，另一个成员由 CLR 实现。</span><span class="sxs-lookup"><span data-stu-id="fa33d-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="fa33d-127">作为宿主端实现，`IHostSyncManager` 接口对应于 CLR 实现的 `ICLRSyncManager` 接口。</span><span class="sxs-lookup"><span data-stu-id="fa33d-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="fa33d-128">CLR 调用 `SetCLRSyncManager` 为主机提供 `ICLRSyncManager` 实例，以便与当前 `IHostSyncManager` 实例关联。</span><span class="sxs-lookup"><span data-stu-id="fa33d-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa33d-129">要求</span><span class="sxs-lookup"><span data-stu-id="fa33d-129">Requirements</span></span>  
 <span data-ttu-id="fa33d-130">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fa33d-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa33d-131">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fa33d-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa33d-132">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="fa33d-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa33d-133">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa33d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa33d-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa33d-134">See also</span></span>

- [<span data-ttu-id="fa33d-135">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="fa33d-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="fa33d-136">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="fa33d-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
