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
ms.openlocfilehash: 192492c232970842270f031832d1eb46357ec07f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527167"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="00a77-102">ICLRRuntimeHost::GetCurrentAppDomainId 方法</span><span class="sxs-lookup"><span data-stu-id="00a77-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="00a77-103">获取的数字标识符<xref:System.AppDomain>当前正在执行。</span><span class="sxs-lookup"><span data-stu-id="00a77-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00a77-104">语法</span><span class="sxs-lookup"><span data-stu-id="00a77-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="00a77-105">参数</span><span class="sxs-lookup"><span data-stu-id="00a77-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="00a77-106">[out]数字标识符<xref:System.AppDomain>当前正在执行。</span><span class="sxs-lookup"><span data-stu-id="00a77-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00a77-107">返回值</span><span class="sxs-lookup"><span data-stu-id="00a77-107">Return Value</span></span>  
  
|<span data-ttu-id="00a77-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="00a77-108">HRESULT</span></span>|<span data-ttu-id="00a77-109">描述</span><span class="sxs-lookup"><span data-stu-id="00a77-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="00a77-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="00a77-110">S_OK</span></span>|<span data-ttu-id="00a77-111">`GetCurrentAppDomainId` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="00a77-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="00a77-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="00a77-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="00a77-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="00a77-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="00a77-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="00a77-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="00a77-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="00a77-115">The call timed out.</span></span>|  
|<span data-ttu-id="00a77-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="00a77-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="00a77-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="00a77-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="00a77-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="00a77-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="00a77-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="00a77-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="00a77-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="00a77-120">E_FAIL</span></span>|<span data-ttu-id="00a77-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="00a77-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="00a77-122">如果方法返回 E_FAIL，CLR 不再在该过程中可用。</span><span class="sxs-lookup"><span data-stu-id="00a77-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="00a77-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="00a77-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00a77-124">备注</span><span class="sxs-lookup"><span data-stu-id="00a77-124">Remarks</span></span>  
 <span data-ttu-id="00a77-125">`pdwAppDomainId`参数设置为的值<xref:System.AppDomain.Id%2A>属性的<xref:System.AppDomain>在其中执行当前线程。</span><span class="sxs-lookup"><span data-stu-id="00a77-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00a77-126">要求</span><span class="sxs-lookup"><span data-stu-id="00a77-126">Requirements</span></span>  
 <span data-ttu-id="00a77-127">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="00a77-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00a77-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="00a77-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="00a77-129">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="00a77-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="00a77-130">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00a77-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00a77-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="00a77-131">See also</span></span>
- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="00a77-132">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="00a77-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
