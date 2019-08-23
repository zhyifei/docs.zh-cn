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
ms.openlocfilehash: bdc597e741023af1c7cc1f48e378083157dd4a5d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937739"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="c8f9d-102">IHostCrst::Enter 方法</span><span class="sxs-lookup"><span data-stu-id="c8f9d-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="c8f9d-103">输入当前[IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)实例所表示的临界区。</span><span class="sxs-lookup"><span data-stu-id="c8f9d-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8f9d-104">语法</span><span class="sxs-lookup"><span data-stu-id="c8f9d-104">Syntax</span></span>  
  
```cpp  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8f9d-105">参数</span><span class="sxs-lookup"><span data-stu-id="c8f9d-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="c8f9d-106">中[WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)值之一, 指示当操作阻止时主机应采取的操作。</span><span class="sxs-lookup"><span data-stu-id="c8f9d-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8f9d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c8f9d-107">Return Value</span></span>  
  
|<span data-ttu-id="c8f9d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c8f9d-108">HRESULT</span></span>|<span data-ttu-id="c8f9d-109">描述</span><span class="sxs-lookup"><span data-stu-id="c8f9d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c8f9d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c8f9d-110">S_OK</span></span>|<span data-ttu-id="c8f9d-111">`Enter`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="c8f9d-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="c8f9d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c8f9d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c8f9d-113">公共语言运行时 (CLR) 未加载到进程中, 或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c8f9d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c8f9d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c8f9d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c8f9d-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="c8f9d-115">The call timed out.</span></span>|  
|<span data-ttu-id="c8f9d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c8f9d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c8f9d-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c8f9d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c8f9d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c8f9d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c8f9d-119">已阻止的线程或纤程正在等待某个事件时, 该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="c8f9d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c8f9d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c8f9d-120">E_FAIL</span></span>|<span data-ttu-id="c8f9d-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c8f9d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c8f9d-122">当方法返回 E_FAIL 时, CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="c8f9d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c8f9d-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c8f9d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8f9d-124">备注</span><span class="sxs-lookup"><span data-stu-id="c8f9d-124">Remarks</span></span>  
 <span data-ttu-id="c8f9d-125">`Enter`对 Win32 `EnterCriticalSection`函数进行镜像。</span><span class="sxs-lookup"><span data-stu-id="c8f9d-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c8f9d-126">直到进入临界区, 此方法才会返回。</span><span class="sxs-lookup"><span data-stu-id="c8f9d-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8f9d-127">要求</span><span class="sxs-lookup"><span data-stu-id="c8f9d-127">Requirements</span></span>  
 <span data-ttu-id="c8f9d-128">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c8f9d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8f9d-129">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c8f9d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8f9d-130">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c8f9d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8f9d-131">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8f9d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8f9d-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8f9d-132">See also</span></span>

- [<span data-ttu-id="c8f9d-133">ICLRSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="c8f9d-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="c8f9d-134">IHostCrst 接口</span><span class="sxs-lookup"><span data-stu-id="c8f9d-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="c8f9d-135">IHostSyncManager 接口</span><span class="sxs-lookup"><span data-stu-id="c8f9d-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
