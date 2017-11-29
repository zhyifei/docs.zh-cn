---
title: "ICLRAssemblyIdentityManager::GetBindingIdentityFromFile 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 140240f5f108cdd26cd0e813d7fe47f102a3b941
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="f2e31-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="f2e31-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>
<span data-ttu-id="f2e31-103">获取在指定的文件路径的程序集的绑定数据的程序集标识。</span><span class="sxs-lookup"><span data-stu-id="f2e31-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2e31-104">语法</span><span class="sxs-lookup"><span data-stu-id="f2e31-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2e31-105">参数</span><span class="sxs-lookup"><span data-stu-id="f2e31-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="f2e31-106">[in]要进行求值的文件路径。</span><span class="sxs-lookup"><span data-stu-id="f2e31-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f2e31-107">[in]值为[ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md)枚举，指示程序集的标识类型。</span><span class="sxs-lookup"><span data-stu-id="f2e31-107">[in] A value of the [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="f2e31-108">提供以用于将来扩展。</span><span class="sxs-lookup"><span data-stu-id="f2e31-108">Provided for future extensibility.</span></span> <span data-ttu-id="f2e31-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT 是公共语言运行时 (CLR) 2.0 版支持的唯一值。</span><span class="sxs-lookup"><span data-stu-id="f2e31-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="f2e31-110">[out]包含的不透明的程序集标识数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="f2e31-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="f2e31-111">[在中，out]指向的大小的`pwzBuffer`。</span><span class="sxs-lookup"><span data-stu-id="f2e31-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2e31-112">返回值</span><span class="sxs-lookup"><span data-stu-id="f2e31-112">Return Value</span></span>  
  
|<span data-ttu-id="f2e31-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f2e31-113">HRESULT</span></span>|<span data-ttu-id="f2e31-114">描述</span><span class="sxs-lookup"><span data-stu-id="f2e31-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2e31-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="f2e31-115">S_OK</span></span>|<span data-ttu-id="f2e31-116">该方法返回成功。</span><span class="sxs-lookup"><span data-stu-id="f2e31-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="f2e31-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f2e31-117">E_INVALIDARG</span></span>|<span data-ttu-id="f2e31-118">提供`pwzFilePath`为 null。</span><span class="sxs-lookup"><span data-stu-id="f2e31-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="f2e31-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="f2e31-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="f2e31-120">大小`pwzBuffer`太小。</span><span class="sxs-lookup"><span data-stu-id="f2e31-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="f2e31-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f2e31-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f2e31-122">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="f2e31-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f2e31-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f2e31-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f2e31-124">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="f2e31-124">The call timed out.</span></span>|  
|<span data-ttu-id="f2e31-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f2e31-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f2e31-126">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="f2e31-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f2e31-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f2e31-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f2e31-128">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="f2e31-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f2e31-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f2e31-129">E_FAIL</span></span>|<span data-ttu-id="f2e31-130">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="f2e31-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f2e31-131">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="f2e31-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f2e31-132">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="f2e31-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2e31-133">备注</span><span class="sxs-lookup"><span data-stu-id="f2e31-133">Remarks</span></span>  
 <span data-ttu-id="f2e31-134">`GetBindingIdentityFromFile`通常称为两次。</span><span class="sxs-lookup"><span data-stu-id="f2e31-134">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="f2e31-135">第一个调用提供的 null 值`pwzBuffer`，并且该方法返回的适当大小以`pcchBufferSize`。</span><span class="sxs-lookup"><span data-stu-id="f2e31-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="f2e31-136">第二个调用提供适当分配的缓冲区，并且该方法返回与实际缓冲区完成后的数据。</span><span class="sxs-lookup"><span data-stu-id="f2e31-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2e31-137">要求</span><span class="sxs-lookup"><span data-stu-id="f2e31-137">Requirements</span></span>  
 <span data-ttu-id="f2e31-138">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f2e31-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2e31-139">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f2e31-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2e31-140">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f2e31-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2e31-141">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2e31-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2e31-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2e31-142">See Also</span></span>  
 [<span data-ttu-id="f2e31-143">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="f2e31-143">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="f2e31-144">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="f2e31-144">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="f2e31-145">ICLRHostBindingPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="f2e31-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
