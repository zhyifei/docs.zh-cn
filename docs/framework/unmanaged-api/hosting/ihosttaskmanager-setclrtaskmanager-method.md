---
title: IHostTaskManager::SetCLRTaskManager 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetCLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetCLRTaskManager
helpviewer_keywords:
- IHostTaskManager::SetCLRTaskManager method [.NET Framework hosting]
- SetCLRTaskManager method [.NET Framework hosting]
ms.assetid: ec90ee83-bd4b-408b-9274-62a923ab86a1
topic_type:
- apiref
ms.openlocfilehash: c674cc43065bf8ea102bec1c5134757380454913
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141240"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="a27da-102">IHostTaskManager::SetCLRTaskManager 方法</span><span class="sxs-lookup"><span data-stu-id="a27da-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="a27da-103">向宿主提供一个接口指针，该指针指向由公共语言运行时（CLR）实现的[ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="a27da-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a27da-104">语法</span><span class="sxs-lookup"><span data-stu-id="a27da-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a27da-105">参数</span><span class="sxs-lookup"><span data-stu-id="a27da-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="a27da-106">中指向由公共语言运行时实现的 `ICLRTaskManager` 实例的指针。</span><span class="sxs-lookup"><span data-stu-id="a27da-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a27da-107">返回值</span><span class="sxs-lookup"><span data-stu-id="a27da-107">Return Value</span></span>  
  
|<span data-ttu-id="a27da-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a27da-108">HRESULT</span></span>|<span data-ttu-id="a27da-109">描述</span><span class="sxs-lookup"><span data-stu-id="a27da-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a27da-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a27da-110">S_OK</span></span>|<span data-ttu-id="a27da-111">`SetCLRTaskManager` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="a27da-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="a27da-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a27da-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a27da-113">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="a27da-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a27da-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a27da-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a27da-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="a27da-115">The call timed out.</span></span>|  
|<span data-ttu-id="a27da-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a27da-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a27da-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="a27da-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a27da-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a27da-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a27da-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="a27da-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a27da-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a27da-120">E_FAIL</span></span>|<span data-ttu-id="a27da-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="a27da-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a27da-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="a27da-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a27da-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="a27da-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a27da-124">备注</span><span class="sxs-lookup"><span data-stu-id="a27da-124">Remarks</span></span>  
 <span data-ttu-id="a27da-125">运行时调用 `SetCLRTaskManager` 向宿主提供指向 `ICLRTaskManager` 实例的接口指针。</span><span class="sxs-lookup"><span data-stu-id="a27da-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a27da-126">要求</span><span class="sxs-lookup"><span data-stu-id="a27da-126">Requirements</span></span>  
 <span data-ttu-id="a27da-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a27da-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a27da-128">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a27da-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a27da-129">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="a27da-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a27da-130">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a27da-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a27da-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="a27da-131">See also</span></span>

- [<span data-ttu-id="a27da-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="a27da-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="a27da-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="a27da-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="a27da-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="a27da-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="a27da-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="a27da-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
