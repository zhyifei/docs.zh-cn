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
ms.openlocfilehash: e110f1f5ea326c232c7c96bb05913080e950083d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158894"
---
# <a name="ihosttaskmanagersetuilocale-method"></a><span data-ttu-id="ec067-102">IHostTaskManager::SetUILocale 方法</span><span class="sxs-lookup"><span data-stu-id="ec067-102">IHostTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="ec067-103">通知主机，公共语言运行时 (CLR) 已更改的用户界面 (UI) 区域设置或区域性，当前正在执行的任务。</span><span class="sxs-lookup"><span data-stu-id="ec067-103">Notifies the host that the common language runtime (CLR) has changed the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec067-104">语法</span><span class="sxs-lookup"><span data-stu-id="ec067-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec067-105">参数</span><span class="sxs-lookup"><span data-stu-id="ec067-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="ec067-106">[in]映射到新分配的地理区域性和语言区域设置标识符值。</span><span class="sxs-lookup"><span data-stu-id="ec067-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec067-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ec067-107">Return Value</span></span>  
  
|<span data-ttu-id="ec067-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ec067-108">HRESULT</span></span>|<span data-ttu-id="ec067-109">描述</span><span class="sxs-lookup"><span data-stu-id="ec067-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ec067-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ec067-110">S_OK</span></span>|<span data-ttu-id="ec067-111">`SetUILocale` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ec067-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="ec067-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ec067-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ec067-113">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ec067-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ec067-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ec067-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ec067-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="ec067-115">The call timed out.</span></span>|  
|<span data-ttu-id="ec067-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ec067-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ec067-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ec067-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ec067-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ec067-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ec067-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="ec067-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ec067-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ec067-120">E_FAIL</span></span>|<span data-ttu-id="ec067-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ec067-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ec067-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="ec067-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ec067-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ec067-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ec067-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="ec067-124">E_NOTIMPL</span></span>|<span data-ttu-id="ec067-125">主机不允许托管的用户代码，若要更改的 UI 区域性。</span><span class="sxs-lookup"><span data-stu-id="ec067-125">The host does not allow managed user code to change the UI culture.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec067-126">备注</span><span class="sxs-lookup"><span data-stu-id="ec067-126">Remarks</span></span>  
 <span data-ttu-id="ec067-127">运行时调用`SetUILocale`时的值<xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType>属性更改由托管代码。</span><span class="sxs-lookup"><span data-stu-id="ec067-127">The runtime calls `SetUILocale` when the value of the <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="ec067-128">此方法提供主机后，若要执行同步的区域设置可能具有的任何机制的机会。</span><span class="sxs-lookup"><span data-stu-id="ec067-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="ec067-129">如果主机不允许 UI 区域设置，以便从托管代码中，更改或不实现同步的区域设置的机制，它应从此方法返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="ec067-129">If a host does not allow the UI locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec067-130">要求</span><span class="sxs-lookup"><span data-stu-id="ec067-130">Requirements</span></span>  
 <span data-ttu-id="ec067-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ec067-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec067-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ec067-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ec067-133">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ec067-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec067-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec067-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec067-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec067-135">See also</span></span>

- [<span data-ttu-id="ec067-136">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="ec067-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="ec067-137">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="ec067-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="ec067-138">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="ec067-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="ec067-139">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="ec067-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="ec067-140">SetLocale 方法</span><span class="sxs-lookup"><span data-stu-id="ec067-140">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)
