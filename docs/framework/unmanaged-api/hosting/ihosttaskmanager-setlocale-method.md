---
title: IHostTaskManager::SetLocale 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: 747ee407-ee8c-484d-9583-25089236d2d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b43de32807da2478af23e52997fce2f4da1b339
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674685"
---
# <a name="ihosttaskmanagersetlocale-method"></a><span data-ttu-id="d04b8-102">IHostTaskManager::SetLocale 方法</span><span class="sxs-lookup"><span data-stu-id="d04b8-102">IHostTaskManager::SetLocale Method</span></span>
<span data-ttu-id="d04b8-103">通知主机，公共语言运行时 (CLR) 已更改区域设置或区域性，当前正在执行的任务。</span><span class="sxs-lookup"><span data-stu-id="d04b8-103">Notifies the host that the common language runtime (CLR) has changed the locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d04b8-104">语法</span><span class="sxs-lookup"><span data-stu-id="d04b8-104">Syntax</span></span>  
  
```  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d04b8-105">参数</span><span class="sxs-lookup"><span data-stu-id="d04b8-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="d04b8-106">[in]映射到新分配的地理区域性和语言区域设置标识符值。</span><span class="sxs-lookup"><span data-stu-id="d04b8-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d04b8-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d04b8-107">Return Value</span></span>  
  
|<span data-ttu-id="d04b8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d04b8-108">HRESULT</span></span>|<span data-ttu-id="d04b8-109">描述</span><span class="sxs-lookup"><span data-stu-id="d04b8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d04b8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d04b8-110">S_OK</span></span>|<span data-ttu-id="d04b8-111">`SetLocale` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="d04b8-111">`SetLocale` returned successfully.</span></span>|  
|<span data-ttu-id="d04b8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d04b8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d04b8-113">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d04b8-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d04b8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d04b8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d04b8-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="d04b8-115">The call timed out.</span></span>|  
|<span data-ttu-id="d04b8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d04b8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d04b8-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="d04b8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d04b8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d04b8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d04b8-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="d04b8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d04b8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d04b8-120">E_FAIL</span></span>|<span data-ttu-id="d04b8-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d04b8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d04b8-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="d04b8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d04b8-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d04b8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d04b8-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="d04b8-124">E_NOTIMPL</span></span>|<span data-ttu-id="d04b8-125">主机不允许托管的用户代码，若要修改的区域设置。</span><span class="sxs-lookup"><span data-stu-id="d04b8-125">The host does not allow managed user code to modify the locale.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d04b8-126">备注</span><span class="sxs-lookup"><span data-stu-id="d04b8-126">Remarks</span></span>  
 <span data-ttu-id="d04b8-127">运行时调用`SetLocale`时的值<xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>属性更改由托管代码。</span><span class="sxs-lookup"><span data-stu-id="d04b8-127">The runtime calls `SetLocale` when the value of the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="d04b8-128">此方法提供主机后，若要执行同步的区域设置可能具有的任何机制的机会。</span><span class="sxs-lookup"><span data-stu-id="d04b8-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="d04b8-129">如果主机不允许的区域设置，若要从托管代码中，更改或不实现同步的区域设置的机制，它应从此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="d04b8-129">If a host does not allow the locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d04b8-130">要求</span><span class="sxs-lookup"><span data-stu-id="d04b8-130">Requirements</span></span>  
 <span data-ttu-id="d04b8-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d04b8-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d04b8-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d04b8-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d04b8-133">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d04b8-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d04b8-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d04b8-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d04b8-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="d04b8-135">See also</span></span>
- [<span data-ttu-id="d04b8-136">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="d04b8-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="d04b8-137">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="d04b8-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="d04b8-138">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="d04b8-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="d04b8-139">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="d04b8-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="d04b8-140">SetUILocale 方法</span><span class="sxs-lookup"><span data-stu-id="d04b8-140">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)
