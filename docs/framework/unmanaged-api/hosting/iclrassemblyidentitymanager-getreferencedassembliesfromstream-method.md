---
title: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: f4c200ad23ff7a71298e84fda857912da53978a5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126686"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a><span data-ttu-id="db103-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream 方法</span><span class="sxs-lookup"><span data-stu-id="db103-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream Method</span></span>
<span data-ttu-id="db103-103">获取一个指向[ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)对象的指针，该对象包含指定流中的程序集所引用的程序集的程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="db103-103">Gets a pointer to an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db103-104">语法</span><span class="sxs-lookup"><span data-stu-id="db103-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db103-105">参数</span><span class="sxs-lookup"><span data-stu-id="db103-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="db103-106">中一个接口指针，指向包含要计算的程序集的 `IStream`。</span><span class="sxs-lookup"><span data-stu-id="db103-106">[in] An interface pointer to an `IStream` containing the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="db103-107">中提供用于将来的扩展性。</span><span class="sxs-lookup"><span data-stu-id="db103-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="db103-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT 是当前版本的公共语言运行时（CLR）支持的唯一值。</span><span class="sxs-lookup"><span data-stu-id="db103-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="db103-109">中指向[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)对象的指针，该对象包含要从 `ppReferenceEnum`中排除的程序集的程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="db103-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that contains assembly identity data for the assemblies to be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="db103-110">弄一个指针，指向 `ICLRReferenceAssemblyEnum` 对象的地址，该对象包含 `pStream`中的程序集引用的程序集的程序集标识数据，`pExcludeAssembliesList`中不包括程序集。</span><span class="sxs-lookup"><span data-stu-id="db103-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in `pStream`, excluding the assemblies in `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db103-111">返回值</span><span class="sxs-lookup"><span data-stu-id="db103-111">Return Value</span></span>  
  
|<span data-ttu-id="db103-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="db103-112">HRESULT</span></span>|<span data-ttu-id="db103-113">描述</span><span class="sxs-lookup"><span data-stu-id="db103-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="db103-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="db103-114">S_OK</span></span>|<span data-ttu-id="db103-115">方法已成功返回。</span><span class="sxs-lookup"><span data-stu-id="db103-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="db103-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="db103-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="db103-117">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="db103-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="db103-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="db103-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="db103-119">调用超时。</span><span class="sxs-lookup"><span data-stu-id="db103-119">The call timed out.</span></span>|  
|<span data-ttu-id="db103-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="db103-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="db103-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="db103-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="db103-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="db103-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="db103-123">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="db103-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="db103-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="db103-124">E_FAIL</span></span>|<span data-ttu-id="db103-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="db103-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="db103-126">如果某个方法返回 E_FAIL，则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="db103-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="db103-127">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="db103-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db103-128">备注</span><span class="sxs-lookup"><span data-stu-id="db103-128">Remarks</span></span>  
 <span data-ttu-id="db103-129">调用方可以选择从返回的列表中排除一组已知的程序集引用。</span><span class="sxs-lookup"><span data-stu-id="db103-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="db103-130">此集由 `pExcludeAssembliesList`定义。</span><span class="sxs-lookup"><span data-stu-id="db103-130">This set is defined by `pExcludeAssembliesList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db103-131">要求</span><span class="sxs-lookup"><span data-stu-id="db103-131">Requirements</span></span>  
 <span data-ttu-id="db103-132">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="db103-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db103-133">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="db103-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db103-134">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="db103-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db103-135">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db103-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db103-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="db103-136">See also</span></span>

- [<span data-ttu-id="db103-137">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="db103-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="db103-138">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="db103-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="db103-139">ICLRReferenceAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="db103-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
