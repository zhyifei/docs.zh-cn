---
title: IHostControl::SetAppDomainManager 方法
ms.date: 03/30/2017
api_name:
- IHostControl.SetAppDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::SetAppDomainManager
helpviewer_keywords:
- IHostControl::SetAppDomainManager method [.NET Framework hosting]
- SetAppDomainManager method [.NET Framework hosting]
ms.assetid: 6562bbe7-0d67-4c50-a958-3a18cf680375
topic_type:
- apiref
ms.openlocfilehash: de264135450190fd028eb8cf12017d94cc65ffac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134726"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a><span data-ttu-id="aa29c-102">IHostControl::SetAppDomainManager 方法</span><span class="sxs-lookup"><span data-stu-id="aa29c-102">IHostControl::SetAppDomainManager Method</span></span>
<span data-ttu-id="aa29c-103">通知宿主已创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="aa29c-103">Notifies the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa29c-104">语法</span><span class="sxs-lookup"><span data-stu-id="aa29c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa29c-105">参数</span><span class="sxs-lookup"><span data-stu-id="aa29c-105">Parameters</span></span>  
 `dwAppDomainID`  
 <span data-ttu-id="aa29c-106">中所选 <xref:System.AppDomain>的数值标识符。</span><span class="sxs-lookup"><span data-stu-id="aa29c-106">[in] The numeric identifier of the selected <xref:System.AppDomain>.</span></span>  
  
 `pUnkAppDomainManager`  
 <span data-ttu-id="aa29c-107">中指向宿主作为 `IUnknown`实现的 <xref:System.AppDomainManager> 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="aa29c-107">[in] A pointer to the <xref:System.AppDomainManager> object that the host implements as `IUnknown`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa29c-108">返回值</span><span class="sxs-lookup"><span data-stu-id="aa29c-108">Return Value</span></span>  
  
|<span data-ttu-id="aa29c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aa29c-109">HRESULT</span></span>|<span data-ttu-id="aa29c-110">描述</span><span class="sxs-lookup"><span data-stu-id="aa29c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aa29c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="aa29c-111">S_OK</span></span>|<span data-ttu-id="aa29c-112">`SetAppDomainManager` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="aa29c-112">`SetAppDomainManager` returned successfully.</span></span>|  
|<span data-ttu-id="aa29c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="aa29c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="aa29c-114">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="aa29c-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="aa29c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="aa29c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="aa29c-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="aa29c-116">The call timed out.</span></span>|  
|<span data-ttu-id="aa29c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="aa29c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="aa29c-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="aa29c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="aa29c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="aa29c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="aa29c-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="aa29c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="aa29c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="aa29c-121">E_FAIL</span></span>|<span data-ttu-id="aa29c-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="aa29c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="aa29c-123">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="aa29c-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="aa29c-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="aa29c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa29c-125">备注</span><span class="sxs-lookup"><span data-stu-id="aa29c-125">Remarks</span></span>  
 <span data-ttu-id="aa29c-126"><xref:System.AppDomainManager> 向宿主提供一种机制，用于启动到托管代码，并控制每个 <xref:System.AppDomain>的创建和设置。</span><span class="sxs-lookup"><span data-stu-id="aa29c-126">The <xref:System.AppDomainManager> provides the host with a mechanism to bootstrap into managed code and to control the creation and settings of each <xref:System.AppDomain>.</span></span> <span data-ttu-id="aa29c-127">创建该 <xref:System.AppDomain> 时，将 <xref:System.AppDomainManager> 加载到每个 <xref:System.AppDomain> 中。</span><span class="sxs-lookup"><span data-stu-id="aa29c-127">The <xref:System.AppDomainManager> is loaded into each <xref:System.AppDomain> when that <xref:System.AppDomain> is created.</span></span> <span data-ttu-id="aa29c-128">如果选择此选项，CLR 将通过设置 `pUnkAppDomainManager` 参数的值，通知宿主已创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="aa29c-128">If it chooses, the CLR notifies the host that the application domain has been created by setting the value of the `pUnkAppDomainManager` parameter.</span></span>  
  
 <span data-ttu-id="aa29c-129">在其 `SetAppDomainManager` 方法的实现中，宿主可以设置应用程序域管理器的程序集名称和类型。</span><span class="sxs-lookup"><span data-stu-id="aa29c-129">In its implementation of the `SetAppDomainManager` method, the host can set the assembly name and type for the application domain manager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa29c-130">要求</span><span class="sxs-lookup"><span data-stu-id="aa29c-130">Requirements</span></span>  
 <span data-ttu-id="aa29c-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aa29c-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa29c-132">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="aa29c-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aa29c-133">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="aa29c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa29c-134">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa29c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa29c-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa29c-135">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="aa29c-136">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="aa29c-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
