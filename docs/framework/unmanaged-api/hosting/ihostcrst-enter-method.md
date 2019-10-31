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
ms.openlocfilehash: 757fb996b268892818a54a3f80a54edfd89c7630
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124432"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="1f8b1-102">IHostCrst::Enter 方法</span><span class="sxs-lookup"><span data-stu-id="1f8b1-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="1f8b1-103">输入当前[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)实例所表示的临界区。</span><span class="sxs-lookup"><span data-stu-id="1f8b1-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f8b1-104">语法</span><span class="sxs-lookup"><span data-stu-id="1f8b1-104">Syntax</span></span>  
  
```cpp  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f8b1-105">参数</span><span class="sxs-lookup"><span data-stu-id="1f8b1-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="1f8b1-106">中[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)值之一，指示当操作阻止时主机应采取的操作。</span><span class="sxs-lookup"><span data-stu-id="1f8b1-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f8b1-107">返回值</span><span class="sxs-lookup"><span data-stu-id="1f8b1-107">Return Value</span></span>  
  
|<span data-ttu-id="1f8b1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1f8b1-108">HRESULT</span></span>|<span data-ttu-id="1f8b1-109">描述</span><span class="sxs-lookup"><span data-stu-id="1f8b1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1f8b1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1f8b1-110">S_OK</span></span>|<span data-ttu-id="1f8b1-111">`Enter` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="1f8b1-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="1f8b1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1f8b1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1f8b1-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="1f8b1-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1f8b1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1f8b1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1f8b1-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="1f8b1-115">The call timed out.</span></span>|  
|<span data-ttu-id="1f8b1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1f8b1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1f8b1-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="1f8b1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1f8b1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1f8b1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1f8b1-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="1f8b1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1f8b1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1f8b1-120">E_FAIL</span></span>|<span data-ttu-id="1f8b1-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="1f8b1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1f8b1-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="1f8b1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1f8b1-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="1f8b1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f8b1-124">备注</span><span class="sxs-lookup"><span data-stu-id="1f8b1-124">Remarks</span></span>  
 <span data-ttu-id="1f8b1-125">`Enter` 镜像 Win32 `EnterCriticalSection` 函数。</span><span class="sxs-lookup"><span data-stu-id="1f8b1-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f8b1-126">直到进入临界区，此方法才会返回。</span><span class="sxs-lookup"><span data-stu-id="1f8b1-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f8b1-127">要求</span><span class="sxs-lookup"><span data-stu-id="1f8b1-127">Requirements</span></span>  
 <span data-ttu-id="1f8b1-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1f8b1-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f8b1-129">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1f8b1-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1f8b1-130">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="1f8b1-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1f8b1-131">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f8b1-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f8b1-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f8b1-132">See also</span></span>

- [<span data-ttu-id="1f8b1-133">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="1f8b1-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="1f8b1-134">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="1f8b1-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="1f8b1-135">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="1f8b1-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
