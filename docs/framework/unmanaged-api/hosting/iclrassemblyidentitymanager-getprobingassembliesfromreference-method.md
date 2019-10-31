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
ms.openlocfilehash: c8c3ca3716d97703051846f104be0f783136588a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126720"
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a><span data-ttu-id="9e2be-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference 方法</span><span class="sxs-lookup"><span data-stu-id="9e2be-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Method</span></span>
<span data-ttu-id="9e2be-103">获取具有指定标识类型的程序集所引用的程序集标识的[ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)枚举器。</span><span class="sxs-lookup"><span data-stu-id="9e2be-103">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e2be-104">语法</span><span class="sxs-lookup"><span data-stu-id="9e2be-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e2be-105">参数</span><span class="sxs-lookup"><span data-stu-id="9e2be-105">Parameters</span></span>  
 `dwMachineType`  
 <span data-ttu-id="9e2be-106">中一个有效的值，该值指定处理器体系结构（如 WinNT 中所定义）。</span><span class="sxs-lookup"><span data-stu-id="9e2be-106">[in] A valid value that specifies the processor architecture, as defined in WinNT.h.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9e2be-107">中提供用于将来的扩展性。</span><span class="sxs-lookup"><span data-stu-id="9e2be-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="9e2be-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT 是当前版本的公共语言运行时（CLR）支持的唯一值。</span><span class="sxs-lookup"><span data-stu-id="9e2be-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzReferenceIdentity`  
 <span data-ttu-id="9e2be-109">中不透明的程序集绑定标识，通常是从对[ICLRAssemblyIdentityManager：： GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)或[ICLRAssemblyIdentityManager：： GetBindingIdentityFromStream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)方法的调用返回的。</span><span class="sxs-lookup"><span data-stu-id="9e2be-109">[in] An opaque assembly binding identity, typically returned from a call to the [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) or [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) method.</span></span>  
  
 `ppProbingAssemblyEnum`  
 <span data-ttu-id="9e2be-110">弄一个指向 `ICLRProbingAssemblyEnum` 枚举器的接口指针，该枚举数包含对由 `pwzReferenceIdentity`标识的程序集引用的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="9e2be-110">[out] An interface pointer to an `ICLRProbingAssemblyEnum` enumerator that contains references to the assemblies referenced by the assembly identified by `pwzReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e2be-111">返回值</span><span class="sxs-lookup"><span data-stu-id="9e2be-111">Return Value</span></span>  
  
|<span data-ttu-id="9e2be-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9e2be-112">HRESULT</span></span>|<span data-ttu-id="9e2be-113">描述</span><span class="sxs-lookup"><span data-stu-id="9e2be-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9e2be-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9e2be-114">S_OK</span></span>|<span data-ttu-id="9e2be-115">方法已成功返回。</span><span class="sxs-lookup"><span data-stu-id="9e2be-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="9e2be-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9e2be-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9e2be-117">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="9e2be-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9e2be-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9e2be-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9e2be-119">调用超时。</span><span class="sxs-lookup"><span data-stu-id="9e2be-119">The call timed out.</span></span>|  
|<span data-ttu-id="9e2be-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9e2be-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9e2be-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="9e2be-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9e2be-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9e2be-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9e2be-123">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="9e2be-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9e2be-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9e2be-124">E_FAIL</span></span>|<span data-ttu-id="9e2be-125">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="9e2be-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9e2be-126">如果某个方法返回 E_FAIL，则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="9e2be-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9e2be-127">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="9e2be-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9e2be-128">要求</span><span class="sxs-lookup"><span data-stu-id="9e2be-128">Requirements</span></span>  
 <span data-ttu-id="9e2be-129">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9e2be-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e2be-130">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9e2be-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9e2be-131">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="9e2be-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e2be-132">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e2be-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e2be-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e2be-133">See also</span></span>

- [<span data-ttu-id="9e2be-134">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="9e2be-134">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="9e2be-135">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="9e2be-135">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="9e2be-136">ICLRProbingAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="9e2be-136">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
