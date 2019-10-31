---
title: ICLRDomainManager::SetPropertiesForDefaultAppDomain 方法
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
ms.openlocfilehash: 37919be2d0ebd7d243615bc5845b0781ac13e574
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129314"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="add3e-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="add3e-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>
<span data-ttu-id="add3e-103">设置将用于初始化默认应用程序域的属性。</span><span class="sxs-lookup"><span data-stu-id="add3e-103">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="add3e-104">语法</span><span class="sxs-lookup"><span data-stu-id="add3e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="add3e-105">参数</span><span class="sxs-lookup"><span data-stu-id="add3e-105">Parameters</span></span>  
 `nProperties`  
 <span data-ttu-id="add3e-106">中`pwszPropertyNames` 和 `pwszPropertyValues`中的条目数。</span><span class="sxs-lookup"><span data-stu-id="add3e-106">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="add3e-107">中属性名称的数组; 如果没有属性，则为 null。</span><span class="sxs-lookup"><span data-stu-id="add3e-107">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="add3e-108">目前，此方法识别的唯一属性名称为 "PARTIAL_TRUST_VISIBLE_ASSEMBLIES"。</span><span class="sxs-lookup"><span data-stu-id="add3e-108">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="add3e-109">中属性值的数组; 如果没有属性，则为 null。</span><span class="sxs-lookup"><span data-stu-id="add3e-109">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="add3e-110">返回值</span><span class="sxs-lookup"><span data-stu-id="add3e-110">Return Value</span></span>  
 <span data-ttu-id="add3e-111">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="add3e-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="add3e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="add3e-112">HRESULT</span></span>|<span data-ttu-id="add3e-113">描述</span><span class="sxs-lookup"><span data-stu-id="add3e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="add3e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="add3e-114">S_OK</span></span>|<span data-ttu-id="add3e-115">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="add3e-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="add3e-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span><span class="sxs-lookup"><span data-stu-id="add3e-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|<span data-ttu-id="add3e-117">`pwszPropertyNames` 包含此方法无法识别的属性名称。</span><span class="sxs-lookup"><span data-stu-id="add3e-117">`pwszPropertyNames` includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="add3e-118">备注</span><span class="sxs-lookup"><span data-stu-id="add3e-118">Remarks</span></span>  
 <span data-ttu-id="add3e-119">"PARTIAL_TRUST_VISIBLE_ASSEMBLIES" 的属性值是一个程序集列表，其中包含具有 <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> 标志的条件 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> （APTCA）特性，在默认应用程序域中对部分受信任的调用方可见。</span><span class="sxs-lookup"><span data-stu-id="add3e-119">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="add3e-120">要求</span><span class="sxs-lookup"><span data-stu-id="add3e-120">Requirements</span></span>  
 <span data-ttu-id="add3e-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="add3e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="add3e-122">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="add3e-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="add3e-123">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="add3e-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="add3e-124">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="add3e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="add3e-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="add3e-125">See also</span></span>

- [<span data-ttu-id="add3e-126">承载</span><span class="sxs-lookup"><span data-stu-id="add3e-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="add3e-127">ICLRDomainManager 接口</span><span class="sxs-lookup"><span data-stu-id="add3e-127">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
