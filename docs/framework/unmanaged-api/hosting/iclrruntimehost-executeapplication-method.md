---
title: "ICLRRuntimeHost::ExecuteApplication 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.ExecuteApplication
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::ExecuteApplication
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteApplication method [.NET Framework hosting]
- ExecuteApplication method [.NET Framework hosting]
ms.assetid: 5f28cc4e-7176-4e00-aa1f-58ae6ee52fe4
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3b43365ad208dae5b28b31cf494de37ca670d791
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="c30d5-102">ICLRRuntimeHost::ExecuteApplication 方法</span><span class="sxs-lookup"><span data-stu-id="c30d5-102">ICLRRuntimeHost::ExecuteApplication Method</span></span>
<span data-ttu-id="c30d5-103">在基于清单的 ClickOnce 部署方案中用于指定要在新域中激活的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c30d5-103">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="c30d5-104">有关这些方案的详细信息，请参阅[ClickOnce 安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)。</span><span class="sxs-lookup"><span data-stu-id="c30d5-104">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c30d5-105">语法</span><span class="sxs-lookup"><span data-stu-id="c30d5-105">Syntax</span></span>  
  
```  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c30d5-106">参数</span><span class="sxs-lookup"><span data-stu-id="c30d5-106">Parameters</span></span>  
 `pwzAppFullName`  
 <span data-ttu-id="c30d5-107">[in]应用程序，如为定义的完整名称<xref:System.ApplicationIdentity>。</span><span class="sxs-lookup"><span data-stu-id="c30d5-107">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="c30d5-108">[in]字符串中包含的数量`ppwzManifestPaths`数组。</span><span class="sxs-lookup"><span data-stu-id="c30d5-108">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="c30d5-109">[in] 可选。</span><span class="sxs-lookup"><span data-stu-id="c30d5-109">[in] Optional.</span></span> <span data-ttu-id="c30d5-110">包含应用程序的清单路径的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="c30d5-110">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="c30d5-111">[in]字符串中包含的数量`ppwzActivationData`数组。</span><span class="sxs-lookup"><span data-stu-id="c30d5-111">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="c30d5-112">[in] 可选。</span><span class="sxs-lookup"><span data-stu-id="c30d5-112">[in] Optional.</span></span> <span data-ttu-id="c30d5-113">包含应用程序的激活数据，例如部署在 Web 应用程序的 URL 的查询字符串部分的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="c30d5-113">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="c30d5-114">[out]从应用程序的入口点返回的值。</span><span class="sxs-lookup"><span data-stu-id="c30d5-114">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c30d5-115">返回值</span><span class="sxs-lookup"><span data-stu-id="c30d5-115">Return Value</span></span>  
  
|<span data-ttu-id="c30d5-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c30d5-116">HRESULT</span></span>|<span data-ttu-id="c30d5-117">描述</span><span class="sxs-lookup"><span data-stu-id="c30d5-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c30d5-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="c30d5-118">S_OK</span></span>|<span data-ttu-id="c30d5-119">`ExecuteApplication`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="c30d5-119">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="c30d5-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c30d5-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c30d5-121">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c30d5-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c30d5-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c30d5-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c30d5-123">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="c30d5-123">The call timed out.</span></span>|  
|<span data-ttu-id="c30d5-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c30d5-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c30d5-125">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c30d5-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c30d5-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c30d5-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c30d5-127">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="c30d5-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c30d5-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c30d5-128">E_FAIL</span></span>|<span data-ttu-id="c30d5-129">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c30d5-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c30d5-130">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="c30d5-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c30d5-131">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c30d5-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c30d5-132">备注</span><span class="sxs-lookup"><span data-stu-id="c30d5-132">Remarks</span></span>  
 <span data-ttu-id="c30d5-133">`ExecuteApplication`用于激活新创建的应用程序域中的 ClickOnce 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c30d5-133">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="c30d5-134">`pReturnValue`输出参数设置为应用程序返回的值。</span><span class="sxs-lookup"><span data-stu-id="c30d5-134">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="c30d5-135">如果提供的值为 null 的`pReturnValue`，`ExecuteApplication`不会失败，但它不返回值。</span><span class="sxs-lookup"><span data-stu-id="c30d5-135">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c30d5-136">不要调用[启动方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)方法之前调用`ExecuteApplication`激活基于清单的应用程序的方法。</span><span class="sxs-lookup"><span data-stu-id="c30d5-136">Do not call the [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="c30d5-137">如果`Start`首先，调用方法`ExecuteApplication`方法调用将失败。</span><span class="sxs-lookup"><span data-stu-id="c30d5-137">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c30d5-138">要求</span><span class="sxs-lookup"><span data-stu-id="c30d5-138">Requirements</span></span>  
 <span data-ttu-id="c30d5-139">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c30d5-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c30d5-140">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c30d5-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c30d5-141">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c30d5-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c30d5-142">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c30d5-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c30d5-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c30d5-143">See Also</span></span>  
 <xref:System.ActivationContext>  
 <xref:System.AppDomainManager>  
 <xref:System.ApplicationIdentity>  
 [<span data-ttu-id="c30d5-144">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="c30d5-144">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="c30d5-145">SetAppDomainManager 方法</span><span class="sxs-lookup"><span data-stu-id="c30d5-145">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)  
 [<span data-ttu-id="c30d5-146">演练：在设计器中使用 ClickOnce 部署 API 按需下载程序集</span><span class="sxs-lookup"><span data-stu-id="c30d5-146">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
