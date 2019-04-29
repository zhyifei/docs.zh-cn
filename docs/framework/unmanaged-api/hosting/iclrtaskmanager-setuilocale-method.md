---
title: ICLRTaskManager::SetUILocale 方法
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetUILocale
helpviewer_keywords:
- ICLRTaskManager::SetUILocale method [.NET Framework hosting]
- SetUILocale method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 03adaa9a-2beb-49b3-b2c4-6b4fc3f10715
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03c5c9d04567832951062fe1512a292f9b32a94b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763329"
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="b872e-102">ICLRTaskManager::SetUILocale 方法</span><span class="sxs-lookup"><span data-stu-id="b872e-102">ICLRTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="b872e-103">将公共语言运行时 (CLR) 主机已修改的用户界面 (UI) 区域设置或区域性通知当前执行的任务。</span><span class="sxs-lookup"><span data-stu-id="b872e-103">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b872e-104">语法</span><span class="sxs-lookup"><span data-stu-id="b872e-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b872e-105">参数</span><span class="sxs-lookup"><span data-stu-id="b872e-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="b872e-106">[in]映射到新分配的地理区域性和用户界面的语言区域设置标识符值。</span><span class="sxs-lookup"><span data-stu-id="b872e-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b872e-107">返回值</span><span class="sxs-lookup"><span data-stu-id="b872e-107">Return Value</span></span>  
  
|<span data-ttu-id="b872e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b872e-108">HRESULT</span></span>|<span data-ttu-id="b872e-109">描述</span><span class="sxs-lookup"><span data-stu-id="b872e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b872e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b872e-110">S_OK</span></span>|<span data-ttu-id="b872e-111">`SetUILocale` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="b872e-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="b872e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b872e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b872e-113">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="b872e-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b872e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b872e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b872e-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="b872e-115">The call timed out.</span></span>|  
|<span data-ttu-id="b872e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b872e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b872e-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="b872e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b872e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b872e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b872e-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="b872e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b872e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b872e-120">E_FAIL</span></span>|<span data-ttu-id="b872e-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="b872e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b872e-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="b872e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b872e-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="b872e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b872e-124">备注</span><span class="sxs-lookup"><span data-stu-id="b872e-124">Remarks</span></span>  
 <span data-ttu-id="b872e-125">`SetUILocale` 提供要执行的区域设置的同步它可能会有任何机制的主机的机会。</span><span class="sxs-lookup"><span data-stu-id="b872e-125">`SetUILocale` provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b872e-126">要求</span><span class="sxs-lookup"><span data-stu-id="b872e-126">Requirements</span></span>  
 <span data-ttu-id="b872e-127">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b872e-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b872e-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b872e-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b872e-129">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b872e-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b872e-130">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b872e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b872e-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="b872e-131">See also</span></span>

- [<span data-ttu-id="b872e-132">ICLRTask 接口</span><span class="sxs-lookup"><span data-stu-id="b872e-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="b872e-133">ICLRTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="b872e-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="b872e-134">IHostTask 接口</span><span class="sxs-lookup"><span data-stu-id="b872e-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="b872e-135">IHostTaskManager 接口</span><span class="sxs-lookup"><span data-stu-id="b872e-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
