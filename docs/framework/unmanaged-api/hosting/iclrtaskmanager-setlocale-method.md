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
ms.openlocfilehash: ae097320ad7cd6e7c840122bf3f315812e9b2acd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199201"
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="2ab19-102">ICLRTaskManager::SetLocale 方法</span><span class="sxs-lookup"><span data-stu-id="2ab19-102">ICLRTaskManager::SetLocale Method</span></span>
<span data-ttu-id="2ab19-103">通知公共语言运行时 (CLR) 主机已修改当前正在执行的任务的区域设置标识符 （可映射到地理区域性和语言） 的值。</span><span class="sxs-lookup"><span data-stu-id="2ab19-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ab19-104">语法</span><span class="sxs-lookup"><span data-stu-id="2ab19-104">Syntax</span></span>  
  
```  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ab19-105">参数</span><span class="sxs-lookup"><span data-stu-id="2ab19-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="2ab19-106">[in]映射到新分配的地理区域性和语言区域设置标识符值。</span><span class="sxs-lookup"><span data-stu-id="2ab19-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ab19-107">返回值</span><span class="sxs-lookup"><span data-stu-id="2ab19-107">Return Value</span></span>  
  
|<span data-ttu-id="2ab19-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2ab19-108">HRESULT</span></span>|<span data-ttu-id="2ab19-109">描述</span><span class="sxs-lookup"><span data-stu-id="2ab19-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2ab19-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2ab19-110">S_OK</span></span>|<span data-ttu-id="2ab19-111">该方法成功返回。</span><span class="sxs-lookup"><span data-stu-id="2ab19-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="2ab19-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2ab19-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2ab19-113">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="2ab19-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2ab19-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2ab19-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2ab19-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="2ab19-115">The call timed out.</span></span>|  
|<span data-ttu-id="2ab19-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2ab19-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2ab19-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="2ab19-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2ab19-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2ab19-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2ab19-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="2ab19-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2ab19-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2ab19-120">E_FAIL</span></span>|<span data-ttu-id="2ab19-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="2ab19-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2ab19-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="2ab19-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2ab19-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="2ab19-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ab19-124">备注</span><span class="sxs-lookup"><span data-stu-id="2ab19-124">Remarks</span></span>  
 <span data-ttu-id="2ab19-125">`SetLocale` 使宿主有机会执行同步的区域设置可能具有的任何机制。</span><span class="sxs-lookup"><span data-stu-id="2ab19-125">`SetLocale` gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ab19-126">要求</span><span class="sxs-lookup"><span data-stu-id="2ab19-126">Requirements</span></span>  
 <span data-ttu-id="2ab19-127">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2ab19-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ab19-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2ab19-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ab19-129">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2ab19-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ab19-130">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ab19-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ab19-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ab19-131">See also</span></span>

- [<span data-ttu-id="2ab19-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="2ab19-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2ab19-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="2ab19-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2ab19-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="2ab19-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2ab19-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="2ab19-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
