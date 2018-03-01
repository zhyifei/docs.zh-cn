---
title: "ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList 方法"
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
- ICLRAssemblyIdentityManager.GetCLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList
helpviewer_keywords:
- GetClrAssemblyReferenceList method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList method [.NET Framework hosting]
ms.assetid: cb5ffae5-287b-4a87-9ca8-7ce3ae0601b7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eefe5ff68c7bd428c18729dcbd792b4c3cb64c2e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="a7be6-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList 方法</span><span class="sxs-lookup"><span data-stu-id="a7be6-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>
<span data-ttu-id="a7be6-103">获取到的接口指针[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)从提供的列表的部分程序集标识的实例。</span><span class="sxs-lookup"><span data-stu-id="a7be6-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7be6-104">语法</span><span class="sxs-lookup"><span data-stu-id="a7be6-104">Syntax</span></span>  
  
```  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7be6-105">参数</span><span class="sxs-lookup"><span data-stu-id="a7be6-105">Parameters</span></span>  
 `ppwzAssemblyReferences`  
 <span data-ttu-id="a7be6-106">[in]数组以 null 结尾的字符串，在窗体中的"名称、 属性 = value..."指定的部分程序集标识列表。</span><span class="sxs-lookup"><span data-stu-id="a7be6-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="a7be6-107">[in]中的项的数目`ppwzAssemblyReferences`。</span><span class="sxs-lookup"><span data-stu-id="a7be6-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="a7be6-108">[out]接口指针`ICLRAssemblyReferenceList`对象，其中包含有关列表中指定的程序集的程序集标识数据`ppwzAssemblyReferences`。</span><span class="sxs-lookup"><span data-stu-id="a7be6-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7be6-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a7be6-109">Return Value</span></span>  
  
|<span data-ttu-id="a7be6-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a7be6-110">HRESULT</span></span>|<span data-ttu-id="a7be6-111">描述</span><span class="sxs-lookup"><span data-stu-id="a7be6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a7be6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a7be6-112">S_OK</span></span>|<span data-ttu-id="a7be6-113">该方法返回成功。</span><span class="sxs-lookup"><span data-stu-id="a7be6-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="a7be6-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a7be6-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a7be6-115">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="a7be6-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a7be6-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a7be6-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a7be6-117">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="a7be6-117">The call timed out.</span></span>|  
|<span data-ttu-id="a7be6-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a7be6-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a7be6-119">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="a7be6-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a7be6-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a7be6-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a7be6-121">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="a7be6-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a7be6-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a7be6-122">E_FAIL</span></span>|<span data-ttu-id="a7be6-123">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="a7be6-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a7be6-124">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="a7be6-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a7be6-125">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="a7be6-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7be6-126">惠?</span><span class="sxs-lookup"><span data-stu-id="a7be6-126">Requirements</span></span>  
 <span data-ttu-id="a7be6-127">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a7be6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7be6-128">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a7be6-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7be6-129">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a7be6-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7be6-130">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7be6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7be6-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7be6-131">See Also</span></span>  
 [<span data-ttu-id="a7be6-132">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="a7be6-132">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="a7be6-133">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="a7be6-133">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
