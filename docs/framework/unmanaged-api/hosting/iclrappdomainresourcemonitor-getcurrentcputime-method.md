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
ms.openlocfilehash: b411190ff36410c1d293f1e48b31975be8a13aee
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616029"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="d038c-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime 方法</span><span class="sxs-lookup"><span data-stu-id="d038c-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>
<span data-ttu-id="d038c-103">获取自应用程序域创建以来在当前应用程序域中执行时所有线程已使用的总处理器时间。</span><span class="sxs-lookup"><span data-stu-id="d038c-103">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d038c-104">语法</span><span class="sxs-lookup"><span data-stu-id="d038c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d038c-105">参数</span><span class="sxs-lookup"><span data-stu-id="d038c-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="d038c-106">中请求的应用程序域的 ID。</span><span class="sxs-lookup"><span data-stu-id="d038c-106">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="d038c-107">弄一个指针，指向自创建应用程序域后，所有线程在当前应用程序域中执行时所使用的总处理器时间。</span><span class="sxs-lookup"><span data-stu-id="d038c-107">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="d038c-108">此参数可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="d038c-108">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d038c-109">返回值</span><span class="sxs-lookup"><span data-stu-id="d038c-109">Return Value</span></span>  
  
|<span data-ttu-id="d038c-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d038c-110">HRESULT</span></span>|<span data-ttu-id="d038c-111">说明</span><span class="sxs-lookup"><span data-stu-id="d038c-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d038c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d038c-112">S_OK</span></span>|<span data-ttu-id="d038c-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="d038c-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="d038c-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="d038c-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="d038c-115">应用程序域已卸载或不存在。</span><span class="sxs-lookup"><span data-stu-id="d038c-115">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="d038c-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d038c-116">E_FAIL</span></span>|<span data-ttu-id="d038c-117">未启用应用程序域资源监视。</span><span class="sxs-lookup"><span data-stu-id="d038c-117">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="d038c-118">-或-</span><span class="sxs-lookup"><span data-stu-id="d038c-118">-or-</span></span><br /><br /> <span data-ttu-id="d038c-119">所有其他失败。</span><span class="sxs-lookup"><span data-stu-id="d038c-119">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d038c-120">备注</span><span class="sxs-lookup"><span data-stu-id="d038c-120">Remarks</span></span>  
 <span data-ttu-id="d038c-121">此方法是托管属性的非托管等效项 <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="d038c-121">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d038c-122">要求</span><span class="sxs-lookup"><span data-stu-id="d038c-122">Requirements</span></span>  
 <span data-ttu-id="d038c-123">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d038c-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d038c-124">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="d038c-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d038c-125">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d038c-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d038c-126">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d038c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d038c-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d038c-127">See also</span></span>

- [<span data-ttu-id="d038c-128">ICLRAppDomainResourceMonitor 接口</span><span class="sxs-lookup"><span data-stu-id="d038c-128">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="d038c-129">承载接口</span><span class="sxs-lookup"><span data-stu-id="d038c-129">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="d038c-130">应用程序域资源监视</span><span class="sxs-lookup"><span data-stu-id="d038c-130">Application Domain Resource Monitoring</span></span>](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="d038c-131">承载</span><span class="sxs-lookup"><span data-stu-id="d038c-131">Hosting</span></span>](index.md)
