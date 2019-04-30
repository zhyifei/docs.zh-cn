---
title: IHostAssemblyStore::ProvideAssembly 方法
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideAssembly
helpviewer_keywords:
- ProvideAssembly method [.NET Framework hosting]
- IHostAssemblyStore::ProvideAssembly method [.NET Framework hosting]
ms.assetid: 625c3dd5-a3f0-442c-adde-310dadbb5054
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62a8be1e330338043df50bd80576b5aa65447b9c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61951757"
---
# <a name="ihostassemblystoreprovideassembly-method"></a><span data-ttu-id="68dff-102">IHostAssemblyStore::ProvideAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="68dff-102">IHostAssemblyStore::ProvideAssembly Method</span></span>
<span data-ttu-id="68dff-103">获取未被引用程序集的引用[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) ，则返回从[ihostassemblymanager:: Getnonhoststoreassemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)。</span><span class="sxs-lookup"><span data-stu-id="68dff-103">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that is returned from [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span> <span data-ttu-id="68dff-104">公共语言运行时 (CLR) 调用`ProvideAssembly`每个程序集未显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="68dff-104">The common language runtime (CLR) calls `ProvideAssembly` for each assembly that does not appear in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68dff-105">语法</span><span class="sxs-lookup"><span data-stu-id="68dff-105">Syntax</span></span>  
  
```  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68dff-106">参数</span><span class="sxs-lookup"><span data-stu-id="68dff-106">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="68dff-107">[in]一个指向[AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)主机用于确定是否存在任何版本控制策略，包括某些绑定特征的实例和要绑定到的程序集。</span><span class="sxs-lookup"><span data-stu-id="68dff-107">[in] A pointer to an [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) instance that the host uses to determine certain bind characteristics, including the presence or absence of any versioning policy, and which assembly to bind to.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="68dff-108">[out]指向此请求的程序集的唯一标识符的`IStream`。</span><span class="sxs-lookup"><span data-stu-id="68dff-108">[out] A pointer to a unique identifier for the requested assembly for this `IStream`.</span></span>  
  
 `pHostContext`  
 <span data-ttu-id="68dff-109">[out]用于确定无需使用一个平台，请求的程序集的证据的特定于宿主的数据的指针调用来调用。</span><span class="sxs-lookup"><span data-stu-id="68dff-109">[out] A pointer to host-specific data that is used to determine the evidence of the requested assembly without the need of a platform invoke call.</span></span> <span data-ttu-id="68dff-110">`pHostContext` 对应于<xref:System.Reflection.Assembly.HostContext%2A>的托管属性<xref:System.Reflection.Assembly>类。</span><span class="sxs-lookup"><span data-stu-id="68dff-110">`pHostContext` corresponds to the <xref:System.Reflection.Assembly.HostContext%2A> property of the managed <xref:System.Reflection.Assembly> class.</span></span>  
  
 `ppStmAssemblyImage`  
 <span data-ttu-id="68dff-111">[out]指向的地址的指针`IStream`，其中包含要加载，或者如果找不到程序集，则为 null 的可移植可执行 (PE) 映像。</span><span class="sxs-lookup"><span data-stu-id="68dff-111">[out] A pointer to the address of an `IStream` that contains the portable executable (PE) image to be loaded, or null if the assembly could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="68dff-112">[out]指向的地址的指针`IStream`如果找不到.pdb 文件包含的程序调试 (PDB) 的信息或为 null。</span><span class="sxs-lookup"><span data-stu-id="68dff-112">[out] A pointer to the address of an `IStream` that contains the program debug (PDB) information, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68dff-113">返回值</span><span class="sxs-lookup"><span data-stu-id="68dff-113">Return Value</span></span>  
  
|<span data-ttu-id="68dff-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="68dff-114">HRESULT</span></span>|<span data-ttu-id="68dff-115">描述</span><span class="sxs-lookup"><span data-stu-id="68dff-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="68dff-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="68dff-116">S_OK</span></span>|<span data-ttu-id="68dff-117">`ProvideAssembly` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="68dff-117">`ProvideAssembly` returned successfully.</span></span>|  
|<span data-ttu-id="68dff-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="68dff-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="68dff-119">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="68dff-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="68dff-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="68dff-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="68dff-121">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="68dff-121">The call timed out.</span></span>|  
|<span data-ttu-id="68dff-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="68dff-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="68dff-123">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="68dff-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="68dff-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="68dff-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="68dff-125">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="68dff-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="68dff-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="68dff-126">E_FAIL</span></span>|<span data-ttu-id="68dff-127">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="68dff-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="68dff-128">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="68dff-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="68dff-129">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="68dff-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="68dff-130">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="68dff-130">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="68dff-131">找不到请求的程序集。</span><span class="sxs-lookup"><span data-stu-id="68dff-131">The requested assembly could not be located.</span></span>|  
|<span data-ttu-id="68dff-132">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="68dff-132">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="68dff-133">指定的缓冲区大小`pAssemblyId`不足够大以保存宿主希望返回的标识符。</span><span class="sxs-lookup"><span data-stu-id="68dff-133">The buffer size specified by `pAssemblyId` is not large enough to hold the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68dff-134">备注</span><span class="sxs-lookup"><span data-stu-id="68dff-134">Remarks</span></span>  
 <span data-ttu-id="68dff-135">返回标识值`pAssemblyId`host 所指定。</span><span class="sxs-lookup"><span data-stu-id="68dff-135">The identity value returned for `pAssemblyId` is specified by the host.</span></span> <span data-ttu-id="68dff-136">标识符在进程生存期内必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="68dff-136">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="68dff-137">CLR 使用此值将流作为唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="68dff-137">The CLR uses this value as a unique identifier for the stream.</span></span> <span data-ttu-id="68dff-138">它会检查每个值的值与`pAssemblyId`返回的其他调用`ProvideAssembly`。</span><span class="sxs-lookup"><span data-stu-id="68dff-138">It checks each value against the values for `pAssemblyId` returned by other calls to `ProvideAssembly`.</span></span> <span data-ttu-id="68dff-139">如果主机返回相同`pAssemblyId`值的另一个`IStream`，CLR 将检查是否已映射了该流的内容。</span><span class="sxs-lookup"><span data-stu-id="68dff-139">If the host returns the same `pAssemblyId` value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="68dff-140">如果是这样，在运行时加载而不是映射新映像的现有副本。</span><span class="sxs-lookup"><span data-stu-id="68dff-140">If so, the runtime loads the existing copy of the image instead of mapping a new one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68dff-141">要求</span><span class="sxs-lookup"><span data-stu-id="68dff-141">Requirements</span></span>  
 <span data-ttu-id="68dff-142">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="68dff-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68dff-143">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="68dff-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68dff-144">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="68dff-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68dff-145">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68dff-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68dff-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="68dff-146">See also</span></span>

- [<span data-ttu-id="68dff-147">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="68dff-147">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="68dff-148">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="68dff-148">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="68dff-149">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="68dff-149">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
