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
ms.openlocfilehash: b0da548d5d5cc22eb6754859a802afa4d82fac89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438384"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="7aab1-102">IHostAssemblyManager::GetNonHostStoreAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="7aab1-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>
<span data-ttu-id="7aab1-103">获取到的接口指针[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)表示主机需要公共语言运行时 (CLR) 加载的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="7aab1-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aab1-104">语法</span><span class="sxs-lookup"><span data-stu-id="7aab1-104">Syntax</span></span>  
  
```  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7aab1-105">参数</span><span class="sxs-lookup"><span data-stu-id="7aab1-105">Parameters</span></span>  
 `ppReferenceList`  
 <span data-ttu-id="7aab1-106">[out]指向的地址的指针`ICLRAssemblyReferenceList`包含对该主机期望 CLR 加载的程序集的引用列表。</span><span class="sxs-lookup"><span data-stu-id="7aab1-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7aab1-107">返回值</span><span class="sxs-lookup"><span data-stu-id="7aab1-107">Return Value</span></span>  
  
|<span data-ttu-id="7aab1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7aab1-108">HRESULT</span></span>|<span data-ttu-id="7aab1-109">描述</span><span class="sxs-lookup"><span data-stu-id="7aab1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7aab1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7aab1-110">S_OK</span></span>|<span data-ttu-id="7aab1-111">`GetNonHostStoreAssemblies` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="7aab1-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="7aab1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7aab1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7aab1-113">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="7aab1-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7aab1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7aab1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7aab1-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="7aab1-115">The call timed out.</span></span>|  
|<span data-ttu-id="7aab1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7aab1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7aab1-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="7aab1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7aab1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7aab1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7aab1-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="7aab1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7aab1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7aab1-120">E_FAIL</span></span>|<span data-ttu-id="7aab1-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="7aab1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7aab1-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="7aab1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7aab1-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="7aab1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7aab1-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7aab1-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7aab1-125">没有足够的内存已可用于创建针对请求的引用列表`ICLRAssemblyReferenceList`。</span><span class="sxs-lookup"><span data-stu-id="7aab1-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7aab1-126">备注</span><span class="sxs-lookup"><span data-stu-id="7aab1-126">Remarks</span></span>  
 <span data-ttu-id="7aab1-127">CLR 使用以下准则集对引用进行解析：</span><span class="sxs-lookup"><span data-stu-id="7aab1-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
-   <span data-ttu-id="7aab1-128">首先，查询返回的程序集引用列表`GetNonHostStoreAssemblies`。</span><span class="sxs-lookup"><span data-stu-id="7aab1-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
-   <span data-ttu-id="7aab1-129">如果程序集将出现在列表中，CLR 将绑定到它正常。</span><span class="sxs-lookup"><span data-stu-id="7aab1-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
-   <span data-ttu-id="7aab1-130">如果程序集不显示在列表中，主机具有提供的实现[IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)，CLR 调用[ihostassemblystore:: Provideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)以允许主机提供要将绑定到程序集。</span><span class="sxs-lookup"><span data-stu-id="7aab1-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
-   <span data-ttu-id="7aab1-131">否则，CLR 将无法绑定到程序集。</span><span class="sxs-lookup"><span data-stu-id="7aab1-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="7aab1-132">如果主机将设置`ppReferenceList`为 null，则 CLR 首先探测全局程序集缓存中，将调用`ProvideAssembly`，然后探测应用程序基，以解析程序集引用。</span><span class="sxs-lookup"><span data-stu-id="7aab1-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7aab1-133">在初始化时 CLR 调用`GetNonHostStoreAssemblies`仅一次。</span><span class="sxs-lookup"><span data-stu-id="7aab1-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="7aab1-134">不再次调用该方法。</span><span class="sxs-lookup"><span data-stu-id="7aab1-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7aab1-135">要求</span><span class="sxs-lookup"><span data-stu-id="7aab1-135">Requirements</span></span>  
 <span data-ttu-id="7aab1-136">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7aab1-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7aab1-137">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7aab1-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7aab1-138">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7aab1-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7aab1-139">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7aab1-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aab1-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="7aab1-140">See Also</span></span>  
 [<span data-ttu-id="7aab1-141">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="7aab1-141">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="7aab1-142">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="7aab1-142">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="7aab1-143">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="7aab1-143">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
