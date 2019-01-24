---
title: ICLRAssemblyIdentityManager::IsStronglyNamed 方法
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.IsStronglyNamed
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::IsStronglyNamed
helpviewer_keywords:
- IsStronglyNamed method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::IsStronglyNamed method [.NET Framework hosting]
ms.assetid: 954bd386-2076-4d00-9d46-38c728aa9cab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a958e38857d2407930cb8c03a08eabdf6574cda9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563881"
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="96cf2-102">ICLRAssemblyIdentityManager::IsStronglyNamed 方法</span><span class="sxs-lookup"><span data-stu-id="96cf2-102">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>
<span data-ttu-id="96cf2-103">获取一个值，该值指示是否指定的程序集具有强名称。</span><span class="sxs-lookup"><span data-stu-id="96cf2-103">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96cf2-104">语法</span><span class="sxs-lookup"><span data-stu-id="96cf2-104">Syntax</span></span>  
  
```  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96cf2-105">参数</span><span class="sxs-lookup"><span data-stu-id="96cf2-105">Parameters</span></span>  
 `pwzAssemblyIdentity`  
 <span data-ttu-id="96cf2-106">[in]不透明规范的程序集标识要评估的程序集的数据。</span><span class="sxs-lookup"><span data-stu-id="96cf2-106">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="96cf2-107">[out]`true`，如果引用的程序集`pwzAssemblyIdentity`参数是强名称为; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="96cf2-107">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96cf2-108">返回值</span><span class="sxs-lookup"><span data-stu-id="96cf2-108">Return Value</span></span>  
  
|<span data-ttu-id="96cf2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="96cf2-109">HRESULT</span></span>|<span data-ttu-id="96cf2-110">描述</span><span class="sxs-lookup"><span data-stu-id="96cf2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="96cf2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="96cf2-111">S_OK</span></span>|<span data-ttu-id="96cf2-112">该方法成功返回。</span><span class="sxs-lookup"><span data-stu-id="96cf2-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="96cf2-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="96cf2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="96cf2-114">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="96cf2-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="96cf2-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="96cf2-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="96cf2-116">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="96cf2-116">The call timed out.</span></span>|  
|<span data-ttu-id="96cf2-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="96cf2-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="96cf2-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="96cf2-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="96cf2-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="96cf2-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="96cf2-120">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="96cf2-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="96cf2-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="96cf2-121">E_FAIL</span></span>|<span data-ttu-id="96cf2-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="96cf2-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="96cf2-123">如果方法返回 E_FAIL，CLR 不再在该过程中可用。</span><span class="sxs-lookup"><span data-stu-id="96cf2-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="96cf2-124">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="96cf2-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="96cf2-125">要求</span><span class="sxs-lookup"><span data-stu-id="96cf2-125">Requirements</span></span>  
 <span data-ttu-id="96cf2-126">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="96cf2-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96cf2-127">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="96cf2-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="96cf2-128">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="96cf2-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96cf2-129">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96cf2-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96cf2-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="96cf2-130">See also</span></span>
- [<span data-ttu-id="96cf2-131">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="96cf2-131">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
