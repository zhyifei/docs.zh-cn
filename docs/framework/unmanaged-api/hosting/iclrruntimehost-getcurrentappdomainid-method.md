---
title: ICLRRuntimeHost::GetCurrentAppDomainId 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCurrentAppDomainId
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28d1655bdc3746dab87acef2e2aac6758883e74a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096207"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="8ba8a-102">ICLRRuntimeHost::GetCurrentAppDomainId 方法</span><span class="sxs-lookup"><span data-stu-id="8ba8a-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="8ba8a-103">获取的数字标识符<xref:System.AppDomain>当前正在执行。</span><span class="sxs-lookup"><span data-stu-id="8ba8a-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ba8a-104">语法</span><span class="sxs-lookup"><span data-stu-id="8ba8a-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ba8a-105">参数</span><span class="sxs-lookup"><span data-stu-id="8ba8a-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="8ba8a-106">[out]数字标识符<xref:System.AppDomain>当前正在执行。</span><span class="sxs-lookup"><span data-stu-id="8ba8a-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ba8a-107">返回值</span><span class="sxs-lookup"><span data-stu-id="8ba8a-107">Return Value</span></span>  
  
|<span data-ttu-id="8ba8a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8ba8a-108">HRESULT</span></span>|<span data-ttu-id="8ba8a-109">描述</span><span class="sxs-lookup"><span data-stu-id="8ba8a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8ba8a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ba8a-110">S_OK</span></span>|`GetCurrentAppDomainId` <span data-ttu-id="8ba8a-111">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="8ba8a-111">returned successfully.</span></span>|  
|<span data-ttu-id="8ba8a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8ba8a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8ba8a-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="8ba8a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8ba8a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8ba8a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8ba8a-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="8ba8a-115">The call timed out.</span></span>|  
|<span data-ttu-id="8ba8a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8ba8a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8ba8a-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="8ba8a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8ba8a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8ba8a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8ba8a-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="8ba8a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8ba8a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8ba8a-120">E_FAIL</span></span>|<span data-ttu-id="8ba8a-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="8ba8a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8ba8a-122">如果方法返回 E_FAIL，CLR 不再在该过程中可用。</span><span class="sxs-lookup"><span data-stu-id="8ba8a-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8ba8a-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="8ba8a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ba8a-124">备注</span><span class="sxs-lookup"><span data-stu-id="8ba8a-124">Remarks</span></span>  
 <span data-ttu-id="8ba8a-125">`pdwAppDomainId`参数设置为的值<xref:System.AppDomain.Id%2A>属性的<xref:System.AppDomain>在其中执行当前线程。</span><span class="sxs-lookup"><span data-stu-id="8ba8a-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ba8a-126">要求</span><span class="sxs-lookup"><span data-stu-id="8ba8a-126">Requirements</span></span>  
 <span data-ttu-id="8ba8a-127">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8ba8a-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ba8a-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8ba8a-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ba8a-129">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8ba8a-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8ba8a-130">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="8ba8a-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8ba8a-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ba8a-131">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="8ba8a-132">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="8ba8a-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
