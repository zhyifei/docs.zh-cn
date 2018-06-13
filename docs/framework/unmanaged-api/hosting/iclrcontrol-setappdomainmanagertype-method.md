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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be778fed910b2cbdbf5e9ae7754abae437ef6bec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433729"
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="4a14a-102">ICLRControl::SetAppDomainManagerType 方法</span><span class="sxs-lookup"><span data-stu-id="4a14a-102">ICLRControl::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="4a14a-103">设置其类型派生自此<xref:System.AppDomainManager>作为应用程序域管理器的类型。</span><span class="sxs-lookup"><span data-stu-id="4a14a-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a14a-104">语法</span><span class="sxs-lookup"><span data-stu-id="4a14a-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a14a-105">参数</span><span class="sxs-lookup"><span data-stu-id="4a14a-105">Parameters</span></span>  
 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="4a14a-106">[in]请求的类型派生自程序集的名称<xref:System.AppDomainManager>实现。</span><span class="sxs-lookup"><span data-stu-id="4a14a-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="4a14a-107">[in]在中实现的类型的名称`pwzAppDomainManagerAssembly`实现的功能的参数<xref:System.AppDomainManager>。</span><span class="sxs-lookup"><span data-stu-id="4a14a-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a14a-108">返回值</span><span class="sxs-lookup"><span data-stu-id="4a14a-108">Return Value</span></span>  
  
|<span data-ttu-id="4a14a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4a14a-109">HRESULT</span></span>|<span data-ttu-id="4a14a-110">描述</span><span class="sxs-lookup"><span data-stu-id="4a14a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4a14a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a14a-111">S_OK</span></span>|<span data-ttu-id="4a14a-112">该方法返回成功。</span><span class="sxs-lookup"><span data-stu-id="4a14a-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="4a14a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4a14a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4a14a-114">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="4a14a-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4a14a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4a14a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4a14a-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="4a14a-116">The call timed out.</span></span>|  
|<span data-ttu-id="4a14a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a14a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4a14a-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="4a14a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4a14a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4a14a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4a14a-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="4a14a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4a14a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4a14a-121">E_FAIL</span></span>|<span data-ttu-id="4a14a-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="4a14a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4a14a-123">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="4a14a-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4a14a-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="4a14a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a14a-125">要求</span><span class="sxs-lookup"><span data-stu-id="4a14a-125">Requirements</span></span>  
 <span data-ttu-id="4a14a-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4a14a-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a14a-127">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4a14a-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a14a-128">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4a14a-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a14a-129">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a14a-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a14a-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a14a-130">See Also</span></span>  
 [<span data-ttu-id="4a14a-131">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="4a14a-131">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="4a14a-132">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="4a14a-132">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
