---
title: ICLRRuntimeHost::ExecuteInAppDomain 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type:
- apiref
ms.openlocfilehash: c847f177f48d72f28192d1efabe93c65a7b3f4b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120490"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="0d2c3-102">ICLRRuntimeHost::ExecuteInAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="0d2c3-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="0d2c3-103">指定要在其中执行指定的托管代码的 <xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="0d2c3-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d2c3-104">语法</span><span class="sxs-lookup"><span data-stu-id="0d2c3-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d2c3-105">参数</span><span class="sxs-lookup"><span data-stu-id="0d2c3-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="0d2c3-106">中要在其中执行指定方法的 <xref:System.AppDomain> 的数字 ID。</span><span class="sxs-lookup"><span data-stu-id="0d2c3-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="0d2c3-107">中指向函数的指针，该函数在指定的 <xref:System.AppDomain>内执行。</span><span class="sxs-lookup"><span data-stu-id="0d2c3-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="0d2c3-108">中指向不透明调用方分配的内存的指针。</span><span class="sxs-lookup"><span data-stu-id="0d2c3-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="0d2c3-109">此参数由公共语言运行时（CLR）传递到域回调。</span><span class="sxs-lookup"><span data-stu-id="0d2c3-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="0d2c3-110">它不是运行时托管堆内存;此内存的分配和生存期均由调用方控制。</span><span class="sxs-lookup"><span data-stu-id="0d2c3-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d2c3-111">返回值</span><span class="sxs-lookup"><span data-stu-id="0d2c3-111">Return Value</span></span>  
  
|<span data-ttu-id="0d2c3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0d2c3-112">HRESULT</span></span>|<span data-ttu-id="0d2c3-113">描述</span><span class="sxs-lookup"><span data-stu-id="0d2c3-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0d2c3-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="0d2c3-114">S_OK</span></span>|<span data-ttu-id="0d2c3-115">`ExecuteInAppDomain` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="0d2c3-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="0d2c3-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0d2c3-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0d2c3-117">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="0d2c3-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0d2c3-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0d2c3-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0d2c3-119">调用超时。</span><span class="sxs-lookup"><span data-stu-id="0d2c3-119">The call timed out.</span></span>|  
|<span data-ttu-id="0d2c3-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0d2c3-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0d2c3-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="0d2c3-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0d2c3-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0d2c3-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0d2c3-123">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="0d2c3-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0d2c3-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0d2c3-124">E_FAIL</span></span>|<span data-ttu-id="0d2c3-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="0d2c3-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0d2c3-126">如果某个方法返回 E_FAIL，则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="0d2c3-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0d2c3-127">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="0d2c3-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d2c3-128">备注</span><span class="sxs-lookup"><span data-stu-id="0d2c3-128">Remarks</span></span>  
 <span data-ttu-id="0d2c3-129">`ExecuteInAppDomain` 允许主机控制应在其中执行指定托管方法的托管 <xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="0d2c3-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="0d2c3-130">可以通过调用[GetCurrentAppDomainId 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)来获取应用程序域的标识符值，该标识符与 <xref:System.AppDomain.Id%2A> 属性的值相对应。</span><span class="sxs-lookup"><span data-stu-id="0d2c3-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d2c3-131">要求</span><span class="sxs-lookup"><span data-stu-id="0d2c3-131">Requirements</span></span>  
 <span data-ttu-id="0d2c3-132">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0d2c3-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d2c3-133">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0d2c3-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d2c3-134">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="0d2c3-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d2c3-135">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d2c3-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d2c3-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="0d2c3-136">See also</span></span>

- [<span data-ttu-id="0d2c3-137">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="0d2c3-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
