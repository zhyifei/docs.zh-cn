---
title: "ICLRHostProtectionManager::SetEagerSerializeGrantSets 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostProtectionManager.SetEagerSerializeGrantSets
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostProtectionManager::SetEagerSerializeGrantSets
helpviewer_keywords:
- SetEagerSerializeGrantSets method [.NET Framework hosting]
- ICLRHostProtectionManager::SetEagerSerializeGrantSets method [.NET Framework hosting]
ms.assetid: d6158360-22b1-4ace-ad85-d830b9964783
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f1d2bb2ecc4ae7edb4edbaa3ff36650c70c82daf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="405c7-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets 方法</span><span class="sxs-lookup"><span data-stu-id="405c7-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="405c7-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="405c7-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="405c7-104">语法</span><span class="sxs-lookup"><span data-stu-id="405c7-104">Syntax</span></span>  
  
```  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="405c7-105">返回值</span><span class="sxs-lookup"><span data-stu-id="405c7-105">Return Value</span></span>  
  
|<span data-ttu-id="405c7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="405c7-106">HRESULT</span></span>|<span data-ttu-id="405c7-107">描述</span><span class="sxs-lookup"><span data-stu-id="405c7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="405c7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="405c7-108">S_OK</span></span>|<span data-ttu-id="405c7-109">`SetEagerSerializeGrantSets`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="405c7-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="405c7-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="405c7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="405c7-111">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="405c7-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="405c7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="405c7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="405c7-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="405c7-113">The call timed out.</span></span>|  
|<span data-ttu-id="405c7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="405c7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="405c7-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="405c7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="405c7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="405c7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="405c7-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="405c7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="405c7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="405c7-118">E_FAIL</span></span>|<span data-ttu-id="405c7-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="405c7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="405c7-120">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="405c7-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="405c7-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="405c7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="405c7-122">惠?</span><span class="sxs-lookup"><span data-stu-id="405c7-122">Requirements</span></span>  
 <span data-ttu-id="405c7-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="405c7-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="405c7-124">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="405c7-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="405c7-125">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="405c7-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="405c7-126">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="405c7-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="405c7-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="405c7-127">See Also</span></span>  
 [<span data-ttu-id="405c7-128">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="405c7-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="405c7-129">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="405c7-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
