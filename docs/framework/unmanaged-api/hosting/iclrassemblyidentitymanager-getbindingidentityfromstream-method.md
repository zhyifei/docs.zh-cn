---
title: "ICLRAssemblyIdentityManager::GetBindingIdentityFromStream 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager.GetBindingIdentityFromStream
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager::GetBindingIdentityFromStream
helpviewer_keywords:
- GetBindingIdentityFromStream method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream method [.NET Framework hosting]
ms.assetid: 40123b30-a589-46b3-95d3-af7b2b0baa05
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cd16f13bd77127953bdd17b258c7be518088f899
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromstream-method"></a><span data-ttu-id="907d3-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream 方法</span><span class="sxs-lookup"><span data-stu-id="907d3-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream Method</span></span>
<span data-ttu-id="907d3-103">获取指定的流中的程序集的规范的程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="907d3-103">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="907d3-104">语法</span><span class="sxs-lookup"><span data-stu-id="907d3-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromStream (  
    [in] IStream    *pStream,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="907d3-105">参数</span><span class="sxs-lookup"><span data-stu-id="907d3-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="907d3-106">[in]要计算的程序集流。</span><span class="sxs-lookup"><span data-stu-id="907d3-106">[in] The assembly stream to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="907d3-107">[in]提供以用于将来扩展。</span><span class="sxs-lookup"><span data-stu-id="907d3-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="907d3-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT 是公共语言运行时 (CLR) 的当前版本支持的唯一值。</span><span class="sxs-lookup"><span data-stu-id="907d3-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="907d3-109">[out]包含的不透明的程序集标识数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="907d3-109">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="907d3-110">[在中，out]大小`pwzBuffer`。</span><span class="sxs-lookup"><span data-stu-id="907d3-110">[in, out] The size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="907d3-111">返回值</span><span class="sxs-lookup"><span data-stu-id="907d3-111">Return Value</span></span>  
  
|<span data-ttu-id="907d3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="907d3-112">HRESULT</span></span>|<span data-ttu-id="907d3-113">描述</span><span class="sxs-lookup"><span data-stu-id="907d3-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="907d3-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="907d3-114">S_OK</span></span>|<span data-ttu-id="907d3-115">该方法返回成功。</span><span class="sxs-lookup"><span data-stu-id="907d3-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="907d3-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="907d3-116">E_INVALIDARG</span></span>|<span data-ttu-id="907d3-117">提供`pStream`为 null。</span><span class="sxs-lookup"><span data-stu-id="907d3-117">The supplied `pStream` is null.</span></span>|  
|<span data-ttu-id="907d3-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="907d3-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="907d3-119">大小`pwzBuffer`太小。</span><span class="sxs-lookup"><span data-stu-id="907d3-119">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="907d3-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="907d3-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="907d3-121">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="907d3-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="907d3-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="907d3-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="907d3-123">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="907d3-123">The call timed out.</span></span>|  
|<span data-ttu-id="907d3-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="907d3-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="907d3-125">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="907d3-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="907d3-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="907d3-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="907d3-127">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="907d3-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="907d3-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="907d3-128">E_FAIL</span></span>|<span data-ttu-id="907d3-129">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="907d3-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="907d3-130">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="907d3-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="907d3-131">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="907d3-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="907d3-132">要求</span><span class="sxs-lookup"><span data-stu-id="907d3-132">Requirements</span></span>  
 <span data-ttu-id="907d3-133">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="907d3-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="907d3-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="907d3-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="907d3-135">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="907d3-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="907d3-136">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="907d3-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="907d3-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="907d3-137">See Also</span></span>  
 [<span data-ttu-id="907d3-138">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="907d3-138">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="907d3-139">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="907d3-139">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
