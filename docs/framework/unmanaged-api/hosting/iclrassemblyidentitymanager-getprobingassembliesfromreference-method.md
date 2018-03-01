---
title: "ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRAssemblyIdentityManager.GetProbingAssembliesFromReference
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference method [.NET Framework hosting]
- GetProbingAssembliesFromReference method [.NET Framework hosting]
ms.assetid: aec05744-e8d4-44c6-b4a8-e583229ac34e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f255db046f4c7d698ad864723167e81952481519
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a><span data-ttu-id="6270b-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference 方法</span><span class="sxs-lookup"><span data-stu-id="6270b-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Method</span></span>
<span data-ttu-id="6270b-103">获取[ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)由与指定的标识类型的程序集引用的程序集标识的枚举数。</span><span class="sxs-lookup"><span data-stu-id="6270b-103">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6270b-104">语法</span><span class="sxs-lookup"><span data-stu-id="6270b-104">Syntax</span></span>  
  
```  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6270b-105">参数</span><span class="sxs-lookup"><span data-stu-id="6270b-105">Parameters</span></span>  
 `dwMachineType`  
 <span data-ttu-id="6270b-106">[in]一个有效的值，指定处理器体系结构，如在 WinNT.h 中定义。</span><span class="sxs-lookup"><span data-stu-id="6270b-106">[in] A valid value that specifies the processor architecture, as defined in WinNT.h.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="6270b-107">[in]提供以用于将来扩展。</span><span class="sxs-lookup"><span data-stu-id="6270b-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="6270b-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT 是公共语言运行时 (CLR) 的当前版本支持的唯一值。</span><span class="sxs-lookup"><span data-stu-id="6270b-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzReferenceIdentity`  
 <span data-ttu-id="6270b-109">[in]不透明的程序集绑定的标识，通常从调用返回[iclrassemblyidentitymanager:: Getbindingidentityfromfile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)或[iclrassemblyidentitymanager:: Getbindingidentityfromstream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6270b-109">[in] An opaque assembly binding identity, typically returned from a call to the [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) or [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) method.</span></span>  
  
 `ppProbingAssemblyEnum`  
 <span data-ttu-id="6270b-110">[out]接口指针`ICLRProbingAssemblyEnum`包含对标识的程序集引用的程序集的引用的枚举器`pwzReferenceIdentity`。</span><span class="sxs-lookup"><span data-stu-id="6270b-110">[out] An interface pointer to an `ICLRProbingAssemblyEnum` enumerator that contains references to the assemblies referenced by the assembly identified by `pwzReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6270b-111">返回值</span><span class="sxs-lookup"><span data-stu-id="6270b-111">Return Value</span></span>  
  
|<span data-ttu-id="6270b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6270b-112">HRESULT</span></span>|<span data-ttu-id="6270b-113">描述</span><span class="sxs-lookup"><span data-stu-id="6270b-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6270b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="6270b-114">S_OK</span></span>|<span data-ttu-id="6270b-115">该方法返回成功。</span><span class="sxs-lookup"><span data-stu-id="6270b-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="6270b-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6270b-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6270b-117">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="6270b-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6270b-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6270b-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6270b-119">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="6270b-119">The call timed out.</span></span>|  
|<span data-ttu-id="6270b-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6270b-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6270b-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="6270b-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6270b-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6270b-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6270b-123">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="6270b-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6270b-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6270b-124">E_FAIL</span></span>|<span data-ttu-id="6270b-125">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="6270b-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6270b-126">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="6270b-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6270b-127">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="6270b-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6270b-128">惠?</span><span class="sxs-lookup"><span data-stu-id="6270b-128">Requirements</span></span>  
 <span data-ttu-id="6270b-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6270b-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6270b-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6270b-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6270b-131">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6270b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6270b-132">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6270b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6270b-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="6270b-133">See Also</span></span>  
 [<span data-ttu-id="6270b-134">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="6270b-134">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="6270b-135">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="6270b-135">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="6270b-136">ICLRProbingAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="6270b-136">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
