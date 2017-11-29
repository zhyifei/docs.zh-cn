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
ms.openlocfilehash: a9b1e314f7af6edf3d8db00780105dff95868a6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrhostprotectionmanagerseteagerserializegrantsets-method"></a><span data-ttu-id="ed8ac-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets 方法</span><span class="sxs-lookup"><span data-stu-id="ed8ac-102">ICLRHostProtectionManager::SetEagerSerializeGrantSets Method</span></span>
<span data-ttu-id="ed8ac-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="ed8ac-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed8ac-104">语法</span><span class="sxs-lookup"><span data-stu-id="ed8ac-104">Syntax</span></span>  
  
```  
HRESULT SetEagerSerializeGrantSets ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ed8ac-105">返回值</span><span class="sxs-lookup"><span data-stu-id="ed8ac-105">Return Value</span></span>  
  
|<span data-ttu-id="ed8ac-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ed8ac-106">HRESULT</span></span>|<span data-ttu-id="ed8ac-107">描述</span><span class="sxs-lookup"><span data-stu-id="ed8ac-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ed8ac-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed8ac-108">S_OK</span></span>|<span data-ttu-id="ed8ac-109">`SetEagerSerializeGrantSets`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="ed8ac-109">`SetEagerSerializeGrantSets` returned successfully.</span></span>|  
|<span data-ttu-id="ed8ac-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ed8ac-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ed8ac-111">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="ed8ac-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ed8ac-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ed8ac-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ed8ac-113">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="ed8ac-113">The call timed out.</span></span>|  
|<span data-ttu-id="ed8ac-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ed8ac-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ed8ac-115">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="ed8ac-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ed8ac-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ed8ac-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ed8ac-117">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="ed8ac-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ed8ac-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ed8ac-118">E_FAIL</span></span>|<span data-ttu-id="ed8ac-119">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="ed8ac-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ed8ac-120">方法返回 E_FAIL 后，CLR 不再进程内中使用。</span><span class="sxs-lookup"><span data-stu-id="ed8ac-120">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ed8ac-121">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="ed8ac-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ed8ac-122">要求</span><span class="sxs-lookup"><span data-stu-id="ed8ac-122">Requirements</span></span>  
 <span data-ttu-id="ed8ac-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ed8ac-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed8ac-124">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ed8ac-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed8ac-125">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ed8ac-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed8ac-126">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed8ac-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed8ac-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed8ac-127">See Also</span></span>  
 [<span data-ttu-id="ed8ac-128">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="ed8ac-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="ed8ac-129">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="ed8ac-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
