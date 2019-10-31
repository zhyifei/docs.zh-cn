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
ms.openlocfilehash: f4b40a595bbdea4dd390a42af6a0d4b1a5efa2f2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130496"
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="74f93-102">IHostCrst::TryEnter 方法</span><span class="sxs-lookup"><span data-stu-id="74f93-102">IHostCrst::TryEnter Method</span></span>
<span data-ttu-id="74f93-103">尝试输入当前[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)实例所表示的临界区。</span><span class="sxs-lookup"><span data-stu-id="74f93-103">Attempts to enter the critical section represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74f93-104">语法</span><span class="sxs-lookup"><span data-stu-id="74f93-104">Syntax</span></span>  
  
```cpp  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74f93-105">参数</span><span class="sxs-lookup"><span data-stu-id="74f93-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="74f93-106">中[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)值之一，指示当操作阻止时主机应采取的操作。</span><span class="sxs-lookup"><span data-stu-id="74f93-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="74f93-107">[out] 如果可以输入临界区，则 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="74f93-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74f93-108">返回值</span><span class="sxs-lookup"><span data-stu-id="74f93-108">Return Value</span></span>  
  
|<span data-ttu-id="74f93-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74f93-109">HRESULT</span></span>|<span data-ttu-id="74f93-110">描述</span><span class="sxs-lookup"><span data-stu-id="74f93-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="74f93-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="74f93-111">S_OK</span></span>|<span data-ttu-id="74f93-112">`TryEnter` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="74f93-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="74f93-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="74f93-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="74f93-114">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="74f93-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="74f93-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="74f93-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="74f93-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="74f93-116">The call timed out.</span></span>|  
|<span data-ttu-id="74f93-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="74f93-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="74f93-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="74f93-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="74f93-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="74f93-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="74f93-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="74f93-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="74f93-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="74f93-121">E_FAIL</span></span>|<span data-ttu-id="74f93-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="74f93-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="74f93-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="74f93-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="74f93-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="74f93-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74f93-125">备注</span><span class="sxs-lookup"><span data-stu-id="74f93-125">Remarks</span></span>  
 <span data-ttu-id="74f93-126">`TryEnter` 立即返回，并指示调用线程是否进入了临界区。</span><span class="sxs-lookup"><span data-stu-id="74f93-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="74f93-127">此方法对 Wind32 `TryEnterCriticalSection` 函数进行镜像。</span><span class="sxs-lookup"><span data-stu-id="74f93-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74f93-128">要求</span><span class="sxs-lookup"><span data-stu-id="74f93-128">Requirements</span></span>  
 <span data-ttu-id="74f93-129">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="74f93-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74f93-130">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="74f93-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74f93-131">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="74f93-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74f93-132">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74f93-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74f93-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="74f93-133">See also</span></span>

- [<span data-ttu-id="74f93-134">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="74f93-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="74f93-135">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="74f93-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="74f93-136">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="74f93-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
