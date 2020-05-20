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
ms.openlocfilehash: d388f366671f50c3dcb3bd9d387300dd1bbb168f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615899"
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="3187f-102">ICLRAssemblyIdentityManager::IsStronglyNamed 方法</span><span class="sxs-lookup"><span data-stu-id="3187f-102">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>
<span data-ttu-id="3187f-103">获取一个值，该值指示指定的程序集是否具有强名称。</span><span class="sxs-lookup"><span data-stu-id="3187f-103">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3187f-104">语法</span><span class="sxs-lookup"><span data-stu-id="3187f-104">Syntax</span></span>  
  
```cpp  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3187f-105">参数</span><span class="sxs-lookup"><span data-stu-id="3187f-105">Parameters</span></span>  
 `pwzAssemblyIdentity`  
 <span data-ttu-id="3187f-106">中要计算的程序集的不透明规范程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="3187f-106">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="3187f-107">[out] `true` 如果参数引用的程序集 `pwzAssemblyIdentity` 具有强名称，则为; 否则为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="3187f-107">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3187f-108">返回值</span><span class="sxs-lookup"><span data-stu-id="3187f-108">Return Value</span></span>  
  
|<span data-ttu-id="3187f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3187f-109">HRESULT</span></span>|<span data-ttu-id="3187f-110">说明</span><span class="sxs-lookup"><span data-stu-id="3187f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3187f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3187f-111">S_OK</span></span>|<span data-ttu-id="3187f-112">该方法已成功返回。</span><span class="sxs-lookup"><span data-stu-id="3187f-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="3187f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3187f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3187f-114">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="3187f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3187f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3187f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3187f-116">调用超时。</span><span class="sxs-lookup"><span data-stu-id="3187f-116">The call timed out.</span></span>|  
|<span data-ttu-id="3187f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3187f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3187f-118">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="3187f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3187f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3187f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3187f-120">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="3187f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3187f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3187f-121">E_FAIL</span></span>|<span data-ttu-id="3187f-122">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="3187f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3187f-123">如果方法返回 E_FAIL，则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="3187f-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3187f-124">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="3187f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3187f-125">要求</span><span class="sxs-lookup"><span data-stu-id="3187f-125">Requirements</span></span>  
 <span data-ttu-id="3187f-126">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3187f-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3187f-127">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3187f-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3187f-128">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="3187f-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3187f-129">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3187f-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3187f-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3187f-130">See also</span></span>

- [<span data-ttu-id="3187f-131">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="3187f-131">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
