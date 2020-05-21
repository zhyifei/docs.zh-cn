---
title: ICLRTask::LocksHeld 方法
ms.date: 03/30/2017
api_name:
- ICLRTask.LocksHeld
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::LocksHeld
helpviewer_keywords:
- LocksHeld method [.NET Framework hosting]
- ICLRTask::LocksHeld method [.NET Framework hosting]
ms.assetid: e88a4dc3-02cc-4703-a474-292b71c40657
topic_type:
- apiref
ms.openlocfilehash: c67f00acd61d6e0cdf3adfa0d3d0fda2a06a6f31
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762974"
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="df914-102">ICLRTask::LocksHeld 方法</span><span class="sxs-lookup"><span data-stu-id="df914-102">ICLRTask::LocksHeld Method</span></span>
<span data-ttu-id="df914-103">获取任务当前持有的锁的数目。</span><span class="sxs-lookup"><span data-stu-id="df914-103">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df914-104">语法</span><span class="sxs-lookup"><span data-stu-id="df914-104">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df914-105">参数</span><span class="sxs-lookup"><span data-stu-id="df914-105">Parameters</span></span>  
 `pLockCount`  
 <span data-ttu-id="df914-106">弄在调用方法时任务中持有的锁的数目。</span><span class="sxs-lookup"><span data-stu-id="df914-106">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df914-107">返回值</span><span class="sxs-lookup"><span data-stu-id="df914-107">Return Value</span></span>  
  
|<span data-ttu-id="df914-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df914-108">HRESULT</span></span>|<span data-ttu-id="df914-109">说明</span><span class="sxs-lookup"><span data-stu-id="df914-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df914-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="df914-110">S_OK</span></span>|<span data-ttu-id="df914-111">`LocksHeld`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="df914-111">`LocksHeld` returned successfully.</span></span>|  
|<span data-ttu-id="df914-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="df914-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="df914-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="df914-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="df914-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="df914-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="df914-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="df914-115">The call timed out.</span></span>|  
|<span data-ttu-id="df914-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="df914-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="df914-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="df914-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="df914-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="df914-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="df914-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="df914-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="df914-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="df914-120">E_FAIL</span></span>|<span data-ttu-id="df914-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="df914-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="df914-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="df914-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="df914-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="df914-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="df914-124">要求</span><span class="sxs-lookup"><span data-stu-id="df914-124">Requirements</span></span>  
 <span data-ttu-id="df914-125">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="df914-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df914-126">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="df914-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df914-127">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="df914-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df914-128">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df914-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df914-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df914-129">See also</span></span>

- [<span data-ttu-id="df914-130">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="df914-130">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="df914-131">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="df914-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="df914-132">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="df914-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="df914-133">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="df914-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
