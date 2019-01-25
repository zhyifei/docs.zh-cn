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
ms.openlocfilehash: e19f6a51afd6d1e532631a950f4695c8e3d38eb8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521447"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="c284d-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="c284d-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>
<span data-ttu-id="c284d-103">获取数据绑定的程序集在指定的文件路径的程序集标识。</span><span class="sxs-lookup"><span data-stu-id="c284d-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c284d-104">语法</span><span class="sxs-lookup"><span data-stu-id="c284d-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c284d-105">参数</span><span class="sxs-lookup"><span data-stu-id="c284d-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="c284d-106">[in]要计算的文件路径。</span><span class="sxs-lookup"><span data-stu-id="c284d-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c284d-107">[in]值为[ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md)枚举，指示程序集的标识类型。</span><span class="sxs-lookup"><span data-stu-id="c284d-107">[in] A value of the [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="c284d-108">提供为将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="c284d-108">Provided for future extensibility.</span></span> <span data-ttu-id="c284d-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT 是公共语言运行时 (CLR) 2.0 版支持的唯一值。</span><span class="sxs-lookup"><span data-stu-id="c284d-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="c284d-110">[out]包含的不透明的程序集标识数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="c284d-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="c284d-111">[in、 out]指针的大小`pwzBuffer`。</span><span class="sxs-lookup"><span data-stu-id="c284d-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c284d-112">返回值</span><span class="sxs-lookup"><span data-stu-id="c284d-112">Return Value</span></span>  
  
|<span data-ttu-id="c284d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c284d-113">HRESULT</span></span>|<span data-ttu-id="c284d-114">描述</span><span class="sxs-lookup"><span data-stu-id="c284d-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c284d-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="c284d-115">S_OK</span></span>|<span data-ttu-id="c284d-116">该方法成功返回。</span><span class="sxs-lookup"><span data-stu-id="c284d-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="c284d-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c284d-117">E_INVALIDARG</span></span>|<span data-ttu-id="c284d-118">所提供`pwzFilePath`为 null。</span><span class="sxs-lookup"><span data-stu-id="c284d-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="c284d-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="c284d-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="c284d-120">大小`pwzBuffer`太小。</span><span class="sxs-lookup"><span data-stu-id="c284d-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="c284d-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c284d-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c284d-122">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c284d-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c284d-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c284d-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c284d-124">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="c284d-124">The call timed out.</span></span>|  
|<span data-ttu-id="c284d-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c284d-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c284d-126">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c284d-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c284d-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c284d-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c284d-128">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="c284d-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c284d-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c284d-129">E_FAIL</span></span>|<span data-ttu-id="c284d-130">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c284d-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c284d-131">如果方法返回 E_FAIL，CLR 不再在该过程中可用。</span><span class="sxs-lookup"><span data-stu-id="c284d-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c284d-132">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c284d-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c284d-133">备注</span><span class="sxs-lookup"><span data-stu-id="c284d-133">Remarks</span></span>  
 <span data-ttu-id="c284d-134">`GetBindingIdentityFromFile` 通常称为两次。</span><span class="sxs-lookup"><span data-stu-id="c284d-134">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="c284d-135">第一个调用提供的 null 值`pwzBuffer`，并且该方法返回的相应大小以`pcchBufferSize`。</span><span class="sxs-lookup"><span data-stu-id="c284d-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="c284d-136">第二个调用提供的适当地分配的缓冲区，并且该方法返回与实际的缓冲区数据完成后。</span><span class="sxs-lookup"><span data-stu-id="c284d-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c284d-137">要求</span><span class="sxs-lookup"><span data-stu-id="c284d-137">Requirements</span></span>  
 <span data-ttu-id="c284d-138">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c284d-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c284d-139">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c284d-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c284d-140">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c284d-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c284d-141">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c284d-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c284d-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="c284d-142">See also</span></span>
- [<span data-ttu-id="c284d-143">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="c284d-143">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="c284d-144">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="c284d-144">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="c284d-145">ICLRHostBindingPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="c284d-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
