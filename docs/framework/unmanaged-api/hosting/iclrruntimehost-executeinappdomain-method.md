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
ms.openlocfilehash: c012e4e2b5e41737f7bbe6a0fb887693b0ba22c8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176417"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="02c62-102">ICLRRuntimeHost::ExecuteInAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="02c62-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="02c62-103">指定<xref:System.AppDomain>在其中执行指定托管代码的用中。</span><span class="sxs-lookup"><span data-stu-id="02c62-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02c62-104">语法</span><span class="sxs-lookup"><span data-stu-id="02c62-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,
    [in] FExecuteInDomainCallback pCallback,
    [in] void* cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02c62-105">parameters</span><span class="sxs-lookup"><span data-stu-id="02c62-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="02c62-106">[在]要在<xref:System.AppDomain>其中执行指定方法的数字 ID。</span><span class="sxs-lookup"><span data-stu-id="02c62-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="02c62-107">[在]指向要在指定<xref:System.AppDomain>时间内执行的函数的指针。</span><span class="sxs-lookup"><span data-stu-id="02c62-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="02c62-108">[在]指向不透明调用方分配的内存的指针。</span><span class="sxs-lookup"><span data-stu-id="02c62-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="02c62-109">此参数由通用语言运行时 （CLR） 传递给域回调。</span><span class="sxs-lookup"><span data-stu-id="02c62-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="02c62-110">它不是运行时管理的堆内存;它不是运行时管理的堆内存。此内存的分配和生存期都由调用方控制。</span><span class="sxs-lookup"><span data-stu-id="02c62-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02c62-111">返回值</span><span class="sxs-lookup"><span data-stu-id="02c62-111">Return Value</span></span>  
  
|<span data-ttu-id="02c62-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02c62-112">HRESULT</span></span>|<span data-ttu-id="02c62-113">说明</span><span class="sxs-lookup"><span data-stu-id="02c62-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02c62-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="02c62-114">S_OK</span></span>|<span data-ttu-id="02c62-115">`ExecuteInAppDomain`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="02c62-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="02c62-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="02c62-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="02c62-117">CLR 尚未加载到进程中，或者 CLR 处于无法成功运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="02c62-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="02c62-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="02c62-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="02c62-119">呼叫超时。</span><span class="sxs-lookup"><span data-stu-id="02c62-119">The call timed out.</span></span>|  
|<span data-ttu-id="02c62-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="02c62-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="02c62-121">调用方不拥有锁。</span><span class="sxs-lookup"><span data-stu-id="02c62-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="02c62-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="02c62-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="02c62-123">当阻塞的线程或光纤等待事件时，事件已被取消。</span><span class="sxs-lookup"><span data-stu-id="02c62-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="02c62-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="02c62-124">E_FAIL</span></span>|<span data-ttu-id="02c62-125">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="02c62-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="02c62-126">如果方法返回E_FAIL，则 CLR 在进程中不再可用。</span><span class="sxs-lookup"><span data-stu-id="02c62-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="02c62-127">对托管方法的后续调用返回HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="02c62-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02c62-128">备注</span><span class="sxs-lookup"><span data-stu-id="02c62-128">Remarks</span></span>  
 <span data-ttu-id="02c62-129">`ExecuteInAppDomain`允许主机控制应执行指定托管方法的<xref:System.AppDomain>托管方法。</span><span class="sxs-lookup"><span data-stu-id="02c62-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="02c62-130">通过调用[GetCurrentAppDomainId 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)，可以获取应用程序域标识符的值，该标识符<xref:System.AppDomain.Id%2A>对应于属性的值。</span><span class="sxs-lookup"><span data-stu-id="02c62-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02c62-131">要求</span><span class="sxs-lookup"><span data-stu-id="02c62-131">Requirements</span></span>  
 <span data-ttu-id="02c62-132">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="02c62-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02c62-133">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="02c62-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="02c62-134">**库：** 作为资源包含在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="02c62-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02c62-135">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02c62-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02c62-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02c62-136">See also</span></span>

- [<span data-ttu-id="02c62-137">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="02c62-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
