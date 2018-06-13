---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromFile 方法
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28e97289eda5949e6d124426eb58105e2e3ad33e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435037"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="19512-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="19512-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>
<span data-ttu-id="19512-103">获取在指定的文件路径的程序集的绑定数据的程序集标识。</span><span class="sxs-lookup"><span data-stu-id="19512-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19512-104">语法</span><span class="sxs-lookup"><span data-stu-id="19512-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="19512-105">参数</span><span class="sxs-lookup"><span data-stu-id="19512-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="19512-106">[in]要进行求值的文件路径。</span><span class="sxs-lookup"><span data-stu-id="19512-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="19512-107">[in]值为[ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md)枚举，指示程序集的标识类型。</span><span class="sxs-lookup"><span data-stu-id="19512-107">[in] A value of the [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="19512-108">提供以用于将来扩展。</span><span class="sxs-lookup"><span data-stu-id="19512-108">Provided for future extensibility.</span></span> <span data-ttu-id="19512-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT 是公共语言运行时 (CLR) 2.0 版支持的唯一值。</span><span class="sxs-lookup"><span data-stu-id="19512-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="19512-110">[out]包含的不透明的程序集标识数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="19512-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="19512-111">[在中，out]指向的大小的`pwzBuffer`。</span><span class="sxs-lookup"><span data-stu-id="19512-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19512-112">返回值</span><span class="sxs-lookup"><span data-stu-id="19512-112">Return Value</span></span>  
  
|<span data-ttu-id="19512-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="19512-113">HRESULT</span></span>|<span data-ttu-id="19512-114">描述</span><span class="sxs-lookup"><span data-stu-id="19512-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19512-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="19512-115">S_OK</span></span>|<span data-ttu-id="19512-116">该方法返回成功。</span><span class="sxs-lookup"><span data-stu-id="19512-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="19512-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="19512-117">E_INVALIDARG</span></span>|<span data-ttu-id="19512-118">提供`pwzFilePath`为 null。</span><span class="sxs-lookup"><span data-stu-id="19512-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="19512-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="19512-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="19512-120">大小`pwzBuffer`太小。</span><span class="sxs-lookup"><span data-stu-id="19512-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="19512-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="19512-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="19512-122">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="19512-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="19512-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="19512-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="19512-124">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="19512-124">The call timed out.</span></span>|  
|<span data-ttu-id="19512-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="19512-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="19512-126">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="19512-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="19512-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="19512-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="19512-128">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="19512-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="19512-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="19512-129">E_FAIL</span></span>|<span data-ttu-id="19512-130">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="19512-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="19512-131">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="19512-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="19512-132">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="19512-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19512-133">备注</span><span class="sxs-lookup"><span data-stu-id="19512-133">Remarks</span></span>  
 <span data-ttu-id="19512-134">`GetBindingIdentityFromFile` 通常称为两次。</span><span class="sxs-lookup"><span data-stu-id="19512-134">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="19512-135">第一个调用提供的 null 值`pwzBuffer`，并且该方法返回的适当大小以`pcchBufferSize`。</span><span class="sxs-lookup"><span data-stu-id="19512-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="19512-136">第二个调用提供适当分配的缓冲区，并且该方法返回与实际缓冲区完成后的数据。</span><span class="sxs-lookup"><span data-stu-id="19512-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19512-137">要求</span><span class="sxs-lookup"><span data-stu-id="19512-137">Requirements</span></span>  
 <span data-ttu-id="19512-138">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="19512-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19512-139">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="19512-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19512-140">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="19512-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19512-141">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19512-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19512-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="19512-142">See Also</span></span>  
 [<span data-ttu-id="19512-143">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="19512-143">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="19512-144">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="19512-144">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="19512-145">ICLRHostBindingPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="19512-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
