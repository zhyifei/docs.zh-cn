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
ms.openlocfilehash: 1b7d321eec2bbc2beb47c5de034bb4ef5d534c9d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120467"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="a24d4-102">ICLRRuntimeHost::GetCurrentAppDomainId 方法</span><span class="sxs-lookup"><span data-stu-id="a24d4-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="a24d4-103">获取当前正在执行的 <xref:System.AppDomain> 的数值标识符。</span><span class="sxs-lookup"><span data-stu-id="a24d4-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a24d4-104">语法</span><span class="sxs-lookup"><span data-stu-id="a24d4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a24d4-105">参数</span><span class="sxs-lookup"><span data-stu-id="a24d4-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="a24d4-106">弄当前正在执行的 <xref:System.AppDomain> 的数值标识符。</span><span class="sxs-lookup"><span data-stu-id="a24d4-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a24d4-107">返回值</span><span class="sxs-lookup"><span data-stu-id="a24d4-107">Return Value</span></span>  
  
|<span data-ttu-id="a24d4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a24d4-108">HRESULT</span></span>|<span data-ttu-id="a24d4-109">描述</span><span class="sxs-lookup"><span data-stu-id="a24d4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a24d4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a24d4-110">S_OK</span></span>|<span data-ttu-id="a24d4-111">`GetCurrentAppDomainId` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="a24d4-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="a24d4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a24d4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a24d4-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="a24d4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a24d4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a24d4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a24d4-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="a24d4-115">The call timed out.</span></span>|  
|<span data-ttu-id="a24d4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a24d4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a24d4-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="a24d4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a24d4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a24d4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a24d4-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="a24d4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a24d4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a24d4-120">E_FAIL</span></span>|<span data-ttu-id="a24d4-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="a24d4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a24d4-122">如果某个方法返回 E_FAIL，则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="a24d4-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a24d4-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="a24d4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a24d4-124">备注</span><span class="sxs-lookup"><span data-stu-id="a24d4-124">Remarks</span></span>  
 <span data-ttu-id="a24d4-125">`pdwAppDomainId` 参数设置为当前线程正在其中执行的 <xref:System.AppDomain> 的 <xref:System.AppDomain.Id%2A> 属性的值。</span><span class="sxs-lookup"><span data-stu-id="a24d4-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a24d4-126">要求</span><span class="sxs-lookup"><span data-stu-id="a24d4-126">Requirements</span></span>  
 <span data-ttu-id="a24d4-127">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a24d4-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a24d4-128">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a24d4-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a24d4-129">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="a24d4-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a24d4-130">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a24d4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a24d4-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="a24d4-131">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="a24d4-132">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="a24d4-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
