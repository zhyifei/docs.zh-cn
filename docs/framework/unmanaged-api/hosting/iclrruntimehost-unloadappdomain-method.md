---
title: ICLRRuntimeHost::UnloadAppDomain 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.UnloadAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::UnloadAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::UnloadAppDomain method [.NET Framework hosting]
- UnloadAppDomain method [.NET Framework hosting]
ms.assetid: 571912bc-3429-4ff8-8eb2-ea993ffbd901
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 490af9ca67b538e0093115a6b371b65d9788772f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222960"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="62786-102">ICLRRuntimeHost::UnloadAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="62786-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>
<span data-ttu-id="62786-103">卸载托管<xref:System.AppDomain>对应于指定的数字标识符。</span><span class="sxs-lookup"><span data-stu-id="62786-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62786-104">语法</span><span class="sxs-lookup"><span data-stu-id="62786-104">Syntax</span></span>  
  
```  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62786-105">参数</span><span class="sxs-lookup"><span data-stu-id="62786-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="62786-106">[in]要卸载的应用程序域的数字标识符。</span><span class="sxs-lookup"><span data-stu-id="62786-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="62786-107">[in]`true`以指示公共语言运行时 (CLR) 必须等待其完成之前尝试卸载应用程序域中执行应用程序的当前线程。</span><span class="sxs-lookup"><span data-stu-id="62786-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62786-108">返回值</span><span class="sxs-lookup"><span data-stu-id="62786-108">Return Value</span></span>  
  
|<span data-ttu-id="62786-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="62786-109">HRESULT</span></span>|<span data-ttu-id="62786-110">描述</span><span class="sxs-lookup"><span data-stu-id="62786-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="62786-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="62786-111">S_OK</span></span>|`UnloadAppDomain` <span data-ttu-id="62786-112">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="62786-112">returned successfully.</span></span>|  
|<span data-ttu-id="62786-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="62786-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="62786-114">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="62786-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="62786-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="62786-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="62786-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="62786-116">The call timed out.</span></span>|  
|<span data-ttu-id="62786-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="62786-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="62786-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="62786-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="62786-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="62786-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="62786-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="62786-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="62786-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="62786-121">E_FAIL</span></span>|<span data-ttu-id="62786-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="62786-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="62786-123">如果方法返回 E_FAIL，CLR 不再在该过程中可用。</span><span class="sxs-lookup"><span data-stu-id="62786-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="62786-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="62786-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62786-125">备注</span><span class="sxs-lookup"><span data-stu-id="62786-125">Remarks</span></span>  
 <span data-ttu-id="62786-126">可以获取在其中通过调用执行当前线程的应用程序域的数字标识符[GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)。</span><span class="sxs-lookup"><span data-stu-id="62786-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="62786-127">此标识符对应于<xref:System.AppDomain.Id%2A>的托管属性<xref:System.AppDomain>类型。</span><span class="sxs-lookup"><span data-stu-id="62786-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62786-128">要求</span><span class="sxs-lookup"><span data-stu-id="62786-128">Requirements</span></span>  
 <span data-ttu-id="62786-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="62786-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62786-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="62786-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62786-131">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="62786-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="62786-132">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="62786-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="62786-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="62786-133">See also</span></span>

- [<span data-ttu-id="62786-134">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="62786-134">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
