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
ms.openlocfilehash: 91c9a92d83312efcfd90a15aa0a60cccb6b44d7f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134738"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="68a76-102">IHostAssemblyManager::GetAssemblyStore 方法</span><span class="sxs-lookup"><span data-stu-id="68a76-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>
<span data-ttu-id="68a76-103">获取一个接口指针，该指针指向表示宿主加载的程序集列表的[IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) 。</span><span class="sxs-lookup"><span data-stu-id="68a76-103">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68a76-104">语法</span><span class="sxs-lookup"><span data-stu-id="68a76-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68a76-105">参数</span><span class="sxs-lookup"><span data-stu-id="68a76-105">Parameters</span></span>  
 `ppAssemblyStore`  
 <span data-ttu-id="68a76-106">弄指向 `IHostAssemblyStore` 实例的函数指针，如果宿主未实现 `IHostAssemblyStore`，则为 null。</span><span class="sxs-lookup"><span data-stu-id="68a76-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68a76-107">返回值</span><span class="sxs-lookup"><span data-stu-id="68a76-107">Return Value</span></span>  
  
|<span data-ttu-id="68a76-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="68a76-108">HRESULT</span></span>|<span data-ttu-id="68a76-109">描述</span><span class="sxs-lookup"><span data-stu-id="68a76-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="68a76-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="68a76-110">S_OK</span></span>|<span data-ttu-id="68a76-111">`GetAssemblyStore` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="68a76-111">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="68a76-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="68a76-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="68a76-113">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="68a76-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="68a76-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="68a76-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="68a76-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="68a76-115">The call timed out.</span></span>|  
|<span data-ttu-id="68a76-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="68a76-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="68a76-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="68a76-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="68a76-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="68a76-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="68a76-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="68a76-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="68a76-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="68a76-120">E_FAIL</span></span>|<span data-ttu-id="68a76-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="68a76-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="68a76-122">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="68a76-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="68a76-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="68a76-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="68a76-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="68a76-124">E_NOINTERFACE</span></span>|<span data-ttu-id="68a76-125">宿主不提供 `IHostAssemblyStore`的实现。</span><span class="sxs-lookup"><span data-stu-id="68a76-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68a76-126">备注</span><span class="sxs-lookup"><span data-stu-id="68a76-126">Remarks</span></span>  
 <span data-ttu-id="68a76-127">`IHostAssemblyStore` 提供允许主机独立于 CLR 绑定到程序集和模块的方法。</span><span class="sxs-lookup"><span data-stu-id="68a76-127">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="68a76-128">主机通常提供程序集存储区，以允许从文件系统以外的其他格式加载程序集。</span><span class="sxs-lookup"><span data-stu-id="68a76-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68a76-129">如果主机未实现 `IHostAssemblyStore`，`GetAssemblyStore` 应返回 E_NOINTERFACE 的 HRESULT 值，并且应将 `ppAssemblyStore` 设置为 null。</span><span class="sxs-lookup"><span data-stu-id="68a76-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68a76-130">要求</span><span class="sxs-lookup"><span data-stu-id="68a76-130">Requirements</span></span>  
 <span data-ttu-id="68a76-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="68a76-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68a76-132">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="68a76-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68a76-133">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="68a76-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68a76-134">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68a76-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68a76-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="68a76-135">See also</span></span>

- [<span data-ttu-id="68a76-136">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="68a76-136">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="68a76-137">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="68a76-137">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
