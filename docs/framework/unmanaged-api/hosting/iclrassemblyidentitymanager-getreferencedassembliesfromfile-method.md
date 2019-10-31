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
ms.openlocfilehash: 65dc330e88cb2457cc34f9994313373ab1ab84aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126704"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a><span data-ttu-id="a0fa5-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="a0fa5-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile Method</span></span>
<span data-ttu-id="a0fa5-103">获取一个[ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)实例，该实例包含程序集在指定文件路径处引用的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="a0fa5-103">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0fa5-104">语法</span><span class="sxs-lookup"><span data-stu-id="a0fa5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromFile (  
    [in]  LPCWSTR pwzFilePath,  
    [in]  DWORD   dwFlags,  
    [in]  ICLRAssemblyReferenceList   *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum  **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0fa5-105">参数</span><span class="sxs-lookup"><span data-stu-id="a0fa5-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="a0fa5-106">中要计算的程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="a0fa5-106">[in] The path to the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a0fa5-107">中提供用于将来的扩展性。</span><span class="sxs-lookup"><span data-stu-id="a0fa5-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="a0fa5-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT 是当前版本的公共语言运行时（CLR）支持的唯一值。</span><span class="sxs-lookup"><span data-stu-id="a0fa5-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="a0fa5-109">中指向[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)对象的指针，该对象表示应从 `ppReferenceEnum`中排除的程序集。</span><span class="sxs-lookup"><span data-stu-id="a0fa5-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that represents assemblies that should be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="a0fa5-110">弄一个指针，它指向 `ICLRReferenceAssemblyEnum` 对象的地址，该对象包含在 `pwzFilePath`的程序集引用的程序集的程序集标识数据，不包括 `pExcludeAssembliesList`表示的程序集。</span><span class="sxs-lookup"><span data-stu-id="a0fa5-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly at `pwzFilePath`, excluding the assemblies represented by `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0fa5-111">返回值</span><span class="sxs-lookup"><span data-stu-id="a0fa5-111">Return Value</span></span>  
  
|<span data-ttu-id="a0fa5-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0fa5-112">HRESULT</span></span>|<span data-ttu-id="a0fa5-113">描述</span><span class="sxs-lookup"><span data-stu-id="a0fa5-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0fa5-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0fa5-114">S_OK</span></span>|<span data-ttu-id="a0fa5-115">方法已成功返回。</span><span class="sxs-lookup"><span data-stu-id="a0fa5-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="a0fa5-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a0fa5-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a0fa5-117">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="a0fa5-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a0fa5-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a0fa5-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a0fa5-119">调用超时。</span><span class="sxs-lookup"><span data-stu-id="a0fa5-119">The call timed out.</span></span>|  
|<span data-ttu-id="a0fa5-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a0fa5-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a0fa5-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="a0fa5-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a0fa5-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a0fa5-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a0fa5-123">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="a0fa5-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a0fa5-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0fa5-124">E_FAIL</span></span>|<span data-ttu-id="a0fa5-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="a0fa5-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a0fa5-126">如果某个方法返回 E_FAIL，则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="a0fa5-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a0fa5-127">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="a0fa5-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0fa5-128">备注</span><span class="sxs-lookup"><span data-stu-id="a0fa5-128">Remarks</span></span>  
 <span data-ttu-id="a0fa5-129">调用方可以选择从返回的列表中排除一组已知的程序集引用。</span><span class="sxs-lookup"><span data-stu-id="a0fa5-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="a0fa5-130">此集由 `pExcludeAssembliesList` 参数定义。</span><span class="sxs-lookup"><span data-stu-id="a0fa5-130">This set is defined by the `pExcludeAssembliesList` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0fa5-131">要求</span><span class="sxs-lookup"><span data-stu-id="a0fa5-131">Requirements</span></span>  
 <span data-ttu-id="a0fa5-132">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a0fa5-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0fa5-133">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a0fa5-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0fa5-134">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="a0fa5-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0fa5-135">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0fa5-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0fa5-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0fa5-136">See also</span></span>

- [<span data-ttu-id="a0fa5-137">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="a0fa5-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="a0fa5-138">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="a0fa5-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="a0fa5-139">ICLRReferenceAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="a0fa5-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
