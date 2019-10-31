---
title: ICLRHostProtectionManager::SetProtectedCategories 方法
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetProtectedCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type:
- apiref
ms.openlocfilehash: e3f2429462b4454e87690d98ad9fb446574add91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141034"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="1aea7-102">ICLRHostProtectionManager::SetProtectedCategories 方法</span><span class="sxs-lookup"><span data-stu-id="1aea7-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>
<span data-ttu-id="1aea7-103">指定应阻止在部分受信任代码中运行的托管类型和成员的类别。</span><span class="sxs-lookup"><span data-stu-id="1aea7-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aea7-104">语法</span><span class="sxs-lookup"><span data-stu-id="1aea7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1aea7-105">参数</span><span class="sxs-lookup"><span data-stu-id="1aea7-105">Parameters</span></span>  
 `categories`  
 <span data-ttu-id="1aea7-106">中[EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)值的组合，指示应阻止托管类型和成员的哪些类别在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="1aea7-106">[in] A combination of [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1aea7-107">返回值</span><span class="sxs-lookup"><span data-stu-id="1aea7-107">Return Value</span></span>  
  
|<span data-ttu-id="1aea7-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1aea7-108">HRESULT</span></span>|<span data-ttu-id="1aea7-109">描述</span><span class="sxs-lookup"><span data-stu-id="1aea7-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1aea7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1aea7-110">S_OK</span></span>|<span data-ttu-id="1aea7-111">`SetProtectedCategories` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="1aea7-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="1aea7-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1aea7-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1aea7-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="1aea7-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1aea7-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1aea7-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1aea7-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="1aea7-115">The call timed out.</span></span>|  
|<span data-ttu-id="1aea7-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1aea7-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1aea7-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="1aea7-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1aea7-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1aea7-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1aea7-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="1aea7-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1aea7-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1aea7-120">E_FAIL</span></span>|<span data-ttu-id="1aea7-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="1aea7-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1aea7-122">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="1aea7-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1aea7-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="1aea7-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1aea7-124">备注</span><span class="sxs-lookup"><span data-stu-id="1aea7-124">Remarks</span></span>  
 <span data-ttu-id="1aea7-125">每个 `EApiCategories` 值都是指托管类型和成员的列表。</span><span class="sxs-lookup"><span data-stu-id="1aea7-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="1aea7-126">`EApiCategories` 枚举和 `SetProtectedCategories` 方法与托管 <xref:System.Security.Permissions.HostProtectionAttribute> 类直接相关，该类用于标记公开与 `EApiCategories`所述的类别对应的功能的托管类型和成员。</span><span class="sxs-lookup"><span data-stu-id="1aea7-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="1aea7-127">有关详细信息，请参阅 <xref:System.Security.Permissions.HostProtectionAttribute> 和 <xref:System.Security.Permissions.HostProtectionResource> 枚举，这与 `EApiCategories`直接对应。</span><span class="sxs-lookup"><span data-stu-id="1aea7-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1aea7-128">要求</span><span class="sxs-lookup"><span data-stu-id="1aea7-128">Requirements</span></span>  
 <span data-ttu-id="1aea7-129">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1aea7-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1aea7-130">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1aea7-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1aea7-131">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="1aea7-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1aea7-132">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1aea7-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aea7-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="1aea7-133">See also</span></span>

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [<span data-ttu-id="1aea7-134">EApiCategories 枚举</span><span class="sxs-lookup"><span data-stu-id="1aea7-134">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="1aea7-135">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="1aea7-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="1aea7-136">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="1aea7-136">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
