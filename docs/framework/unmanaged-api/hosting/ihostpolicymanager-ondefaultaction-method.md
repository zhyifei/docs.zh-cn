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
ms.openlocfilehash: 8d987614c1a5a2c90ccb3faa11c605767ae5cfda
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178023"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="86ae1-102">IHostPolicyManager::OnDefaultAction 方法</span><span class="sxs-lookup"><span data-stu-id="86ae1-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="86ae1-103">通知主机通用语言运行时 （CLR） 即将采取由调用[ICLRPolicyManager：：：SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)方法以响应线程中止或<xref:System.AppDomain>卸载而设置的默认操作。</span><span class="sxs-lookup"><span data-stu-id="86ae1-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86ae1-104">语法</span><span class="sxs-lookup"><span data-stu-id="86ae1-104">Syntax</span></span>  
  
```cpp  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86ae1-105">parameters</span><span class="sxs-lookup"><span data-stu-id="86ae1-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="86ae1-106">[在][EClr操作](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)值之一，指示 CLR 正在响应的事件类型。</span><span class="sxs-lookup"><span data-stu-id="86ae1-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="86ae1-107">[在][EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值之一，指示 CLR 为响应事件而执行的操作。</span><span class="sxs-lookup"><span data-stu-id="86ae1-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86ae1-108">返回值</span><span class="sxs-lookup"><span data-stu-id="86ae1-108">Return Value</span></span>  
  
|<span data-ttu-id="86ae1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="86ae1-109">HRESULT</span></span>|<span data-ttu-id="86ae1-110">说明</span><span class="sxs-lookup"><span data-stu-id="86ae1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="86ae1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="86ae1-111">S_OK</span></span>|<span data-ttu-id="86ae1-112">`OnDefaultAction`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="86ae1-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="86ae1-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="86ae1-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="86ae1-114">CLR 尚未加载到进程中，或者 CLR 处于无法运行托管代码或处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="86ae1-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="86ae1-115">成功</span><span class="sxs-lookup"><span data-stu-id="86ae1-115">successfully</span></span>|  
|<span data-ttu-id="86ae1-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="86ae1-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="86ae1-117">呼叫超时。</span><span class="sxs-lookup"><span data-stu-id="86ae1-117">The call timed out.</span></span>|  
|<span data-ttu-id="86ae1-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="86ae1-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="86ae1-119">调用方不拥有锁。</span><span class="sxs-lookup"><span data-stu-id="86ae1-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="86ae1-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="86ae1-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="86ae1-121">当阻塞的线程或光纤等待事件时，事件已被取消。</span><span class="sxs-lookup"><span data-stu-id="86ae1-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="86ae1-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="86ae1-122">E_FAIL</span></span>|<span data-ttu-id="86ae1-123">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="86ae1-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="86ae1-124">当方法返回E_FAIL时，CLR 在进程中不再可用。</span><span class="sxs-lookup"><span data-stu-id="86ae1-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="86ae1-125">对托管方法的后续调用返回HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="86ae1-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="86ae1-126">要求</span><span class="sxs-lookup"><span data-stu-id="86ae1-126">Requirements</span></span>  
 <span data-ttu-id="86ae1-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="86ae1-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86ae1-128">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="86ae1-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="86ae1-129">**库：** 作为资源包含在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="86ae1-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="86ae1-130">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86ae1-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86ae1-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86ae1-131">See also</span></span>

- [<span data-ttu-id="86ae1-132">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="86ae1-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="86ae1-133">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="86ae1-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="86ae1-134">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="86ae1-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="86ae1-135">IHostPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="86ae1-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
