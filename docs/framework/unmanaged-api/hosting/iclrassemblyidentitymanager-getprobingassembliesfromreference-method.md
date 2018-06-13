---
title: ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26423837c173b5f18282a8aa480ae92ecc452489
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435649"
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a><span data-ttu-id="2dfb7-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference 方法</span><span class="sxs-lookup"><span data-stu-id="2dfb7-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Method</span></span>
<span data-ttu-id="2dfb7-103">获取[ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)由与指定的标识类型的程序集引用的程序集标识的枚举数。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-103">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dfb7-104">语法</span><span class="sxs-lookup"><span data-stu-id="2dfb7-104">Syntax</span></span>  
  
```  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2dfb7-105">参数</span><span class="sxs-lookup"><span data-stu-id="2dfb7-105">Parameters</span></span>  
 `dwMachineType`  
 <span data-ttu-id="2dfb7-106">[in]一个有效的值，指定处理器体系结构，如在 WinNT.h 中定义。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-106">[in] A valid value that specifies the processor architecture, as defined in WinNT.h.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="2dfb7-107">[in]提供以用于将来扩展。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="2dfb7-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT 是公共语言运行时 (CLR) 的当前版本支持的唯一值。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzReferenceIdentity`  
 <span data-ttu-id="2dfb7-109">[in]不透明的程序集绑定的标识，通常从调用返回[iclrassemblyidentitymanager:: Getbindingidentityfromfile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)或[iclrassemblyidentitymanager:: Getbindingidentityfromstream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-109">[in] An opaque assembly binding identity, typically returned from a call to the [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) or [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) method.</span></span>  
  
 `ppProbingAssemblyEnum`  
 <span data-ttu-id="2dfb7-110">[out]接口指针`ICLRProbingAssemblyEnum`包含对标识的程序集引用的程序集的引用的枚举器`pwzReferenceIdentity`。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-110">[out] An interface pointer to an `ICLRProbingAssemblyEnum` enumerator that contains references to the assemblies referenced by the assembly identified by `pwzReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2dfb7-111">返回值</span><span class="sxs-lookup"><span data-stu-id="2dfb7-111">Return Value</span></span>  
  
|<span data-ttu-id="2dfb7-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2dfb7-112">HRESULT</span></span>|<span data-ttu-id="2dfb7-113">描述</span><span class="sxs-lookup"><span data-stu-id="2dfb7-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2dfb7-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="2dfb7-114">S_OK</span></span>|<span data-ttu-id="2dfb7-115">该方法返回成功。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="2dfb7-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2dfb7-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2dfb7-117">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2dfb7-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2dfb7-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2dfb7-119">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-119">The call timed out.</span></span>|  
|<span data-ttu-id="2dfb7-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2dfb7-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2dfb7-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2dfb7-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2dfb7-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2dfb7-123">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2dfb7-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2dfb7-124">E_FAIL</span></span>|<span data-ttu-id="2dfb7-125">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2dfb7-126">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2dfb7-127">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2dfb7-128">要求</span><span class="sxs-lookup"><span data-stu-id="2dfb7-128">Requirements</span></span>  
 <span data-ttu-id="2dfb7-129">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dfb7-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2dfb7-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2dfb7-131">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2dfb7-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2dfb7-132">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2dfb7-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dfb7-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="2dfb7-133">See Also</span></span>  
 [<span data-ttu-id="2dfb7-134">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="2dfb7-134">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="2dfb7-135">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="2dfb7-135">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="2dfb7-136">ICLRProbingAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="2dfb7-136">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
