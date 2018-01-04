---
title: "ICLRHostProtectionManager::SetProtectedCategories 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostProtectionManager.SetProtectedCategories
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0971e93f02420966d6561c5b7d4dce8b75e222fb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="6d23d-102">ICLRHostProtectionManager::SetProtectedCategories 方法</span><span class="sxs-lookup"><span data-stu-id="6d23d-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>
<span data-ttu-id="6d23d-103">指定的托管的类型和成员的类别应禁止在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="6d23d-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d23d-104">语法</span><span class="sxs-lookup"><span data-stu-id="6d23d-104">Syntax</span></span>  
  
```  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d23d-105">参数</span><span class="sxs-lookup"><span data-stu-id="6d23d-105">Parameters</span></span>  
 `categories`  
 <span data-ttu-id="6d23d-106">[in]组合[EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)值，指示哪些类别的托管的类型和成员应禁止在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="6d23d-106">[in] A combination of [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d23d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="6d23d-107">Return Value</span></span>  
  
|<span data-ttu-id="6d23d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6d23d-108">HRESULT</span></span>|<span data-ttu-id="6d23d-109">描述</span><span class="sxs-lookup"><span data-stu-id="6d23d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6d23d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6d23d-110">S_OK</span></span>|<span data-ttu-id="6d23d-111">`SetProtectedCategories`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="6d23d-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="6d23d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6d23d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6d23d-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="6d23d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6d23d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6d23d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6d23d-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="6d23d-115">The call timed out.</span></span>|  
|<span data-ttu-id="6d23d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6d23d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6d23d-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="6d23d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6d23d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6d23d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6d23d-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="6d23d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6d23d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6d23d-120">E_FAIL</span></span>|<span data-ttu-id="6d23d-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="6d23d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6d23d-122">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="6d23d-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6d23d-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="6d23d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d23d-124">备注</span><span class="sxs-lookup"><span data-stu-id="6d23d-124">Remarks</span></span>  
 <span data-ttu-id="6d23d-125">每个`EApiCategories`值参考了托管的类型和成员的列表。</span><span class="sxs-lookup"><span data-stu-id="6d23d-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="6d23d-126">`EApiCategories`枚举和`SetProtectedCategories`方法直接相关于托管<xref:System.Security.Permissions.HostProtectionAttribute>类，用于将标记公开对应于所描述的类别的功能的托管的类型和成员`EApiCategories`。</span><span class="sxs-lookup"><span data-stu-id="6d23d-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="6d23d-127">有关详细信息，请参阅<xref:System.Security.Permissions.HostProtectionAttribute>和<xref:System.Security.Permissions.HostProtectionResource>枚举，直接对应于`EApiCategories`。</span><span class="sxs-lookup"><span data-stu-id="6d23d-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d23d-128">惠?</span><span class="sxs-lookup"><span data-stu-id="6d23d-128">Requirements</span></span>  
 <span data-ttu-id="6d23d-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6d23d-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d23d-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6d23d-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6d23d-131">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6d23d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d23d-132">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d23d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d23d-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d23d-133">See Also</span></span>  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
 <xref:System.Security.Permissions.HostProtectionResource>  
 [<span data-ttu-id="6d23d-134">EApiCategories 枚举</span><span class="sxs-lookup"><span data-stu-id="6d23d-134">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 [<span data-ttu-id="6d23d-135">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="6d23d-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="6d23d-136">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="6d23d-136">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
