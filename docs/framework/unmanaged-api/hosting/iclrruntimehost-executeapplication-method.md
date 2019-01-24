---
title: ICLRRuntimeHost::ExecuteApplication 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteApplication
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteApplication
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteApplication method [.NET Framework hosting]
- ExecuteApplication method [.NET Framework hosting]
ms.assetid: 5f28cc4e-7176-4e00-aa1f-58ae6ee52fe4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a68c210c8c87597e2f3e664ff67ff4ba3557323d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656357"
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="e6d06-102">ICLRRuntimeHost::ExecuteApplication 方法</span><span class="sxs-lookup"><span data-stu-id="e6d06-102">ICLRRuntimeHost::ExecuteApplication Method</span></span>
<span data-ttu-id="e6d06-103">基于清单的 ClickOnce 部署方案中使用，以指定要在新域中激活的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e6d06-103">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="e6d06-104">有关这些方案的详细信息，请参阅[ClickOnce 安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)。</span><span class="sxs-lookup"><span data-stu-id="e6d06-104">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6d06-105">语法</span><span class="sxs-lookup"><span data-stu-id="e6d06-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="e6d06-106">参数</span><span class="sxs-lookup"><span data-stu-id="e6d06-106">Parameters</span></span>  
 `pwzAppFullName`  
 <span data-ttu-id="e6d06-107">[in]应用程序，如为定义的完整名称<xref:System.ApplicationIdentity>。</span><span class="sxs-lookup"><span data-stu-id="e6d06-107">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="e6d06-108">[in]中包含的字符串数目`ppwzManifestPaths`数组。</span><span class="sxs-lookup"><span data-stu-id="e6d06-108">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="e6d06-109">[in] 可选。</span><span class="sxs-lookup"><span data-stu-id="e6d06-109">[in] Optional.</span></span> <span data-ttu-id="e6d06-110">包含应用程序的清单路径的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="e6d06-110">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="e6d06-111">[in]中包含的字符串数目`ppwzActivationData`数组。</span><span class="sxs-lookup"><span data-stu-id="e6d06-111">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="e6d06-112">[in] 可选。</span><span class="sxs-lookup"><span data-stu-id="e6d06-112">[in] Optional.</span></span> <span data-ttu-id="e6d06-113">一个字符串数组，包含应用程序的激活数据，如在 Web 上的部署的应用程序的 URL 的查询字符串部分。</span><span class="sxs-lookup"><span data-stu-id="e6d06-113">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="e6d06-114">[out]从应用程序的入口点返回的值。</span><span class="sxs-lookup"><span data-stu-id="e6d06-114">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6d06-115">返回值</span><span class="sxs-lookup"><span data-stu-id="e6d06-115">Return Value</span></span>  
  
|<span data-ttu-id="e6d06-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e6d06-116">HRESULT</span></span>|<span data-ttu-id="e6d06-117">描述</span><span class="sxs-lookup"><span data-stu-id="e6d06-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e6d06-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="e6d06-118">S_OK</span></span>|<span data-ttu-id="e6d06-119">`ExecuteApplication` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="e6d06-119">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="e6d06-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e6d06-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e6d06-121">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="e6d06-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e6d06-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e6d06-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e6d06-123">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="e6d06-123">The call timed out.</span></span>|  
|<span data-ttu-id="e6d06-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e6d06-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e6d06-125">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="e6d06-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e6d06-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e6d06-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e6d06-127">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="e6d06-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e6d06-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e6d06-128">E_FAIL</span></span>|<span data-ttu-id="e6d06-129">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="e6d06-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e6d06-130">如果方法返回 E_FAIL，CLR 不再在该过程中可用。</span><span class="sxs-lookup"><span data-stu-id="e6d06-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e6d06-131">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="e6d06-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6d06-132">备注</span><span class="sxs-lookup"><span data-stu-id="e6d06-132">Remarks</span></span>  
 <span data-ttu-id="e6d06-133">`ExecuteApplication` 用来激活新创建的应用程序域中的 ClickOnce 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e6d06-133">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="e6d06-134">`pReturnValue`输出参数设置为应用程序返回的值。</span><span class="sxs-lookup"><span data-stu-id="e6d06-134">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="e6d06-135">如果提供的值为 null 的`pReturnValue`，`ExecuteApplication`未失败，但它不返回值。</span><span class="sxs-lookup"><span data-stu-id="e6d06-135">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e6d06-136">不要调用[启动方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)方法之前调用`ExecuteApplication`方法，以激活基于清单的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e6d06-136">Do not call the [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="e6d06-137">如果`Start`首先，调用方法`ExecuteApplication`方法调用将失败。</span><span class="sxs-lookup"><span data-stu-id="e6d06-137">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6d06-138">要求</span><span class="sxs-lookup"><span data-stu-id="e6d06-138">Requirements</span></span>  
 <span data-ttu-id="e6d06-139">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e6d06-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6d06-140">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e6d06-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6d06-141">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e6d06-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6d06-142">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6d06-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d06-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6d06-143">See also</span></span>
- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [<span data-ttu-id="e6d06-144">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="e6d06-144">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="e6d06-145">SetAppDomainManager 方法</span><span class="sxs-lookup"><span data-stu-id="e6d06-145">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)
- [<span data-ttu-id="e6d06-146">演练：在设计器中使用 ClickOnce 部署 API 按需下载程序集</span><span class="sxs-lookup"><span data-stu-id="e6d06-146">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
