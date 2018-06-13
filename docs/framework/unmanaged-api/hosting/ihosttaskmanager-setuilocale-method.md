---
title: IHostTaskManager::SetUILocale 方法
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetUILocale
helpviewer_keywords:
- SetUILocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetUILocale method [.NET Framework hosting]
ms.assetid: d0c87a9c-ea81-4237-a16b-c22b36ec9dc8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f929dceafc72af89cfd85b1617de7bbd0bc0dfff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442737"
---
# <a name="ihosttaskmanagersetuilocale-method"></a><span data-ttu-id="5e047-102">IHostTaskManager::SetUILocale 方法</span><span class="sxs-lookup"><span data-stu-id="5e047-102">IHostTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="5e047-103">通知主机公共语言运行时 (CLR) 已更改的用户界面 (UI) 区域设置或区域性，当前正在执行的任务。</span><span class="sxs-lookup"><span data-stu-id="5e047-103">Notifies the host that the common language runtime (CLR) has changed the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e047-104">语法</span><span class="sxs-lookup"><span data-stu-id="5e047-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5e047-105">参数</span><span class="sxs-lookup"><span data-stu-id="5e047-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="5e047-106">[in]映射到新分配的地理区域性和语言区域设置标识符值。</span><span class="sxs-lookup"><span data-stu-id="5e047-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e047-107">返回值</span><span class="sxs-lookup"><span data-stu-id="5e047-107">Return Value</span></span>  
  
|<span data-ttu-id="5e047-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5e047-108">HRESULT</span></span>|<span data-ttu-id="5e047-109">描述</span><span class="sxs-lookup"><span data-stu-id="5e047-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5e047-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5e047-110">S_OK</span></span>|<span data-ttu-id="5e047-111">`SetUILocale` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="5e047-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="5e047-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5e047-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5e047-113">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="5e047-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5e047-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5e047-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5e047-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="5e047-115">The call timed out.</span></span>|  
|<span data-ttu-id="5e047-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5e047-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5e047-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="5e047-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5e047-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5e047-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5e047-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="5e047-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5e047-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5e047-120">E_FAIL</span></span>|<span data-ttu-id="5e047-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="5e047-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5e047-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="5e047-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5e047-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="5e047-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5e047-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="5e047-124">E_NOTIMPL</span></span>|<span data-ttu-id="5e047-125">主机不允许托管的用户代码更改的 UI 区域性。</span><span class="sxs-lookup"><span data-stu-id="5e047-125">The host does not allow managed user code to change the UI culture.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e047-126">备注</span><span class="sxs-lookup"><span data-stu-id="5e047-126">Remarks</span></span>  
 <span data-ttu-id="5e047-127">在运行时调用`SetUILocale`时的值<xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType>属性更改由托管代码。</span><span class="sxs-lookup"><span data-stu-id="5e047-127">The runtime calls `SetUILocale` when the value of the <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="5e047-128">此方法使宿主能够执行的区域设置的同步可能会显示任何机制有机会。</span><span class="sxs-lookup"><span data-stu-id="5e047-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="5e047-129">如果主机不允许使用要从托管代码中，更改的 UI 区域设置，或不实现一种机制来同步区域设置，则应从此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="5e047-129">If a host does not allow the UI locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e047-130">要求</span><span class="sxs-lookup"><span data-stu-id="5e047-130">Requirements</span></span>  
 <span data-ttu-id="5e047-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5e047-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e047-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5e047-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5e047-133">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5e047-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5e047-134">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e047-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e047-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e047-135">See Also</span></span>  
 [<span data-ttu-id="5e047-136">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="5e047-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="5e047-137">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="5e047-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="5e047-138">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="5e047-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="5e047-139">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="5e047-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="5e047-140">SetLocale 方法</span><span class="sxs-lookup"><span data-stu-id="5e047-140">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)
