---
title: ICLRAppDomainResourceMonitor::GetCurrentCpuTime 方法
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63f5687787a9b0cdb30790b7e80e4160cdf413f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737239"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="c0bf4-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime 方法</span><span class="sxs-lookup"><span data-stu-id="c0bf4-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>
<span data-ttu-id="c0bf4-103">获取在当前的应用程序域中执行，原因是已创建的应用程序域时使用的所有线程的总处理器时间。</span><span class="sxs-lookup"><span data-stu-id="c0bf4-103">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0bf4-104">语法</span><span class="sxs-lookup"><span data-stu-id="c0bf4-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0bf4-105">参数</span><span class="sxs-lookup"><span data-stu-id="c0bf4-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="c0bf4-106">[in]请求的应用程序域的 ID。</span><span class="sxs-lookup"><span data-stu-id="c0bf4-106">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="c0bf4-107">[out]指向创建应用程序域之后，在当前应用程序域中执行时使用的所有线程的总处理器时间的指针。</span><span class="sxs-lookup"><span data-stu-id="c0bf4-107">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="c0bf4-108">此参数可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="c0bf4-108">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0bf4-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c0bf4-109">Return Value</span></span>  
  
|<span data-ttu-id="c0bf4-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c0bf4-110">HRESULT</span></span>|<span data-ttu-id="c0bf4-111">描述</span><span class="sxs-lookup"><span data-stu-id="c0bf4-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c0bf4-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c0bf4-112">S_OK</span></span>|<span data-ttu-id="c0bf4-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="c0bf4-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="c0bf4-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="c0bf4-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="c0bf4-115">应用程序域已被卸载，或不存在。</span><span class="sxs-lookup"><span data-stu-id="c0bf4-115">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="c0bf4-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c0bf4-116">E_FAIL</span></span>|<span data-ttu-id="c0bf4-117">未启用应用程序域资源监视。</span><span class="sxs-lookup"><span data-stu-id="c0bf4-117">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="c0bf4-118">或</span><span class="sxs-lookup"><span data-stu-id="c0bf4-118">-or-</span></span><br /><br /> <span data-ttu-id="c0bf4-119">所有其他失败。</span><span class="sxs-lookup"><span data-stu-id="c0bf4-119">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0bf4-120">备注</span><span class="sxs-lookup"><span data-stu-id="c0bf4-120">Remarks</span></span>  
 <span data-ttu-id="c0bf4-121">此方法相当于非托管的托管<xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="c0bf4-121">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0bf4-122">要求</span><span class="sxs-lookup"><span data-stu-id="c0bf4-122">Requirements</span></span>  
 <span data-ttu-id="c0bf4-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c0bf4-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0bf4-124">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c0bf4-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c0bf4-125">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c0bf4-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0bf4-126">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0bf4-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0bf4-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0bf4-127">See also</span></span>
- [<span data-ttu-id="c0bf4-128">ICLRAppDomainResourceMonitor 接口</span><span class="sxs-lookup"><span data-stu-id="c0bf4-128">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="c0bf4-129">承载接口</span><span class="sxs-lookup"><span data-stu-id="c0bf4-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="c0bf4-130">应用程序域资源监视</span><span class="sxs-lookup"><span data-stu-id="c0bf4-130">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="c0bf4-131">承载</span><span class="sxs-lookup"><span data-stu-id="c0bf4-131">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
