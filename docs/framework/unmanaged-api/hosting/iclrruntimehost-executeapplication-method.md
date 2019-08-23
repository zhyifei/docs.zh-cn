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
ms.openlocfilehash: 38938de335e5f0d7cb8051554c400f16df012362
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965358"
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="8a041-102">ICLRRuntimeHost::ExecuteApplication 方法</span><span class="sxs-lookup"><span data-stu-id="8a041-102">ICLRRuntimeHost::ExecuteApplication Method</span></span>
<span data-ttu-id="8a041-103">在基于清单的 ClickOnce 部署方案中用于指定要在新域中激活的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8a041-103">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="8a041-104">有关这些方案的详细信息, 请参阅[ClickOnce 安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)。</span><span class="sxs-lookup"><span data-stu-id="8a041-104">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a041-105">语法</span><span class="sxs-lookup"><span data-stu-id="8a041-105">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a041-106">参数</span><span class="sxs-lookup"><span data-stu-id="8a041-106">Parameters</span></span>  
 `pwzAppFullName`  
 <span data-ttu-id="8a041-107">中为定义<xref:System.ApplicationIdentity>的应用程序的完整名称。</span><span class="sxs-lookup"><span data-stu-id="8a041-107">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="8a041-108">中`ppwzManifestPaths`数组中包含的字符串的数目。</span><span class="sxs-lookup"><span data-stu-id="8a041-108">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="8a041-109">[in] 可选。</span><span class="sxs-lookup"><span data-stu-id="8a041-109">[in] Optional.</span></span> <span data-ttu-id="8a041-110">包含应用程序的清单路径的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="8a041-110">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="8a041-111">中`ppwzActivationData`数组中包含的字符串的数目。</span><span class="sxs-lookup"><span data-stu-id="8a041-111">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="8a041-112">[in] 可选。</span><span class="sxs-lookup"><span data-stu-id="8a041-112">[in] Optional.</span></span> <span data-ttu-id="8a041-113">一个字符串数组, 其中包含应用程序的激活数据, 如通过 Web 部署的应用程序的 URL 的查询字符串部分。</span><span class="sxs-lookup"><span data-stu-id="8a041-113">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="8a041-114">弄从应用程序的入口点返回的值。</span><span class="sxs-lookup"><span data-stu-id="8a041-114">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a041-115">返回值</span><span class="sxs-lookup"><span data-stu-id="8a041-115">Return Value</span></span>  
  
|<span data-ttu-id="8a041-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a041-116">HRESULT</span></span>|<span data-ttu-id="8a041-117">描述</span><span class="sxs-lookup"><span data-stu-id="8a041-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8a041-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="8a041-118">S_OK</span></span>|<span data-ttu-id="8a041-119">`ExecuteApplication`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="8a041-119">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="8a041-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8a041-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8a041-121">公共语言运行时 (CLR) 未加载到进程中, 或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="8a041-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8a041-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8a041-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8a041-123">调用超时。</span><span class="sxs-lookup"><span data-stu-id="8a041-123">The call timed out.</span></span>|  
|<span data-ttu-id="8a041-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8a041-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8a041-125">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="8a041-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8a041-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8a041-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8a041-127">已阻止的线程或纤程正在等待某个事件时, 该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="8a041-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8a041-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8a041-128">E_FAIL</span></span>|<span data-ttu-id="8a041-129">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="8a041-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8a041-130">如果某个方法返回 E_FAIL, 则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="8a041-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8a041-131">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="8a041-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a041-132">备注</span><span class="sxs-lookup"><span data-stu-id="8a041-132">Remarks</span></span>  
 <span data-ttu-id="8a041-133">`ExecuteApplication`用于在新创建的应用程序域中激活 ClickOnce 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8a041-133">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="8a041-134">`pReturnValue` Output 参数设置为应用程序返回的值。</span><span class="sxs-lookup"><span data-stu-id="8a041-134">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="8a041-135">如果为`pReturnValue`提供 null 值, `ExecuteApplication`则不会失败, 但它不返回值。</span><span class="sxs-lookup"><span data-stu-id="8a041-135">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8a041-136">请不要在调用`ExecuteApplication`方法之前调用[Start 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)方法来激活基于清单的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8a041-136">Do not call the [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="8a041-137">如果首先调用`ExecuteApplication`方法,方法调用将失败。 `Start`</span><span class="sxs-lookup"><span data-stu-id="8a041-137">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a041-138">要求</span><span class="sxs-lookup"><span data-stu-id="8a041-138">Requirements</span></span>  
 <span data-ttu-id="8a041-139">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8a041-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a041-140">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8a041-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a041-141">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8a041-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a041-142">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a041-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a041-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a041-143">See also</span></span>

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [<span data-ttu-id="8a041-144">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="8a041-144">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="8a041-145">SetAppDomainManager 方法</span><span class="sxs-lookup"><span data-stu-id="8a041-145">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)
- [<span data-ttu-id="8a041-146">演练：在设计器中使用 ClickOnce 部署 API 按需下载程序集</span><span class="sxs-lookup"><span data-stu-id="8a041-146">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
