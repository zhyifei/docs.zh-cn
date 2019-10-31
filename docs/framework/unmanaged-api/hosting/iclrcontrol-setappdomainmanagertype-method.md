---
title: ICLRControl::SetAppDomainManagerType 方法
ms.date: 03/30/2017
api_name:
- ICLRControl.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRControl interface [.NET Framework hosting]
- ICLRControl::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ec57828b-2aad-496d-a35a-e45d4bd7fe77
topic_type:
- apiref
ms.openlocfilehash: be29a4f83901b8e8fc338c2daa8f5703523402b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126578"
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="3ca19-102">ICLRControl::SetAppDomainManagerType 方法</span><span class="sxs-lookup"><span data-stu-id="3ca19-102">ICLRControl::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="3ca19-103">将从 <xref:System.AppDomainManager> 派生的类型设置为应用程序域管理器的类型。</span><span class="sxs-lookup"><span data-stu-id="3ca19-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ca19-104">语法</span><span class="sxs-lookup"><span data-stu-id="3ca19-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ca19-105">参数</span><span class="sxs-lookup"><span data-stu-id="3ca19-105">Parameters</span></span>  
 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="3ca19-106">中在其中实现从 <xref:System.AppDomainManager> 派生的请求类型的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="3ca19-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="3ca19-107">中实现 <xref:System.AppDomainManager>的功能的 `pwzAppDomainManagerAssembly` 参数中实现的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="3ca19-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ca19-108">返回值</span><span class="sxs-lookup"><span data-stu-id="3ca19-108">Return Value</span></span>  
  
|<span data-ttu-id="3ca19-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3ca19-109">HRESULT</span></span>|<span data-ttu-id="3ca19-110">描述</span><span class="sxs-lookup"><span data-stu-id="3ca19-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3ca19-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3ca19-111">S_OK</span></span>|<span data-ttu-id="3ca19-112">方法已成功返回。</span><span class="sxs-lookup"><span data-stu-id="3ca19-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="3ca19-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3ca19-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3ca19-114">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="3ca19-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3ca19-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3ca19-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3ca19-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="3ca19-116">The call timed out.</span></span>|  
|<span data-ttu-id="3ca19-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3ca19-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3ca19-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="3ca19-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3ca19-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3ca19-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3ca19-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="3ca19-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3ca19-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3ca19-121">E_FAIL</span></span>|<span data-ttu-id="3ca19-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="3ca19-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3ca19-123">方法返回 E_FAIL 后，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="3ca19-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3ca19-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="3ca19-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3ca19-125">要求</span><span class="sxs-lookup"><span data-stu-id="3ca19-125">Requirements</span></span>  
 <span data-ttu-id="3ca19-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3ca19-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ca19-127">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3ca19-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3ca19-128">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="3ca19-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3ca19-129">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ca19-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ca19-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ca19-130">See also</span></span>

- [<span data-ttu-id="3ca19-131">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="3ca19-131">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="3ca19-132">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="3ca19-132">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
