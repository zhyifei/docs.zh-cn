---
title: "ICLRAssemblyIdentityManager::IsStronglyNamed 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager.IsStronglyNamed
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager::IsStronglyNamed
helpviewer_keywords:
- IsStronglyNamed method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::IsStronglyNamed method [.NET Framework hosting]
ms.assetid: 954bd386-2076-4d00-9d46-38c728aa9cab
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1cb727d9144fc3364a04cd5b9064527c55f5ee79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="154f4-102">ICLRAssemblyIdentityManager::IsStronglyNamed 方法</span><span class="sxs-lookup"><span data-stu-id="154f4-102">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>
<span data-ttu-id="154f4-103">获取一个值，该值指示指定的程序集具有强名称。</span><span class="sxs-lookup"><span data-stu-id="154f4-103">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="154f4-104">语法</span><span class="sxs-lookup"><span data-stu-id="154f4-104">Syntax</span></span>  
  
```  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="154f4-105">参数</span><span class="sxs-lookup"><span data-stu-id="154f4-105">Parameters</span></span>  
 `pwzAssemblyIdentity`  
 <span data-ttu-id="154f4-106">[in]要计算的程序集不透明规范的程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="154f4-106">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="154f4-107">[out]`true`，如果引用了程序集`pwzAssemblyIdentity`参数是强命名; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="154f4-107">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="154f4-108">返回值</span><span class="sxs-lookup"><span data-stu-id="154f4-108">Return Value</span></span>  
  
|<span data-ttu-id="154f4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="154f4-109">HRESULT</span></span>|<span data-ttu-id="154f4-110">描述</span><span class="sxs-lookup"><span data-stu-id="154f4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="154f4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="154f4-111">S_OK</span></span>|<span data-ttu-id="154f4-112">该方法返回成功。</span><span class="sxs-lookup"><span data-stu-id="154f4-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="154f4-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="154f4-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="154f4-114">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="154f4-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="154f4-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="154f4-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="154f4-116">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="154f4-116">The call timed out.</span></span>|  
|<span data-ttu-id="154f4-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="154f4-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="154f4-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="154f4-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="154f4-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="154f4-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="154f4-120">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="154f4-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="154f4-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="154f4-121">E_FAIL</span></span>|<span data-ttu-id="154f4-122">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="154f4-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="154f4-123">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="154f4-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="154f4-124">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="154f4-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="154f4-125">惠?</span><span class="sxs-lookup"><span data-stu-id="154f4-125">Requirements</span></span>  
 <span data-ttu-id="154f4-126">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="154f4-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="154f4-127">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="154f4-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="154f4-128">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="154f4-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="154f4-129">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="154f4-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="154f4-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="154f4-130">See Also</span></span>  
 [<span data-ttu-id="154f4-131">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="154f4-131">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
