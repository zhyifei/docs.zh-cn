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
ms.openlocfilehash: cdf0a720ac440d156b5b8bdc8dc2c78d3bb5ba86
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128558"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="7449c-102">IHostPolicyManager::OnDefaultAction 方法</span><span class="sxs-lookup"><span data-stu-id="7449c-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="7449c-103">向宿主通知公共语言运行时（CLR）将使用对[ICLRPolicyManager：： SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)方法的调用设置的默认操作，以响应线程中止或 <xref:System.AppDomain> 卸载。</span><span class="sxs-lookup"><span data-stu-id="7449c-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7449c-104">语法</span><span class="sxs-lookup"><span data-stu-id="7449c-104">Syntax</span></span>  
  
```cpp  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7449c-105">参数</span><span class="sxs-lookup"><span data-stu-id="7449c-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="7449c-106">中[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)值之一，指示 CLR 响应的事件类型。</span><span class="sxs-lookup"><span data-stu-id="7449c-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="7449c-107">中[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值之一，指示 CLR 响应事件所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="7449c-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7449c-108">返回值</span><span class="sxs-lookup"><span data-stu-id="7449c-108">Return Value</span></span>  
  
|<span data-ttu-id="7449c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7449c-109">HRESULT</span></span>|<span data-ttu-id="7449c-110">描述</span><span class="sxs-lookup"><span data-stu-id="7449c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7449c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7449c-111">S_OK</span></span>|<span data-ttu-id="7449c-112">`OnDefaultAction` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="7449c-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="7449c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7449c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7449c-114">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="7449c-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="7449c-115">顺利</span><span class="sxs-lookup"><span data-stu-id="7449c-115">successfully</span></span>|  
|<span data-ttu-id="7449c-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7449c-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7449c-117">调用超时。</span><span class="sxs-lookup"><span data-stu-id="7449c-117">The call timed out.</span></span>|  
|<span data-ttu-id="7449c-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7449c-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7449c-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="7449c-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7449c-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7449c-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7449c-121">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="7449c-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7449c-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7449c-122">E_FAIL</span></span>|<span data-ttu-id="7449c-123">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="7449c-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7449c-124">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="7449c-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7449c-125">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="7449c-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7449c-126">要求</span><span class="sxs-lookup"><span data-stu-id="7449c-126">Requirements</span></span>  
 <span data-ttu-id="7449c-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7449c-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7449c-128">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7449c-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7449c-129">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="7449c-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7449c-130">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7449c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7449c-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="7449c-131">See also</span></span>

- [<span data-ttu-id="7449c-132">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="7449c-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="7449c-133">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="7449c-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="7449c-134">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="7449c-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="7449c-135">IHostPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="7449c-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
