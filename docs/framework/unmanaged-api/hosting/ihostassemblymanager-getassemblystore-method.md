---
title: "IHostAssemblyManager::GetAssemblyStore 方法"
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
- IHostAssemblyManager.GetAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetAssemblyStore
helpviewer_keywords:
- IHostAssemblyManager::GetAssemblyStore method [.NET Framework hosting]
- GetAssemblyStore method [.NET Framework hosting]
ms.assetid: d0f74593-9bb1-4a11-8096-e29734b20698
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 347947622601475147663b8838bef5f36a1f7e32
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="d4091-102">IHostAssemblyManager::GetAssemblyStore 方法</span><span class="sxs-lookup"><span data-stu-id="d4091-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>
<span data-ttu-id="d4091-103">获取到的接口指针[IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)表示主机加载的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="d4091-103">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4091-104">语法</span><span class="sxs-lookup"><span data-stu-id="d4091-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4091-105">参数</span><span class="sxs-lookup"><span data-stu-id="d4091-105">Parameters</span></span>  
 `ppAssemblyStore`  
 <span data-ttu-id="d4091-106">[out]函数指针到`IHostAssemblyStore`实例，则为 null，如果主机不实现`IHostAssemblyStore`。</span><span class="sxs-lookup"><span data-stu-id="d4091-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4091-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d4091-107">Return Value</span></span>  
  
|<span data-ttu-id="d4091-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d4091-108">HRESULT</span></span>|<span data-ttu-id="d4091-109">描述</span><span class="sxs-lookup"><span data-stu-id="d4091-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d4091-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d4091-110">S_OK</span></span>|<span data-ttu-id="d4091-111">`GetAssemblyStore`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="d4091-111">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="d4091-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d4091-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d4091-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d4091-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d4091-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d4091-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d4091-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="d4091-115">The call timed out.</span></span>|  
|<span data-ttu-id="d4091-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d4091-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d4091-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="d4091-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d4091-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d4091-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d4091-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="d4091-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d4091-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d4091-120">E_FAIL</span></span>|<span data-ttu-id="d4091-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d4091-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d4091-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="d4091-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d4091-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d4091-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d4091-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="d4091-124">E_NOINTERFACE</span></span>|<span data-ttu-id="d4091-125">主机未提供的实现`IHostAssemblyStore`。</span><span class="sxs-lookup"><span data-stu-id="d4091-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4091-126">备注</span><span class="sxs-lookup"><span data-stu-id="d4091-126">Remarks</span></span>  
 <span data-ttu-id="d4091-127">`IHostAssemblyStore`提供使主机可绑定到程序集和独立于 CLR 模块的方法。</span><span class="sxs-lookup"><span data-stu-id="d4091-127">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="d4091-128">主机通常提供程序集存储区，以允许要从文件系统以外的格式加载程序集。</span><span class="sxs-lookup"><span data-stu-id="d4091-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4091-129">如果主机不实现`IHostAssemblyStore`，`GetAssemblyStore`应返回 HRESULT 值的 E_NOINTERFACE，并且应设置`ppAssemblyStore`为 null。</span><span class="sxs-lookup"><span data-stu-id="d4091-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4091-130">惠?</span><span class="sxs-lookup"><span data-stu-id="d4091-130">Requirements</span></span>  
 <span data-ttu-id="d4091-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d4091-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4091-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d4091-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d4091-133">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d4091-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d4091-134">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4091-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4091-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4091-135">See Also</span></span>  
 [<span data-ttu-id="d4091-136">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="d4091-136">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="d4091-137">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="d4091-137">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
