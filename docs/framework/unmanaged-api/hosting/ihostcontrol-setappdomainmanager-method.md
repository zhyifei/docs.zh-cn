---
title: IHostControl::SetAppDomainManager 方法
ms.date: 03/30/2017
api_name:
- IHostControl.SetAppDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::SetAppDomainManager
helpviewer_keywords:
- IHostControl::SetAppDomainManager method [.NET Framework hosting]
- SetAppDomainManager method [.NET Framework hosting]
ms.assetid: 6562bbe7-0d67-4c50-a958-3a18cf680375
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb63f1e9d2b30ce764521aa68fbafe0407cbe922
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441869"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a><span data-ttu-id="e0aac-102">IHostControl::SetAppDomainManager 方法</span><span class="sxs-lookup"><span data-stu-id="e0aac-102">IHostControl::SetAppDomainManager Method</span></span>
<span data-ttu-id="e0aac-103">通知主机应用程序域已创建。</span><span class="sxs-lookup"><span data-stu-id="e0aac-103">Notifies the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0aac-104">语法</span><span class="sxs-lookup"><span data-stu-id="e0aac-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0aac-105">参数</span><span class="sxs-lookup"><span data-stu-id="e0aac-105">Parameters</span></span>  
 `dwAppDomainID`  
 <span data-ttu-id="e0aac-106">[in]所选的数字标识符<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="e0aac-106">[in] The numeric identifier of the selected <xref:System.AppDomain>.</span></span>  
  
 `pUnkAppDomainManager`  
 <span data-ttu-id="e0aac-107">[in]指向的指针<xref:System.AppDomainManager>主机实现作为对象`IUnknown`。</span><span class="sxs-lookup"><span data-stu-id="e0aac-107">[in] A pointer to the <xref:System.AppDomainManager> object that the host implements as `IUnknown`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0aac-108">返回值</span><span class="sxs-lookup"><span data-stu-id="e0aac-108">Return Value</span></span>  
  
|<span data-ttu-id="e0aac-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e0aac-109">HRESULT</span></span>|<span data-ttu-id="e0aac-110">描述</span><span class="sxs-lookup"><span data-stu-id="e0aac-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0aac-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0aac-111">S_OK</span></span>|<span data-ttu-id="e0aac-112">`SetAppDomainManager` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="e0aac-112">`SetAppDomainManager` returned successfully.</span></span>|  
|<span data-ttu-id="e0aac-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e0aac-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e0aac-114">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="e0aac-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e0aac-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e0aac-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e0aac-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="e0aac-116">The call timed out.</span></span>|  
|<span data-ttu-id="e0aac-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e0aac-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e0aac-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="e0aac-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e0aac-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e0aac-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e0aac-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="e0aac-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e0aac-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e0aac-121">E_FAIL</span></span>|<span data-ttu-id="e0aac-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="e0aac-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e0aac-123">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="e0aac-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e0aac-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="e0aac-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0aac-125">备注</span><span class="sxs-lookup"><span data-stu-id="e0aac-125">Remarks</span></span>  
 <span data-ttu-id="e0aac-126"><xref:System.AppDomainManager>为宿主提供一种机制，用于引导到托管代码和控制的创建和设置每个<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="e0aac-126">The <xref:System.AppDomainManager> provides the host with a mechanism to bootstrap into managed code and to control the creation and settings of each <xref:System.AppDomain>.</span></span> <span data-ttu-id="e0aac-127"><xref:System.AppDomainManager>将会加载到每个<xref:System.AppDomain>时，<xref:System.AppDomain>创建。</span><span class="sxs-lookup"><span data-stu-id="e0aac-127">The <xref:System.AppDomainManager> is loaded into each <xref:System.AppDomain> when that <xref:System.AppDomain> is created.</span></span> <span data-ttu-id="e0aac-128">如果选择，CLR 通知宿主已通过设置的值创建了应用程序域`pUnkAppDomainManager`参数。</span><span class="sxs-lookup"><span data-stu-id="e0aac-128">If it chooses, the CLR notifies the host that the application domain has been created by setting the value of the `pUnkAppDomainManager` parameter.</span></span>  
  
 <span data-ttu-id="e0aac-129">在其实现`SetAppDomainManager`方法，主机可以设置程序集名称和类型的应用程序域管理器。</span><span class="sxs-lookup"><span data-stu-id="e0aac-129">In its implementation of the `SetAppDomainManager` method, the host can set the assembly name and type for the application domain manager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0aac-130">要求</span><span class="sxs-lookup"><span data-stu-id="e0aac-130">Requirements</span></span>  
 <span data-ttu-id="e0aac-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e0aac-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0aac-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e0aac-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0aac-133">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e0aac-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0aac-134">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0aac-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0aac-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0aac-135">See Also</span></span>  
 <xref:System.AppDomain>  
 <xref:System.AppDomainManager>  
 [<span data-ttu-id="e0aac-136">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="e0aac-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
