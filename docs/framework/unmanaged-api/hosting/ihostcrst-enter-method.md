---
title: "IHostCrst::Enter 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst.Enter
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst::Enter
helpviewer_keywords:
- Enter method [.NET Framework hosting]
- IHostCrst::Enter method [.NET Framework hosting]
ms.assetid: 100dd7eb-7053-4295-9bb3-32ba47f6ec79
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9d209e13360616295f166ad23c65b0c4e764af79
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="7de41-102">IHostCrst::Enter 方法</span><span class="sxs-lookup"><span data-stu-id="7de41-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="7de41-103">进入临界区表示由当前[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="7de41-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7de41-104">语法</span><span class="sxs-lookup"><span data-stu-id="7de41-104">Syntax</span></span>  
  
```  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7de41-105">参数</span><span class="sxs-lookup"><span data-stu-id="7de41-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="7de41-106">[in]之一[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)值，指示主机时应采取什么操作的操作块。</span><span class="sxs-lookup"><span data-stu-id="7de41-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7de41-107">返回值</span><span class="sxs-lookup"><span data-stu-id="7de41-107">Return Value</span></span>  
  
|<span data-ttu-id="7de41-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7de41-108">HRESULT</span></span>|<span data-ttu-id="7de41-109">描述</span><span class="sxs-lookup"><span data-stu-id="7de41-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7de41-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7de41-110">S_OK</span></span>|<span data-ttu-id="7de41-111">`Enter`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="7de41-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="7de41-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7de41-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7de41-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="7de41-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7de41-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7de41-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7de41-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="7de41-115">The call timed out.</span></span>|  
|<span data-ttu-id="7de41-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7de41-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7de41-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="7de41-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7de41-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7de41-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7de41-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="7de41-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7de41-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7de41-120">E_FAIL</span></span>|<span data-ttu-id="7de41-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="7de41-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7de41-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="7de41-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7de41-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="7de41-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7de41-124">备注</span><span class="sxs-lookup"><span data-stu-id="7de41-124">Remarks</span></span>  
 <span data-ttu-id="7de41-125">`Enter`镜像 Win32`EnterCriticalSection`函数。</span><span class="sxs-lookup"><span data-stu-id="7de41-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7de41-126">此方法不返回直到输入关键部分。</span><span class="sxs-lookup"><span data-stu-id="7de41-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7de41-127">要求</span><span class="sxs-lookup"><span data-stu-id="7de41-127">Requirements</span></span>  
 <span data-ttu-id="7de41-128">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7de41-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7de41-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7de41-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7de41-130">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7de41-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7de41-131">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7de41-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7de41-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7de41-132">See Also</span></span>  
 [<span data-ttu-id="7de41-133">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="7de41-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="7de41-134">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="7de41-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="7de41-135">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="7de41-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
