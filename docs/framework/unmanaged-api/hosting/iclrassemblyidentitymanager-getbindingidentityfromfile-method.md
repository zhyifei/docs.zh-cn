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
ms.openlocfilehash: 19d6a76d62680be91a7b9721912ca528edde7511
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126759"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="8bb2e-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="8bb2e-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>
<span data-ttu-id="8bb2e-103">获取指定文件路径处的程序集的程序集标识绑定数据。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bb2e-104">语法</span><span class="sxs-lookup"><span data-stu-id="8bb2e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bb2e-105">参数</span><span class="sxs-lookup"><span data-stu-id="8bb2e-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="8bb2e-106">中要计算的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="8bb2e-107">中指示程序集的标识类型的[ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md)枚举的值。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-107">[in] A value of the [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="8bb2e-108">提供用于将来的扩展性。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-108">Provided for future extensibility.</span></span> <span data-ttu-id="8bb2e-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT 是公共语言运行时（CLR）版本2.0 支持的唯一值。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="8bb2e-110">弄包含不透明程序集标识数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="8bb2e-111">[in，out]指向 `pwzBuffer`的大小的指针。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8bb2e-112">返回值</span><span class="sxs-lookup"><span data-stu-id="8bb2e-112">Return Value</span></span>  
  
|<span data-ttu-id="8bb2e-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8bb2e-113">HRESULT</span></span>|<span data-ttu-id="8bb2e-114">描述</span><span class="sxs-lookup"><span data-stu-id="8bb2e-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8bb2e-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="8bb2e-115">S_OK</span></span>|<span data-ttu-id="8bb2e-116">方法已成功返回。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="8bb2e-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="8bb2e-117">E_INVALIDARG</span></span>|<span data-ttu-id="8bb2e-118">提供的 `pwzFilePath` 为 null。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="8bb2e-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="8bb2e-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="8bb2e-120">`pwzBuffer` 的大小太小。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="8bb2e-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8bb2e-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8bb2e-122">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8bb2e-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8bb2e-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8bb2e-124">调用超时。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-124">The call timed out.</span></span>|  
|<span data-ttu-id="8bb2e-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8bb2e-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8bb2e-126">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8bb2e-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8bb2e-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8bb2e-128">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8bb2e-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8bb2e-129">E_FAIL</span></span>|<span data-ttu-id="8bb2e-130">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8bb2e-131">如果某个方法返回 E_FAIL，则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8bb2e-132">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bb2e-133">备注</span><span class="sxs-lookup"><span data-stu-id="8bb2e-133">Remarks</span></span>  
 <span data-ttu-id="8bb2e-134">`GetBindingIdentityFromFile` 通常称为两次。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-134">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="8bb2e-135">第一次调用为 `pwzBuffer`提供了 null 值，并且该方法在 `pcchBufferSize`中返回适当大小。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="8bb2e-136">第二个调用提供适当分配的缓冲区，方法在完成时返回实际的缓冲区数据。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bb2e-137">要求</span><span class="sxs-lookup"><span data-stu-id="8bb2e-137">Requirements</span></span>  
 <span data-ttu-id="8bb2e-138">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8bb2e-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bb2e-139">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8bb2e-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8bb2e-140">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8bb2e-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8bb2e-141">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bb2e-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bb2e-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="8bb2e-142">See also</span></span>

- [<span data-ttu-id="8bb2e-143">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="8bb2e-143">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="8bb2e-144">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="8bb2e-144">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="8bb2e-145">ICLRHostBindingPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="8bb2e-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
