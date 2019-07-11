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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cfd7c835cdc4b53c753d714216d1745eb0b80c2d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772928"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="1ef85-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="1ef85-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>
<span data-ttu-id="1ef85-103">设置将用来初始化默认应用程序域的属性。</span><span class="sxs-lookup"><span data-stu-id="1ef85-103">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ef85-104">语法</span><span class="sxs-lookup"><span data-stu-id="1ef85-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ef85-105">参数</span><span class="sxs-lookup"><span data-stu-id="1ef85-105">Parameters</span></span>  
 `nProperties`  
 <span data-ttu-id="1ef85-106">[in]中的条目数`pwszPropertyNames`和`pwszPropertyValues`。</span><span class="sxs-lookup"><span data-stu-id="1ef85-106">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="1ef85-107">[in]属性名称或如果没有属性，则为 null 的数组。</span><span class="sxs-lookup"><span data-stu-id="1ef85-107">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="1ef85-108">目前，此方法识别的唯一属性名称为"PARTIAL_TRUST_VISIBLE_ASSEMBLIES"。</span><span class="sxs-lookup"><span data-stu-id="1ef85-108">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="1ef85-109">[in]属性值或如果没有属性，则为 null 的数组。</span><span class="sxs-lookup"><span data-stu-id="1ef85-109">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ef85-110">返回值</span><span class="sxs-lookup"><span data-stu-id="1ef85-110">Return Value</span></span>  
 <span data-ttu-id="1ef85-111">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="1ef85-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1ef85-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1ef85-112">HRESULT</span></span>|<span data-ttu-id="1ef85-113">描述</span><span class="sxs-lookup"><span data-stu-id="1ef85-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1ef85-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="1ef85-114">S_OK</span></span>|<span data-ttu-id="1ef85-115">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="1ef85-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="1ef85-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span><span class="sxs-lookup"><span data-stu-id="1ef85-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|<span data-ttu-id="1ef85-117">`pwszPropertyNames` 包括此方法无法识别的属性名称。</span><span class="sxs-lookup"><span data-stu-id="1ef85-117">`pwszPropertyNames` includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ef85-118">备注</span><span class="sxs-lookup"><span data-stu-id="1ef85-118">Remarks</span></span>  
 <span data-ttu-id="1ef85-119">"PARTIAL_TRUST_VISIBLE_ASSEMBLIES"的属性值是具有条件性的程序集的列表<xref:System.Security.AllowPartiallyTrustedCallersAttribute>与 (APTCA) 特性<xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType>标志，但这是在默认应用程序中进行部分受信任调用方对可见域。</span><span class="sxs-lookup"><span data-stu-id="1ef85-119">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ef85-120">要求</span><span class="sxs-lookup"><span data-stu-id="1ef85-120">Requirements</span></span>  
 <span data-ttu-id="1ef85-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1ef85-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ef85-122">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="1ef85-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1ef85-123">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1ef85-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1ef85-124">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ef85-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ef85-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ef85-125">See also</span></span>

- [<span data-ttu-id="1ef85-126">承载</span><span class="sxs-lookup"><span data-stu-id="1ef85-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="1ef85-127">ICLRDomainManager 接口</span><span class="sxs-lookup"><span data-stu-id="1ef85-127">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
