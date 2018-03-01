---
title: "ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream 方法"
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
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream method [.NET Framework hosting]
- GetReferencedAssembliesFromStream method [.NET Framework hosting]
ms.assetid: fe9849c1-c3fc-477b-a31f-e8619f5516f5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aae8c16430f8139601a5faa2bad42e285bceb84b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a><span data-ttu-id="cff39-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream 方法</span><span class="sxs-lookup"><span data-stu-id="cff39-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream Method</span></span>
<span data-ttu-id="cff39-103">获取一个指向[ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)对象，其中包含指定的流中的程序集引用的程序集的程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="cff39-103">Gets a pointer to an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cff39-104">语法</span><span class="sxs-lookup"><span data-stu-id="cff39-104">Syntax</span></span>  
  
```  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cff39-105">参数</span><span class="sxs-lookup"><span data-stu-id="cff39-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="cff39-106">[in]接口指针`IStream`包含该程序集，要进行求值。</span><span class="sxs-lookup"><span data-stu-id="cff39-106">[in] An interface pointer to an `IStream` containing the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="cff39-107">[in]提供以用于将来扩展。</span><span class="sxs-lookup"><span data-stu-id="cff39-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="cff39-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT 是公共语言运行时 (CLR) 的当前版本支持的唯一值。</span><span class="sxs-lookup"><span data-stu-id="cff39-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="cff39-109">[in]指向的指针[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)对象，其中包含要从排除的程序集的程序集标识数据`ppReferenceEnum`。</span><span class="sxs-lookup"><span data-stu-id="cff39-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that contains assembly identity data for the assemblies to be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="cff39-110">[out]指向的地址的指针`ICLRReferenceAssemblyEnum`对象，其中包含程序集标识数据中的程序集引用的程序集`pStream`，不包括中的程序集`pExcludeAssembliesList`。</span><span class="sxs-lookup"><span data-stu-id="cff39-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in `pStream`, excluding the assemblies in `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cff39-111">返回值</span><span class="sxs-lookup"><span data-stu-id="cff39-111">Return Value</span></span>  
  
|<span data-ttu-id="cff39-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cff39-112">HRESULT</span></span>|<span data-ttu-id="cff39-113">描述</span><span class="sxs-lookup"><span data-stu-id="cff39-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cff39-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="cff39-114">S_OK</span></span>|<span data-ttu-id="cff39-115">该方法返回成功。</span><span class="sxs-lookup"><span data-stu-id="cff39-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="cff39-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cff39-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cff39-117">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="cff39-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cff39-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cff39-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cff39-119">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="cff39-119">The call timed out.</span></span>|  
|<span data-ttu-id="cff39-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cff39-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cff39-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="cff39-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cff39-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cff39-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cff39-123">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="cff39-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cff39-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cff39-124">E_FAIL</span></span>|<span data-ttu-id="cff39-125">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="cff39-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cff39-126">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="cff39-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cff39-127">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="cff39-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cff39-128">备注</span><span class="sxs-lookup"><span data-stu-id="cff39-128">Remarks</span></span>  
 <span data-ttu-id="cff39-129">调用方可以选择从返回的列表中排除一组已知程序集引用。</span><span class="sxs-lookup"><span data-stu-id="cff39-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="cff39-130">此集定义为`pExcludeAssembliesList`。</span><span class="sxs-lookup"><span data-stu-id="cff39-130">This set is defined by `pExcludeAssembliesList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cff39-131">惠?</span><span class="sxs-lookup"><span data-stu-id="cff39-131">Requirements</span></span>  
 <span data-ttu-id="cff39-132">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cff39-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cff39-133">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cff39-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cff39-134">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="cff39-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cff39-135">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cff39-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cff39-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="cff39-136">See Also</span></span>  
 [<span data-ttu-id="cff39-137">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="cff39-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="cff39-138">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="cff39-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="cff39-139">ICLRReferenceAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="cff39-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
