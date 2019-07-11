---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromStream 方法
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream
helpviewer_keywords:
- GetBindingIdentityFromStream method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream method [.NET Framework hosting]
ms.assetid: 40123b30-a589-46b3-95d3-af7b2b0baa05
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16cb3495bbc2fa9ead25afd5e7120774b021a37f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773559"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromstream-method"></a><span data-ttu-id="f7ecb-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream 方法</span><span class="sxs-lookup"><span data-stu-id="f7ecb-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream Method</span></span>
<span data-ttu-id="f7ecb-103">获取指定的流中的程序集的规范的程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="f7ecb-103">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7ecb-104">语法</span><span class="sxs-lookup"><span data-stu-id="f7ecb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromStream (  
    [in] IStream    *pStream,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7ecb-105">参数</span><span class="sxs-lookup"><span data-stu-id="f7ecb-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="f7ecb-106">[in]要计算的程序集流。</span><span class="sxs-lookup"><span data-stu-id="f7ecb-106">[in] The assembly stream to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f7ecb-107">[in]提供为将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="f7ecb-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="f7ecb-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT 是公共语言运行时 (CLR) 的当前版本支持的唯一值。</span><span class="sxs-lookup"><span data-stu-id="f7ecb-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="f7ecb-109">[out]包含的不透明的程序集标识数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="f7ecb-109">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="f7ecb-110">[in、 out]大小`pwzBuffer`。</span><span class="sxs-lookup"><span data-stu-id="f7ecb-110">[in, out] The size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7ecb-111">返回值</span><span class="sxs-lookup"><span data-stu-id="f7ecb-111">Return Value</span></span>  
  
|<span data-ttu-id="f7ecb-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f7ecb-112">HRESULT</span></span>|<span data-ttu-id="f7ecb-113">描述</span><span class="sxs-lookup"><span data-stu-id="f7ecb-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f7ecb-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="f7ecb-114">S_OK</span></span>|<span data-ttu-id="f7ecb-115">该方法成功返回。</span><span class="sxs-lookup"><span data-stu-id="f7ecb-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="f7ecb-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f7ecb-116">E_INVALIDARG</span></span>|<span data-ttu-id="f7ecb-117">所提供`pStream`为 null。</span><span class="sxs-lookup"><span data-stu-id="f7ecb-117">The supplied `pStream` is null.</span></span>|  
|<span data-ttu-id="f7ecb-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="f7ecb-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="f7ecb-119">大小`pwzBuffer`太小。</span><span class="sxs-lookup"><span data-stu-id="f7ecb-119">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="f7ecb-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f7ecb-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f7ecb-121">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="f7ecb-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f7ecb-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f7ecb-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f7ecb-123">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="f7ecb-123">The call timed out.</span></span>|  
|<span data-ttu-id="f7ecb-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f7ecb-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f7ecb-125">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="f7ecb-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f7ecb-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f7ecb-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f7ecb-127">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="f7ecb-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f7ecb-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f7ecb-128">E_FAIL</span></span>|<span data-ttu-id="f7ecb-129">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="f7ecb-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f7ecb-130">如果方法返回 E_FAIL，CLR 不再在该过程中可用。</span><span class="sxs-lookup"><span data-stu-id="f7ecb-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f7ecb-131">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="f7ecb-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f7ecb-132">要求</span><span class="sxs-lookup"><span data-stu-id="f7ecb-132">Requirements</span></span>  
 <span data-ttu-id="f7ecb-133">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f7ecb-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7ecb-134">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f7ecb-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f7ecb-135">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f7ecb-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7ecb-136">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7ecb-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7ecb-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7ecb-137">See also</span></span>

- [<span data-ttu-id="f7ecb-138">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="f7ecb-138">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="f7ecb-139">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="f7ecb-139">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
