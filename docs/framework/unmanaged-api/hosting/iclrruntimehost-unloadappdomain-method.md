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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641354"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="2da5a-102">ICLRRuntimeHost::UnloadAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="2da5a-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>
<span data-ttu-id="2da5a-103">卸载托管<xref:System.AppDomain>对应于指定的数字标识符。</span><span class="sxs-lookup"><span data-stu-id="2da5a-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2da5a-104">语法</span><span class="sxs-lookup"><span data-stu-id="2da5a-104">Syntax</span></span>  
  
```  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2da5a-105">参数</span><span class="sxs-lookup"><span data-stu-id="2da5a-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="2da5a-106">[in]要卸载的应用程序域的数字标识符。</span><span class="sxs-lookup"><span data-stu-id="2da5a-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="2da5a-107">[in]`true`以指示公共语言运行时 (CLR) 必须等待其完成之前尝试卸载应用程序域中执行应用程序的当前线程。</span><span class="sxs-lookup"><span data-stu-id="2da5a-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2da5a-108">返回值</span><span class="sxs-lookup"><span data-stu-id="2da5a-108">Return Value</span></span>  
  
|<span data-ttu-id="2da5a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2da5a-109">HRESULT</span></span>|<span data-ttu-id="2da5a-110">描述</span><span class="sxs-lookup"><span data-stu-id="2da5a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2da5a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2da5a-111">S_OK</span></span>|<span data-ttu-id="2da5a-112">`UnloadAppDomain` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="2da5a-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="2da5a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2da5a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2da5a-114">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="2da5a-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2da5a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2da5a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2da5a-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="2da5a-116">The call timed out.</span></span>|  
|<span data-ttu-id="2da5a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2da5a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2da5a-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="2da5a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2da5a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2da5a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2da5a-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="2da5a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2da5a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2da5a-121">E_FAIL</span></span>|<span data-ttu-id="2da5a-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="2da5a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2da5a-123">如果方法返回 E_FAIL，CLR 不再在该过程中可用。</span><span class="sxs-lookup"><span data-stu-id="2da5a-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2da5a-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="2da5a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2da5a-125">备注</span><span class="sxs-lookup"><span data-stu-id="2da5a-125">Remarks</span></span>  
 <span data-ttu-id="2da5a-126">可以获取在其中通过调用执行当前线程的应用程序域的数字标识符[GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)。</span><span class="sxs-lookup"><span data-stu-id="2da5a-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="2da5a-127">此标识符对应于<xref:System.AppDomain.Id%2A>的托管属性<xref:System.AppDomain>类型。</span><span class="sxs-lookup"><span data-stu-id="2da5a-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2da5a-128">要求</span><span class="sxs-lookup"><span data-stu-id="2da5a-128">Requirements</span></span>  
 <span data-ttu-id="2da5a-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2da5a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2da5a-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2da5a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2da5a-131">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2da5a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2da5a-132">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2da5a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2da5a-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="2da5a-133">See also</span></span>

- [<span data-ttu-id="2da5a-134">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="2da5a-134">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
