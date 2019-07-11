---
title: IHostAssemblyManager::GetNonHostStoreAssemblies 方法
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetNonHostStoreAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies
helpviewer_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies method [.NET Framework hosting]
- GetNonHostStoreAssemblies method [.NET Framework hosting]
ms.assetid: d2250b38-c76a-40ce-80c8-ba45149886e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3680721c70ab69776c973913d929f7bdd9db3909
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779446"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="67fcf-102">IHostAssemblyManager::GetNonHostStoreAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="67fcf-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>
<span data-ttu-id="67fcf-103">获取到的接口指针[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)表示主机需要公共语言运行时 (CLR) 加载的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="67fcf-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67fcf-104">语法</span><span class="sxs-lookup"><span data-stu-id="67fcf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67fcf-105">参数</span><span class="sxs-lookup"><span data-stu-id="67fcf-105">Parameters</span></span>  
 `ppReferenceList`  
 <span data-ttu-id="67fcf-106">[out]指向的地址的指针`ICLRAssemblyReferenceList`，其中包含一系列主机需要 CLR 加载的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="67fcf-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67fcf-107">返回值</span><span class="sxs-lookup"><span data-stu-id="67fcf-107">Return Value</span></span>  
  
|<span data-ttu-id="67fcf-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="67fcf-108">HRESULT</span></span>|<span data-ttu-id="67fcf-109">描述</span><span class="sxs-lookup"><span data-stu-id="67fcf-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="67fcf-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="67fcf-110">S_OK</span></span>|<span data-ttu-id="67fcf-111">`GetNonHostStoreAssemblies` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="67fcf-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="67fcf-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="67fcf-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="67fcf-113">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="67fcf-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="67fcf-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="67fcf-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="67fcf-115">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="67fcf-115">The call timed out.</span></span>|  
|<span data-ttu-id="67fcf-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="67fcf-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="67fcf-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="67fcf-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="67fcf-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="67fcf-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="67fcf-119">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="67fcf-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="67fcf-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="67fcf-120">E_FAIL</span></span>|<span data-ttu-id="67fcf-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="67fcf-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="67fcf-122">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="67fcf-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="67fcf-123">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="67fcf-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="67fcf-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="67fcf-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="67fcf-125">没有足够的内存已可用于创建针对所请求的引用列表`ICLRAssemblyReferenceList`。</span><span class="sxs-lookup"><span data-stu-id="67fcf-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67fcf-126">备注</span><span class="sxs-lookup"><span data-stu-id="67fcf-126">Remarks</span></span>  
 <span data-ttu-id="67fcf-127">CLR 使用以下指导原则集引用进行解析：</span><span class="sxs-lookup"><span data-stu-id="67fcf-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
- <span data-ttu-id="67fcf-128">首先，它会查询返回的程序集引用列表`GetNonHostStoreAssemblies`。</span><span class="sxs-lookup"><span data-stu-id="67fcf-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
- <span data-ttu-id="67fcf-129">如果该程序集出现在列表中，CLR 将绑定到其正常。</span><span class="sxs-lookup"><span data-stu-id="67fcf-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
- <span data-ttu-id="67fcf-130">如果程序集不会显示在列表中，并且主机具有提供的实现[IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)，CLR 将调用[ihostassemblystore:: Provideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)以允许主机提供要将绑定到程序集。</span><span class="sxs-lookup"><span data-stu-id="67fcf-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
- <span data-ttu-id="67fcf-131">否则，CLR 将无法将绑定到程序集。</span><span class="sxs-lookup"><span data-stu-id="67fcf-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="67fcf-132">如果主机设置`ppReferenceList`为 null，则 CLR 首先探测全局程序集缓存中，并调用`ProvideAssembly`，然后探测应用程序基，若要解决的程序集引用。</span><span class="sxs-lookup"><span data-stu-id="67fcf-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67fcf-133">CLR 调用时初始化，`GetNonHostStoreAssemblies`仅一次。</span><span class="sxs-lookup"><span data-stu-id="67fcf-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="67fcf-134">不再次调用该方法。</span><span class="sxs-lookup"><span data-stu-id="67fcf-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67fcf-135">要求</span><span class="sxs-lookup"><span data-stu-id="67fcf-135">Requirements</span></span>  
 <span data-ttu-id="67fcf-136">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="67fcf-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67fcf-137">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="67fcf-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67fcf-138">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="67fcf-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67fcf-139">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67fcf-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67fcf-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="67fcf-140">See also</span></span>

- [<span data-ttu-id="67fcf-141">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="67fcf-141">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="67fcf-142">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="67fcf-142">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="67fcf-143">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="67fcf-143">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
