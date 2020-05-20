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
ms.openlocfilehash: 5cf6f942add3d090cf830e71a545b9f4d4f69f00
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703173"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="8e392-102">ICLRHostProtectionManager::SetProtectedCategories 方法</span><span class="sxs-lookup"><span data-stu-id="8e392-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>
<span data-ttu-id="8e392-103">指定应阻止在部分受信任代码中运行的托管类型和成员的类别。</span><span class="sxs-lookup"><span data-stu-id="8e392-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e392-104">语法</span><span class="sxs-lookup"><span data-stu-id="8e392-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e392-105">参数</span><span class="sxs-lookup"><span data-stu-id="8e392-105">Parameters</span></span>  
 `categories`  
 <span data-ttu-id="8e392-106">中[EApiCategories](eapicategories-enumeration.md)值的组合，指示应阻止托管类型和成员的哪些类别在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="8e392-106">[in] A combination of [EApiCategories](eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e392-107">返回值</span><span class="sxs-lookup"><span data-stu-id="8e392-107">Return Value</span></span>  
  
|<span data-ttu-id="8e392-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8e392-108">HRESULT</span></span>|<span data-ttu-id="8e392-109">说明</span><span class="sxs-lookup"><span data-stu-id="8e392-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8e392-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e392-110">S_OK</span></span>|<span data-ttu-id="8e392-111">`SetProtectedCategories`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="8e392-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="8e392-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8e392-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8e392-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="8e392-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8e392-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8e392-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8e392-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="8e392-115">The call timed out.</span></span>|  
|<span data-ttu-id="8e392-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8e392-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8e392-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="8e392-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8e392-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8e392-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8e392-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="8e392-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8e392-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8e392-120">E_FAIL</span></span>|<span data-ttu-id="8e392-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="8e392-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8e392-122">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="8e392-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8e392-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="8e392-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e392-124">备注</span><span class="sxs-lookup"><span data-stu-id="8e392-124">Remarks</span></span>  
 <span data-ttu-id="8e392-125">每个 `EApiCategories` 值都是指托管类型和成员的列表。</span><span class="sxs-lookup"><span data-stu-id="8e392-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="8e392-126">`EApiCategories`枚举和方法与 `SetProtectedCategories` 托管类直接相关 <xref:System.Security.Permissions.HostProtectionAttribute> ，后者用于标记公开与所述的类别对应的功能的托管类型和成员 `EApiCategories` 。</span><span class="sxs-lookup"><span data-stu-id="8e392-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="8e392-127">有关详细信息，请参阅 <xref:System.Security.Permissions.HostProtectionAttribute> 和 <xref:System.Security.Permissions.HostProtectionResource> 枚举，后者直接对应于 `EApiCategories` 。</span><span class="sxs-lookup"><span data-stu-id="8e392-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e392-128">要求</span><span class="sxs-lookup"><span data-stu-id="8e392-128">Requirements</span></span>  
 <span data-ttu-id="8e392-129">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8e392-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e392-130">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8e392-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e392-131">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8e392-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e392-132">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e392-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e392-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e392-133">See also</span></span>

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [<span data-ttu-id="8e392-134">EApiCategories 枚举</span><span class="sxs-lookup"><span data-stu-id="8e392-134">EApiCategories Enumeration</span></span>](eapicategories-enumeration.md)
- [<span data-ttu-id="8e392-135">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="8e392-135">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="8e392-136">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="8e392-136">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
