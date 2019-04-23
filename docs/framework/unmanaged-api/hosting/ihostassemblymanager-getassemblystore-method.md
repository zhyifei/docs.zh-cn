---
title: IHostAssemblyManager::GetAssemblyStore 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35e38949ce945d93216daffd3c0d91dad6c8739b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092768"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="b09a4-102">IHostAssemblyManager::GetAssemblyStore 方法</span><span class="sxs-lookup"><span data-stu-id="b09a4-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>
<span data-ttu-id="b09a4-103">获取到的接口指针[IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) ，表示由宿主加载的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="b09a4-103">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b09a4-104">语法</span><span class="sxs-lookup"><span data-stu-id="b09a4-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b09a4-105">参数</span><span class="sxs-lookup"><span data-stu-id="b09a4-105">Parameters</span></span>  
 `ppAssemblyStore`  
 <span data-ttu-id="b09a4-106">[out]指向的函数指针`IHostAssemblyStore`实例，则为 null，如果主机不实现`IHostAssemblyStore`。</span><span class="sxs-lookup"><span data-stu-id="b09a4-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b09a4-107">返回值</span><span class="sxs-lookup"><span data-stu-id="b09a4-107">Return Value</span></span>  
  
|<span data-ttu-id="b09a4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b09a4-108">HRESULT</span></span>|<span data-ttu-id="b09a4-109">描述</span><span class="sxs-lookup"><span data-stu-id="b09a4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b09a4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b09a4-110">S_OK</span></span>|<span data-ttu-id="b09a4-111">`GetAssemblyStore` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="b09a4-111">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="b09a4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b09a4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b09a4-113">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="b09a4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b09a4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b09a4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b09a4-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="b09a4-115">The call timed out.</span></span>|  
|<span data-ttu-id="b09a4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b09a4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b09a4-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="b09a4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b09a4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b09a4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b09a4-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="b09a4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b09a4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b09a4-120">E_FAIL</span></span>|<span data-ttu-id="b09a4-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="b09a4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b09a4-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="b09a4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b09a4-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="b09a4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b09a4-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="b09a4-124">E_NOINTERFACE</span></span>|<span data-ttu-id="b09a4-125">主机未提供的实现`IHostAssemblyStore`。</span><span class="sxs-lookup"><span data-stu-id="b09a4-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b09a4-126">备注</span><span class="sxs-lookup"><span data-stu-id="b09a4-126">Remarks</span></span>  
 <span data-ttu-id="b09a4-127">`IHostAssemblyStore` 提供允许将绑定到程序集和模块独立于 CLR 的主机的方法。</span><span class="sxs-lookup"><span data-stu-id="b09a4-127">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="b09a4-128">主机通常提供程序集存储区，以允许要从文件系统以外的其他格式加载程序集。</span><span class="sxs-lookup"><span data-stu-id="b09a4-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b09a4-129">如果主机不实现`IHostAssemblyStore`，`GetAssemblyStore`应返回 E_NOINTERFACE，HRESULT 值并且应设置`ppAssemblyStore`为 null。</span><span class="sxs-lookup"><span data-stu-id="b09a4-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b09a4-130">要求</span><span class="sxs-lookup"><span data-stu-id="b09a4-130">Requirements</span></span>  
 <span data-ttu-id="b09a4-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b09a4-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b09a4-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b09a4-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b09a4-133">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b09a4-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b09a4-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b09a4-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b09a4-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="b09a4-135">See also</span></span>

- [<span data-ttu-id="b09a4-136">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="b09a4-136">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="b09a4-137">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="b09a4-137">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
