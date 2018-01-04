---
title: "IHostTaskManager::SetUILocale 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.SetUILocale
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::SetUILocale
helpviewer_keywords:
- SetUILocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetUILocale method [.NET Framework hosting]
ms.assetid: d0c87a9c-ea81-4237-a16b-c22b36ec9dc8
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 099c3d4878e7dd83be9240e121777c71c2890c88
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagersetuilocale-method"></a><span data-ttu-id="835b8-102">IHostTaskManager::SetUILocale 方法</span><span class="sxs-lookup"><span data-stu-id="835b8-102">IHostTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="835b8-103">通知主机公共语言运行时 (CLR) 已更改的用户界面 (UI) 区域设置或区域性，当前正在执行的任务。</span><span class="sxs-lookup"><span data-stu-id="835b8-103">Notifies the host that the common language runtime (CLR) has changed the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="835b8-104">语法</span><span class="sxs-lookup"><span data-stu-id="835b8-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="835b8-105">参数</span><span class="sxs-lookup"><span data-stu-id="835b8-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="835b8-106">[in]映射到新分配的地理区域性和语言区域设置标识符值。</span><span class="sxs-lookup"><span data-stu-id="835b8-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="835b8-107">返回值</span><span class="sxs-lookup"><span data-stu-id="835b8-107">Return Value</span></span>  
  
|<span data-ttu-id="835b8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="835b8-108">HRESULT</span></span>|<span data-ttu-id="835b8-109">描述</span><span class="sxs-lookup"><span data-stu-id="835b8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="835b8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="835b8-110">S_OK</span></span>|<span data-ttu-id="835b8-111">`SetUILocale`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="835b8-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="835b8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="835b8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="835b8-113">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="835b8-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="835b8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="835b8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="835b8-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="835b8-115">The call timed out.</span></span>|  
|<span data-ttu-id="835b8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="835b8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="835b8-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="835b8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="835b8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="835b8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="835b8-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="835b8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="835b8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="835b8-120">E_FAIL</span></span>|<span data-ttu-id="835b8-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="835b8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="835b8-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="835b8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="835b8-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="835b8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="835b8-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="835b8-124">E_NOTIMPL</span></span>|<span data-ttu-id="835b8-125">主机不允许托管的用户代码更改的 UI 区域性。</span><span class="sxs-lookup"><span data-stu-id="835b8-125">The host does not allow managed user code to change the UI culture.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="835b8-126">备注</span><span class="sxs-lookup"><span data-stu-id="835b8-126">Remarks</span></span>  
 <span data-ttu-id="835b8-127">在运行时调用`SetUILocale`时的值<xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType>属性更改由托管代码。</span><span class="sxs-lookup"><span data-stu-id="835b8-127">The runtime calls `SetUILocale` when the value of the <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="835b8-128">此方法使宿主能够执行的区域设置的同步可能会显示任何机制有机会。</span><span class="sxs-lookup"><span data-stu-id="835b8-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="835b8-129">如果主机不允许使用要从托管代码中，更改的 UI 区域设置，或不实现一种机制来同步区域设置，则应从此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="835b8-129">If a host does not allow the UI locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="835b8-130">惠?</span><span class="sxs-lookup"><span data-stu-id="835b8-130">Requirements</span></span>  
 <span data-ttu-id="835b8-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="835b8-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="835b8-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="835b8-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="835b8-133">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="835b8-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="835b8-134">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="835b8-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="835b8-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="835b8-135">See Also</span></span>  
 [<span data-ttu-id="835b8-136">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="835b8-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="835b8-137">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="835b8-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="835b8-138">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="835b8-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="835b8-139">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="835b8-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="835b8-140">SetLocale 方法</span><span class="sxs-lookup"><span data-stu-id="835b8-140">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)
