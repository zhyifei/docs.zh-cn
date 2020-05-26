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
ms.openlocfilehash: 782a12a47de0196b90de06572520ef5ed36efb26
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804869"
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="aefee-102">IHostCrst::TryEnter 方法</span><span class="sxs-lookup"><span data-stu-id="aefee-102">IHostCrst::TryEnter Method</span></span>
<span data-ttu-id="aefee-103">尝试输入当前[IHostCrst](ihostcrst-interface.md)实例所表示的临界区。</span><span class="sxs-lookup"><span data-stu-id="aefee-103">Attempts to enter the critical section represented by the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aefee-104">语法</span><span class="sxs-lookup"><span data-stu-id="aefee-104">Syntax</span></span>  
  
```cpp  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aefee-105">参数</span><span class="sxs-lookup"><span data-stu-id="aefee-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="aefee-106">中[WAIT_OPTION](wait-option-enumeration.md)值之一，指示在操作阻止时主机应执行的操作。</span><span class="sxs-lookup"><span data-stu-id="aefee-106">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="aefee-107">[out] `true`如果可以输入临界区，则为; 否则为。否则为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="aefee-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aefee-108">返回值</span><span class="sxs-lookup"><span data-stu-id="aefee-108">Return Value</span></span>  
  
|<span data-ttu-id="aefee-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aefee-109">HRESULT</span></span>|<span data-ttu-id="aefee-110">说明</span><span class="sxs-lookup"><span data-stu-id="aefee-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aefee-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="aefee-111">S_OK</span></span>|<span data-ttu-id="aefee-112">`TryEnter`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="aefee-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="aefee-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="aefee-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="aefee-114">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="aefee-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="aefee-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="aefee-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="aefee-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="aefee-116">The call timed out.</span></span>|  
|<span data-ttu-id="aefee-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="aefee-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="aefee-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="aefee-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="aefee-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="aefee-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="aefee-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="aefee-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="aefee-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="aefee-121">E_FAIL</span></span>|<span data-ttu-id="aefee-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="aefee-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="aefee-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="aefee-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="aefee-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="aefee-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aefee-125">备注</span><span class="sxs-lookup"><span data-stu-id="aefee-125">Remarks</span></span>  
 <span data-ttu-id="aefee-126">`TryEnter`立即返回并指示调用线程是否进入了临界区。</span><span class="sxs-lookup"><span data-stu-id="aefee-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="aefee-127">此方法对 Wind32 函数进行镜像 `TryEnterCriticalSection` 。</span><span class="sxs-lookup"><span data-stu-id="aefee-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aefee-128">要求</span><span class="sxs-lookup"><span data-stu-id="aefee-128">Requirements</span></span>  
 <span data-ttu-id="aefee-129">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aefee-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aefee-130">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="aefee-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aefee-131">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="aefee-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aefee-132">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aefee-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aefee-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aefee-133">See also</span></span>

- [<span data-ttu-id="aefee-134">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="aefee-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="aefee-135">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="aefee-135">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="aefee-136">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="aefee-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
