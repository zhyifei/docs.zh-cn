---
title: ICLRTaskManager::SetLocale 方法
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: ed16bb7f-4206-43a8-b9e9-c5737b69e3af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab6b13c6b7dba34f5ea82d05f483b36bf96aab1d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437321"
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="3dc5d-102">ICLRTaskManager::SetLocale 方法</span><span class="sxs-lookup"><span data-stu-id="3dc5d-102">ICLRTaskManager::SetLocale Method</span></span>
<span data-ttu-id="3dc5d-103">通知宿主已修改的当前正在执行的任务的区域设置标识符 （可映射到地理区域性和语言） 的值的公共语言运行时 (CLR)。</span><span class="sxs-lookup"><span data-stu-id="3dc5d-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dc5d-104">语法</span><span class="sxs-lookup"><span data-stu-id="3dc5d-104">Syntax</span></span>  
  
```  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3dc5d-105">参数</span><span class="sxs-lookup"><span data-stu-id="3dc5d-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="3dc5d-106">[in]映射到新分配的地理区域性和语言区域设置标识符值。</span><span class="sxs-lookup"><span data-stu-id="3dc5d-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3dc5d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="3dc5d-107">Return Value</span></span>  
  
|<span data-ttu-id="3dc5d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3dc5d-108">HRESULT</span></span>|<span data-ttu-id="3dc5d-109">描述</span><span class="sxs-lookup"><span data-stu-id="3dc5d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3dc5d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3dc5d-110">S_OK</span></span>|<span data-ttu-id="3dc5d-111">该方法返回成功。</span><span class="sxs-lookup"><span data-stu-id="3dc5d-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="3dc5d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3dc5d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3dc5d-113">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="3dc5d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3dc5d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3dc5d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3dc5d-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="3dc5d-115">The call timed out.</span></span>|  
|<span data-ttu-id="3dc5d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3dc5d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3dc5d-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="3dc5d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3dc5d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3dc5d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3dc5d-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="3dc5d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3dc5d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3dc5d-120">E_FAIL</span></span>|<span data-ttu-id="3dc5d-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="3dc5d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3dc5d-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="3dc5d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3dc5d-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="3dc5d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3dc5d-124">备注</span><span class="sxs-lookup"><span data-stu-id="3dc5d-124">Remarks</span></span>  
 <span data-ttu-id="3dc5d-125">`SetLocale` 使主机能够执行的区域设置的同步可能会显示任何机制。</span><span class="sxs-lookup"><span data-stu-id="3dc5d-125">`SetLocale` gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dc5d-126">要求</span><span class="sxs-lookup"><span data-stu-id="3dc5d-126">Requirements</span></span>  
 <span data-ttu-id="3dc5d-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3dc5d-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dc5d-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3dc5d-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3dc5d-129">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3dc5d-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3dc5d-130">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dc5d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dc5d-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="3dc5d-131">See Also</span></span>  
 [<span data-ttu-id="3dc5d-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="3dc5d-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="3dc5d-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="3dc5d-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="3dc5d-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="3dc5d-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="3dc5d-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="3dc5d-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
