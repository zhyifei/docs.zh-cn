---
title: IHostPolicyManager::OnDefaultAction 方法
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnDefaultAction
helpviewer_keywords:
- OnDefaultAction method [.NET Framework hosting]
- IHostPolicyManager::OnDefaultAction method [.NET Framework hosting]
ms.assetid: 071e73bd-4795-470f-9373-cfaef553b7f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 17a14b09de14f32e2ae3646f7847d44307ab3b53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439057"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="c8bb8-102">IHostPolicyManager::OnDefaultAction 方法</span><span class="sxs-lookup"><span data-stu-id="c8bb8-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="c8bb8-103">通知公共语言运行时 (CLR) 是执行默认操作调用所设置的主机[iclrpolicymanager:: Setdefaultaction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)方法以响应线程中止或<xref:System.AppDomain>卸载。</span><span class="sxs-lookup"><span data-stu-id="c8bb8-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8bb8-104">语法</span><span class="sxs-lookup"><span data-stu-id="c8bb8-104">Syntax</span></span>  
  
```  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8bb8-105">参数</span><span class="sxs-lookup"><span data-stu-id="c8bb8-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="c8bb8-106">[in]之一[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)值，指示回复 CLR 的事件的种类。</span><span class="sxs-lookup"><span data-stu-id="c8bb8-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="c8bb8-107">[in]之一[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值，指示 CLR 正在以响应事件的操作。</span><span class="sxs-lookup"><span data-stu-id="c8bb8-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8bb8-108">返回值</span><span class="sxs-lookup"><span data-stu-id="c8bb8-108">Return Value</span></span>  
  
|<span data-ttu-id="c8bb8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c8bb8-109">HRESULT</span></span>|<span data-ttu-id="c8bb8-110">描述</span><span class="sxs-lookup"><span data-stu-id="c8bb8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c8bb8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c8bb8-111">S_OK</span></span>|<span data-ttu-id="c8bb8-112">`OnDefaultAction` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="c8bb8-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="c8bb8-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c8bb8-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c8bb8-114">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c8bb8-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="c8bb8-115">已成功</span><span class="sxs-lookup"><span data-stu-id="c8bb8-115">successfully</span></span>|  
|<span data-ttu-id="c8bb8-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c8bb8-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c8bb8-117">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="c8bb8-117">The call timed out.</span></span>|  
|<span data-ttu-id="c8bb8-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c8bb8-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c8bb8-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c8bb8-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c8bb8-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c8bb8-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c8bb8-121">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="c8bb8-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c8bb8-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c8bb8-122">E_FAIL</span></span>|<span data-ttu-id="c8bb8-123">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c8bb8-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c8bb8-124">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="c8bb8-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c8bb8-125">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c8bb8-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c8bb8-126">要求</span><span class="sxs-lookup"><span data-stu-id="c8bb8-126">Requirements</span></span>  
 <span data-ttu-id="c8bb8-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c8bb8-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8bb8-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c8bb8-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8bb8-129">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c8bb8-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8bb8-130">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8bb8-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8bb8-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8bb8-131">See Also</span></span>  
 [<span data-ttu-id="c8bb8-132">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="c8bb8-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="c8bb8-133">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="c8bb8-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="c8bb8-134">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="c8bb8-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="c8bb8-135">IHostPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="c8bb8-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
