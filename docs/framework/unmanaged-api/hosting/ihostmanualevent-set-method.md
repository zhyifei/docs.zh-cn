---
title: IHostManualEvent::Set 方法
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Set
helpviewer_keywords:
- Set method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Set method [.NET Framework hosting]
ms.assetid: e930c174-f71d-4faa-bb59-f0fb3df4d77b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 674745636033f42eb8fb67babf6f5a3f013491c0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093496"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="223b5-102">IHostManualEvent::Set 方法</span><span class="sxs-lookup"><span data-stu-id="223b5-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="223b5-103">设置当前[IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)到已发出信号状态的实例。</span><span class="sxs-lookup"><span data-stu-id="223b5-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="223b5-104">语法</span><span class="sxs-lookup"><span data-stu-id="223b5-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="223b5-105">返回值</span><span class="sxs-lookup"><span data-stu-id="223b5-105">Return Value</span></span>  
  
|<span data-ttu-id="223b5-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="223b5-106">HRESULT</span></span>|<span data-ttu-id="223b5-107">描述</span><span class="sxs-lookup"><span data-stu-id="223b5-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="223b5-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="223b5-108">S_OK</span></span>|`Set` <span data-ttu-id="223b5-109">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="223b5-109">returned successfully.</span></span>|  
|<span data-ttu-id="223b5-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="223b5-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="223b5-111">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="223b5-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="223b5-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="223b5-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="223b5-113">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="223b5-113">The call timed out.</span></span>|  
|<span data-ttu-id="223b5-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="223b5-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="223b5-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="223b5-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="223b5-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="223b5-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="223b5-117">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="223b5-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="223b5-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="223b5-118">E_FAIL</span></span>|<span data-ttu-id="223b5-119">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="223b5-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="223b5-120">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="223b5-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="223b5-121">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="223b5-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="223b5-122">要求</span><span class="sxs-lookup"><span data-stu-id="223b5-122">Requirements</span></span>  
 <span data-ttu-id="223b5-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="223b5-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="223b5-124">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="223b5-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="223b5-125">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="223b5-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="223b5-126">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="223b5-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="223b5-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="223b5-127">See also</span></span>

- [<span data-ttu-id="223b5-128">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="223b5-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="223b5-129">IHostAutoEvent 接口</span><span class="sxs-lookup"><span data-stu-id="223b5-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="223b5-130">IHostManualEvent 接口</span><span class="sxs-lookup"><span data-stu-id="223b5-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="223b5-131">IHostSemaphore 接口</span><span class="sxs-lookup"><span data-stu-id="223b5-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="223b5-132">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="223b5-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
