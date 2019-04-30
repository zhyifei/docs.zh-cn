---
title: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile 方法
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferenceAssembliesFromFile method [.NET Framework hosting]
- GetReferenceAssembliesFromFile method [.NET Framework hosting]
ms.assetid: eed63d31-d977-4c7d-9443-f9d37a2a7d81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ba3ea7fe7b0182971899066f2cee63804fddbd1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985096"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a><span data-ttu-id="65b1b-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="65b1b-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile Method</span></span>
<span data-ttu-id="65b1b-103">获取[ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)实例，其中包含指定的文件路径在程序集引用的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="65b1b-103">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65b1b-104">语法</span><span class="sxs-lookup"><span data-stu-id="65b1b-104">Syntax</span></span>  
  
```  
HRESULT GetReferencedAssembliesFromFile (  
    [in]  LPCWSTR pwzFilePath,  
    [in]  DWORD   dwFlags,  
    [in]  ICLRAssemblyReferenceList   *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum  **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65b1b-105">参数</span><span class="sxs-lookup"><span data-stu-id="65b1b-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="65b1b-106">[in]要计算的程序集路径。</span><span class="sxs-lookup"><span data-stu-id="65b1b-106">[in] The path to the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="65b1b-107">[in]提供为将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="65b1b-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="65b1b-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT 是公共语言运行时 (CLR) 的当前版本支持的唯一值。</span><span class="sxs-lookup"><span data-stu-id="65b1b-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="65b1b-109">[in]一个指向[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)对象，表示应从排除的程序集`ppReferenceEnum`。</span><span class="sxs-lookup"><span data-stu-id="65b1b-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that represents assemblies that should be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="65b1b-110">[out]指向的地址的指针`ICLRReferenceAssemblyEnum`对象，其中包含在该程序集引用的程序集的程序集标识数据`pwzFilePath`，不包括所表示的程序集`pExcludeAssembliesList`。</span><span class="sxs-lookup"><span data-stu-id="65b1b-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly at `pwzFilePath`, excluding the assemblies represented by `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65b1b-111">返回值</span><span class="sxs-lookup"><span data-stu-id="65b1b-111">Return Value</span></span>  
  
|<span data-ttu-id="65b1b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65b1b-112">HRESULT</span></span>|<span data-ttu-id="65b1b-113">描述</span><span class="sxs-lookup"><span data-stu-id="65b1b-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65b1b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="65b1b-114">S_OK</span></span>|<span data-ttu-id="65b1b-115">该方法成功返回。</span><span class="sxs-lookup"><span data-stu-id="65b1b-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="65b1b-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="65b1b-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="65b1b-117">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="65b1b-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="65b1b-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="65b1b-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="65b1b-119">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="65b1b-119">The call timed out.</span></span>|  
|<span data-ttu-id="65b1b-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="65b1b-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="65b1b-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="65b1b-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="65b1b-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="65b1b-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="65b1b-123">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="65b1b-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="65b1b-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="65b1b-124">E_FAIL</span></span>|<span data-ttu-id="65b1b-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="65b1b-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="65b1b-126">如果方法返回 E_FAIL，CLR 不再在该过程中可用。</span><span class="sxs-lookup"><span data-stu-id="65b1b-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="65b1b-127">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="65b1b-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65b1b-128">备注</span><span class="sxs-lookup"><span data-stu-id="65b1b-128">Remarks</span></span>  
 <span data-ttu-id="65b1b-129">调用方可以选择从返回的列表中排除一组已知的程序集引用。</span><span class="sxs-lookup"><span data-stu-id="65b1b-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="65b1b-130">此集由定义`pExcludeAssembliesList`参数。</span><span class="sxs-lookup"><span data-stu-id="65b1b-130">This set is defined by the `pExcludeAssembliesList` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65b1b-131">要求</span><span class="sxs-lookup"><span data-stu-id="65b1b-131">Requirements</span></span>  
 <span data-ttu-id="65b1b-132">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="65b1b-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65b1b-133">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="65b1b-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65b1b-134">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="65b1b-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65b1b-135">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65b1b-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65b1b-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="65b1b-136">See also</span></span>

- [<span data-ttu-id="65b1b-137">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="65b1b-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="65b1b-138">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="65b1b-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="65b1b-139">ICLRReferenceAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="65b1b-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
