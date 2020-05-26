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
ms.openlocfilehash: bbeae2561d2d340c1a7dfed38e740dcc6838e4da
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803096"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="d4738-102">IHostSyncManager::SetCLRSyncManager 方法</span><span class="sxs-lookup"><span data-stu-id="d4738-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="d4738-103">设置要与当前[IHostSyncManager](ihostsyncmanager-interface.md)实例关联的[ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="d4738-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4738-104">语法</span><span class="sxs-lookup"><span data-stu-id="d4738-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4738-105">参数</span><span class="sxs-lookup"><span data-stu-id="d4738-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="d4738-106">中指向 `ICLRSyncManager` 由公共语言运行时（CLR）提供的实例的指针。</span><span class="sxs-lookup"><span data-stu-id="d4738-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4738-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d4738-107">Return Value</span></span>  
  
|<span data-ttu-id="d4738-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d4738-108">HRESULT</span></span>|<span data-ttu-id="d4738-109">说明</span><span class="sxs-lookup"><span data-stu-id="d4738-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d4738-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d4738-110">S_OK</span></span>|<span data-ttu-id="d4738-111">`SetCLRSyncManager`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="d4738-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="d4738-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d4738-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d4738-113">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d4738-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d4738-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d4738-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d4738-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="d4738-115">The call timed out.</span></span>|  
|<span data-ttu-id="d4738-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d4738-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d4738-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="d4738-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d4738-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d4738-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d4738-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="d4738-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d4738-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d4738-120">E_FAIL</span></span>|<span data-ttu-id="d4738-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d4738-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d4738-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="d4738-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d4738-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d4738-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4738-124">备注</span><span class="sxs-lookup"><span data-stu-id="d4738-124">Remarks</span></span>  
 <span data-ttu-id="d4738-125">为了便于主机与 CLR 之间的通信，宿主接口通常成对出现。</span><span class="sxs-lookup"><span data-stu-id="d4738-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="d4738-126">该对的一个成员由主机实现，另一个成员由 CLR 实现。</span><span class="sxs-lookup"><span data-stu-id="d4738-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="d4738-127">作为宿主端实现， `IHostSyncManager` 接口对应于 `ICLRSyncManager` CLR 实现的接口。</span><span class="sxs-lookup"><span data-stu-id="d4738-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="d4738-128">CLR 将调用 `SetCLRSyncManager` 以提供 `ICLRSyncManager` 与当前实例关联的主机的实例 `IHostSyncManager` 。</span><span class="sxs-lookup"><span data-stu-id="d4738-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4738-129">要求</span><span class="sxs-lookup"><span data-stu-id="d4738-129">Requirements</span></span>  
 <span data-ttu-id="d4738-130">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d4738-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4738-131">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d4738-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d4738-132">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d4738-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d4738-133">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4738-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4738-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4738-134">See also</span></span>

- [<span data-ttu-id="d4738-135">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="d4738-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="d4738-136">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="d4738-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
