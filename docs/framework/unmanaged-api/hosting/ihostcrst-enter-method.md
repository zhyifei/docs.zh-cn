---
title: IHostCrst::Enter 方法
ms.date: 03/30/2017
api_name:
- IHostCrst.Enter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Enter
helpviewer_keywords:
- Enter method [.NET Framework hosting]
- IHostCrst::Enter method [.NET Framework hosting]
ms.assetid: 100dd7eb-7053-4295-9bb3-32ba47f6ec79
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c772f67b8ac09e2383aff335d9f164c2e048cbd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145088"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="40ed0-102">IHostCrst::Enter 方法</span><span class="sxs-lookup"><span data-stu-id="40ed0-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="40ed0-103">进入关键节表示由当前[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="40ed0-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40ed0-104">语法</span><span class="sxs-lookup"><span data-stu-id="40ed0-104">Syntax</span></span>  
  
```  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40ed0-105">参数</span><span class="sxs-lookup"><span data-stu-id="40ed0-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="40ed0-106">[in]之一[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)值，它指示主机时应采取什么操作的操作块。</span><span class="sxs-lookup"><span data-stu-id="40ed0-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40ed0-107">返回值</span><span class="sxs-lookup"><span data-stu-id="40ed0-107">Return Value</span></span>  
  
|<span data-ttu-id="40ed0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="40ed0-108">HRESULT</span></span>|<span data-ttu-id="40ed0-109">描述</span><span class="sxs-lookup"><span data-stu-id="40ed0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="40ed0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="40ed0-110">S_OK</span></span>|`Enter` <span data-ttu-id="40ed0-111">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="40ed0-111">returned successfully.</span></span>|  
|<span data-ttu-id="40ed0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="40ed0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="40ed0-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="40ed0-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="40ed0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="40ed0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="40ed0-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="40ed0-115">The call timed out.</span></span>|  
|<span data-ttu-id="40ed0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="40ed0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="40ed0-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="40ed0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="40ed0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="40ed0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="40ed0-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="40ed0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="40ed0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="40ed0-120">E_FAIL</span></span>|<span data-ttu-id="40ed0-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="40ed0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="40ed0-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="40ed0-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="40ed0-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="40ed0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40ed0-124">备注</span><span class="sxs-lookup"><span data-stu-id="40ed0-124">Remarks</span></span>  
 `Enter` <span data-ttu-id="40ed0-125">镜像 Win32`EnterCriticalSection`函数。</span><span class="sxs-lookup"><span data-stu-id="40ed0-125">mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40ed0-126">此方法不返回，直到输入关键部分。</span><span class="sxs-lookup"><span data-stu-id="40ed0-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40ed0-127">要求</span><span class="sxs-lookup"><span data-stu-id="40ed0-127">Requirements</span></span>  
 <span data-ttu-id="40ed0-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="40ed0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40ed0-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="40ed0-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40ed0-130">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="40ed0-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="40ed0-131">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="40ed0-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="40ed0-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="40ed0-132">See also</span></span>

- [<span data-ttu-id="40ed0-133">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="40ed0-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="40ed0-134">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="40ed0-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="40ed0-135">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="40ed0-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
