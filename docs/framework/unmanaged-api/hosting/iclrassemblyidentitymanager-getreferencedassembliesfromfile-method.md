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
ms.openlocfilehash: 3c4f673d88594e86004c6d51a4d58a0ac4642875
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615938"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a><span data-ttu-id="0e580-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="0e580-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile Method</span></span>
<span data-ttu-id="0e580-103">获取一个[ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md)实例，该实例包含程序集在指定文件路径处引用的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="0e580-103">Gets an [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e580-104">语法</span><span class="sxs-lookup"><span data-stu-id="0e580-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromFile (  
    [in]  LPCWSTR pwzFilePath,  
    [in]  DWORD   dwFlags,  
    [in]  ICLRAssemblyReferenceList   *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum  **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e580-105">参数</span><span class="sxs-lookup"><span data-stu-id="0e580-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="0e580-106">中要计算的程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="0e580-106">[in] The path to the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0e580-107">中提供用于将来的扩展性。</span><span class="sxs-lookup"><span data-stu-id="0e580-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="0e580-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT 是当前版本的公共语言运行时（CLR）支持的唯一值。</span><span class="sxs-lookup"><span data-stu-id="0e580-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="0e580-109">中指向[ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)对象的指针，该对象表示应从中排除的程序集 `ppReferenceEnum` 。</span><span class="sxs-lookup"><span data-stu-id="0e580-109">[in] A pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) object that represents assemblies that should be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="0e580-110">弄指向对象地址的指针 `ICLRReferenceAssemblyEnum` ，该对象包含程序集引用的程序集的程序集标识数据，不包括由表示的程序集 `pwzFilePath` `pExcludeAssembliesList` 。</span><span class="sxs-lookup"><span data-stu-id="0e580-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly at `pwzFilePath`, excluding the assemblies represented by `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e580-111">返回值</span><span class="sxs-lookup"><span data-stu-id="0e580-111">Return Value</span></span>  
  
|<span data-ttu-id="0e580-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0e580-112">HRESULT</span></span>|<span data-ttu-id="0e580-113">说明</span><span class="sxs-lookup"><span data-stu-id="0e580-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0e580-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="0e580-114">S_OK</span></span>|<span data-ttu-id="0e580-115">该方法已成功返回。</span><span class="sxs-lookup"><span data-stu-id="0e580-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="0e580-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0e580-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0e580-117">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="0e580-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0e580-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0e580-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0e580-119">调用超时。</span><span class="sxs-lookup"><span data-stu-id="0e580-119">The call timed out.</span></span>|  
|<span data-ttu-id="0e580-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0e580-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0e580-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="0e580-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0e580-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0e580-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0e580-123">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="0e580-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0e580-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0e580-124">E_FAIL</span></span>|<span data-ttu-id="0e580-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="0e580-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0e580-126">如果方法返回 E_FAIL，则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="0e580-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0e580-127">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="0e580-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e580-128">备注</span><span class="sxs-lookup"><span data-stu-id="0e580-128">Remarks</span></span>  
 <span data-ttu-id="0e580-129">调用方可以选择从返回的列表中排除一组已知的程序集引用。</span><span class="sxs-lookup"><span data-stu-id="0e580-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="0e580-130">此集由 `pExcludeAssembliesList` 参数定义。</span><span class="sxs-lookup"><span data-stu-id="0e580-130">This set is defined by the `pExcludeAssembliesList` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e580-131">要求</span><span class="sxs-lookup"><span data-stu-id="0e580-131">Requirements</span></span>  
 <span data-ttu-id="0e580-132">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0e580-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e580-133">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0e580-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0e580-134">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="0e580-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0e580-135">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e580-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e580-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e580-136">See also</span></span>

- [<span data-ttu-id="0e580-137">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="0e580-137">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="0e580-138">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="0e580-138">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="0e580-139">ICLRReferenceAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="0e580-139">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)
