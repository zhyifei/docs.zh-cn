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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127824"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a><span data-ttu-id="63aba-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="63aba-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile Method</span></span>
<span data-ttu-id="63aba-103">获取[ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)实例，其中包含指定的文件路径在程序集引用的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="63aba-103">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63aba-104">语法</span><span class="sxs-lookup"><span data-stu-id="63aba-104">Syntax</span></span>  
  
```  
HRESULT GetReferencedAssembliesFromFile (  
    [in]  LPCWSTR pwzFilePath,  
    [in]  DWORD   dwFlags,  
    [in]  ICLRAssemblyReferenceList   *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum  **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63aba-105">参数</span><span class="sxs-lookup"><span data-stu-id="63aba-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="63aba-106">[in]要计算的程序集路径。</span><span class="sxs-lookup"><span data-stu-id="63aba-106">[in] The path to the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="63aba-107">[in]提供为将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="63aba-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="63aba-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT 是公共语言运行时 (CLR) 的当前版本支持的唯一值。</span><span class="sxs-lookup"><span data-stu-id="63aba-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="63aba-109">[in]一个指向[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)对象，表示应从排除的程序集`ppReferenceEnum`。</span><span class="sxs-lookup"><span data-stu-id="63aba-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that represents assemblies that should be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="63aba-110">[out]指向的地址的指针`ICLRReferenceAssemblyEnum`对象，其中包含在该程序集引用的程序集的程序集标识数据`pwzFilePath`，不包括所表示的程序集`pExcludeAssembliesList`。</span><span class="sxs-lookup"><span data-stu-id="63aba-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly at `pwzFilePath`, excluding the assemblies represented by `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63aba-111">返回值</span><span class="sxs-lookup"><span data-stu-id="63aba-111">Return Value</span></span>  
  
|<span data-ttu-id="63aba-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="63aba-112">HRESULT</span></span>|<span data-ttu-id="63aba-113">描述</span><span class="sxs-lookup"><span data-stu-id="63aba-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="63aba-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="63aba-114">S_OK</span></span>|<span data-ttu-id="63aba-115">该方法成功返回。</span><span class="sxs-lookup"><span data-stu-id="63aba-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="63aba-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="63aba-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="63aba-117">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="63aba-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="63aba-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="63aba-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="63aba-119">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="63aba-119">The call timed out.</span></span>|  
|<span data-ttu-id="63aba-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="63aba-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="63aba-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="63aba-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="63aba-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="63aba-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="63aba-123">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="63aba-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="63aba-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="63aba-124">E_FAIL</span></span>|<span data-ttu-id="63aba-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="63aba-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="63aba-126">如果方法返回 E_FAIL，CLR 不再在该过程中可用。</span><span class="sxs-lookup"><span data-stu-id="63aba-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="63aba-127">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="63aba-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63aba-128">备注</span><span class="sxs-lookup"><span data-stu-id="63aba-128">Remarks</span></span>  
 <span data-ttu-id="63aba-129">调用方可以选择从返回的列表中排除一组已知的程序集引用。</span><span class="sxs-lookup"><span data-stu-id="63aba-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="63aba-130">此集由定义`pExcludeAssembliesList`参数。</span><span class="sxs-lookup"><span data-stu-id="63aba-130">This set is defined by the `pExcludeAssembliesList` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63aba-131">要求</span><span class="sxs-lookup"><span data-stu-id="63aba-131">Requirements</span></span>  
 <span data-ttu-id="63aba-132">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="63aba-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63aba-133">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="63aba-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="63aba-134">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="63aba-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="63aba-135">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="63aba-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="63aba-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="63aba-136">See also</span></span>

- [<span data-ttu-id="63aba-137">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="63aba-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="63aba-138">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="63aba-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="63aba-139">ICLRReferenceAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="63aba-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
