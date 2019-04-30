---
title: IHostCrst::TryEnter 方法
ms.date: 03/30/2017
api_name:
- IHostCrst.TryEnter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::TryEnter
helpviewer_keywords:
- IHostCrst::TryEnter method [.NET Framework hosting]
- TryEnter method [.NET Framework hosting]
ms.assetid: a922fa98-beab-4f09-a342-cc94fc65687f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08e4c395026a743323b40e5b1ace3db64e368078
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967723"
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="7149a-102">IHostCrst::TryEnter 方法</span><span class="sxs-lookup"><span data-stu-id="7149a-102">IHostCrst::TryEnter Method</span></span>
<span data-ttu-id="7149a-103">尝试进入关键节由当前[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="7149a-103">Attempts to enter the critical section represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7149a-104">语法</span><span class="sxs-lookup"><span data-stu-id="7149a-104">Syntax</span></span>  
  
```  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7149a-105">参数</span><span class="sxs-lookup"><span data-stu-id="7149a-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="7149a-106">[in]之一[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)值，它指示主机时应采取什么操作的操作块。</span><span class="sxs-lookup"><span data-stu-id="7149a-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="7149a-107">[out]`true`关键节可输入; 否则为如果`false`。</span><span class="sxs-lookup"><span data-stu-id="7149a-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7149a-108">返回值</span><span class="sxs-lookup"><span data-stu-id="7149a-108">Return Value</span></span>  
  
|<span data-ttu-id="7149a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7149a-109">HRESULT</span></span>|<span data-ttu-id="7149a-110">描述</span><span class="sxs-lookup"><span data-stu-id="7149a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7149a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7149a-111">S_OK</span></span>|<span data-ttu-id="7149a-112">`TryEnter` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="7149a-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="7149a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7149a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7149a-114">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="7149a-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7149a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7149a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7149a-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="7149a-116">The call timed out.</span></span>|  
|<span data-ttu-id="7149a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7149a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7149a-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="7149a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7149a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7149a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7149a-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="7149a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7149a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7149a-121">E_FAIL</span></span>|<span data-ttu-id="7149a-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="7149a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7149a-123">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="7149a-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7149a-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="7149a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7149a-125">备注</span><span class="sxs-lookup"><span data-stu-id="7149a-125">Remarks</span></span>  
 <span data-ttu-id="7149a-126">`TryEnter` 将立即返回，并指示是否调用线程已进入关键节。</span><span class="sxs-lookup"><span data-stu-id="7149a-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="7149a-127">此方法将镜像 Wind32`TryEnterCriticalSection`函数。</span><span class="sxs-lookup"><span data-stu-id="7149a-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7149a-128">要求</span><span class="sxs-lookup"><span data-stu-id="7149a-128">Requirements</span></span>  
 <span data-ttu-id="7149a-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7149a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7149a-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7149a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7149a-131">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7149a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7149a-132">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7149a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7149a-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="7149a-133">See also</span></span>

- [<span data-ttu-id="7149a-134">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="7149a-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="7149a-135">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="7149a-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="7149a-136">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="7149a-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
