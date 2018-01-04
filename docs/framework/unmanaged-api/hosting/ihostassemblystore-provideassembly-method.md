---
title: "IHostAssemblyStore::ProvideAssembly 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyStore.ProvideAssembly
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyStore::ProvideAssembly
helpviewer_keywords:
- ProvideAssembly method [.NET Framework hosting]
- IHostAssemblyStore::ProvideAssembly method [.NET Framework hosting]
ms.assetid: 625c3dd5-a3f0-442c-adde-310dadbb5054
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2097c1ea64e5e9a2a09e0ec57243624b05eeea65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblystoreprovideassembly-method"></a><span data-ttu-id="b33b8-102">IHostAssemblyStore::ProvideAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="b33b8-102">IHostAssemblyStore::ProvideAssembly Method</span></span>
<span data-ttu-id="b33b8-103">获取未被引用程序集的引用[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)从返回[ihostassemblymanager:: Getnonhoststoreassemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)。</span><span class="sxs-lookup"><span data-stu-id="b33b8-103">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that is returned from [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span> <span data-ttu-id="b33b8-104">公共语言运行时 (CLR) 调用`ProvideAssembly`列表中未显示每个程序集。</span><span class="sxs-lookup"><span data-stu-id="b33b8-104">The common language runtime (CLR) calls `ProvideAssembly` for each assembly that does not appear in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b33b8-105">语法</span><span class="sxs-lookup"><span data-stu-id="b33b8-105">Syntax</span></span>  
  
```  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b33b8-106">参数</span><span class="sxs-lookup"><span data-stu-id="b33b8-106">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="b33b8-107">[in]指向的指针[AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)主机使用来确定是否存在任何版本控制策略，包括某些绑定特征的实例和要绑定到的程序集。</span><span class="sxs-lookup"><span data-stu-id="b33b8-107">[in] A pointer to an [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) instance that the host uses to determine certain bind characteristics, including the presence or absence of any versioning policy, and which assembly to bind to.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="b33b8-108">[out]指向此请求的程序集的唯一标识符的`IStream`。</span><span class="sxs-lookup"><span data-stu-id="b33b8-108">[out] A pointer to a unique identifier for the requested assembly for this `IStream`.</span></span>  
  
 `pHostContext`  
 <span data-ttu-id="b33b8-109">[out]用于确定请求的程序集而无需平台的证据的特定于宿主的数据的指针调用。</span><span class="sxs-lookup"><span data-stu-id="b33b8-109">[out] A pointer to host-specific data that is used to determine the evidence of the requested assembly without the need of a platform invoke call.</span></span> <span data-ttu-id="b33b8-110">`pHostContext`对应于<xref:System.Reflection.Assembly.HostContext%2A>属性托管的<xref:System.Reflection.Assembly>类。</span><span class="sxs-lookup"><span data-stu-id="b33b8-110">`pHostContext` corresponds to the <xref:System.Reflection.Assembly.HostContext%2A> property of the managed <xref:System.Reflection.Assembly> class.</span></span>  
  
 `ppStmAssemblyImage`  
 <span data-ttu-id="b33b8-111">[out]指向的地址的指针`IStream`包含要加载的或如果找不到程序集为 null 的可移植可执行 (PE) 映像。</span><span class="sxs-lookup"><span data-stu-id="b33b8-111">[out] A pointer to the address of an `IStream` that contains the portable executable (PE) image to be loaded, or null if the assembly could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="b33b8-112">[out]指向的地址的指针`IStream`如果找不到.pdb 文件包含的程序调试 (PDB) 信息或为 null。</span><span class="sxs-lookup"><span data-stu-id="b33b8-112">[out] A pointer to the address of an `IStream` that contains the program debug (PDB) information, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b33b8-113">返回值</span><span class="sxs-lookup"><span data-stu-id="b33b8-113">Return Value</span></span>  
  
|<span data-ttu-id="b33b8-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b33b8-114">HRESULT</span></span>|<span data-ttu-id="b33b8-115">描述</span><span class="sxs-lookup"><span data-stu-id="b33b8-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b33b8-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="b33b8-116">S_OK</span></span>|<span data-ttu-id="b33b8-117">`ProvideAssembly`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="b33b8-117">`ProvideAssembly` returned successfully.</span></span>|  
|<span data-ttu-id="b33b8-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b33b8-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b33b8-119">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="b33b8-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b33b8-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b33b8-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b33b8-121">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="b33b8-121">The call timed out.</span></span>|  
|<span data-ttu-id="b33b8-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b33b8-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b33b8-123">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="b33b8-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b33b8-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b33b8-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b33b8-125">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="b33b8-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b33b8-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b33b8-126">E_FAIL</span></span>|<span data-ttu-id="b33b8-127">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="b33b8-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b33b8-128">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="b33b8-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b33b8-129">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="b33b8-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b33b8-130">COR_E_FILENOTFOUND (0X80070002)</span><span class="sxs-lookup"><span data-stu-id="b33b8-130">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="b33b8-131">找不到请求的程序集。</span><span class="sxs-lookup"><span data-stu-id="b33b8-131">The requested assembly could not be located.</span></span>|  
|<span data-ttu-id="b33b8-132">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="b33b8-132">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="b33b8-133">通过指定的缓冲区大小`pAssemblyId`不足够大以保存主机想要返回的标识符。</span><span class="sxs-lookup"><span data-stu-id="b33b8-133">The buffer size specified by `pAssemblyId` is not large enough to hold the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b33b8-134">备注</span><span class="sxs-lookup"><span data-stu-id="b33b8-134">Remarks</span></span>  
 <span data-ttu-id="b33b8-135">返回标识值`pAssemblyId`宿主指定。</span><span class="sxs-lookup"><span data-stu-id="b33b8-135">The identity value returned for `pAssemblyId` is specified by the host.</span></span> <span data-ttu-id="b33b8-136">标识符在进程的生存期内必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="b33b8-136">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="b33b8-137">CLR 使用此值流作为唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="b33b8-137">The CLR uses this value as a unique identifier for the stream.</span></span> <span data-ttu-id="b33b8-138">它会检查每个值对的值`pAssemblyId`返回到其他调用`ProvideAssembly`。</span><span class="sxs-lookup"><span data-stu-id="b33b8-138">It checks each value against the values for `pAssemblyId` returned by other calls to `ProvideAssembly`.</span></span> <span data-ttu-id="b33b8-139">如果主机返回相同`pAssemblyId`另一项的值`IStream`，CLR 将检查是否已映射了该流的内容。</span><span class="sxs-lookup"><span data-stu-id="b33b8-139">If the host returns the same `pAssemblyId` value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="b33b8-140">如果是这样，则运行时将加载映像而不是映射一个新的现有副本。</span><span class="sxs-lookup"><span data-stu-id="b33b8-140">If so, the runtime loads the existing copy of the image instead of mapping a new one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b33b8-141">惠?</span><span class="sxs-lookup"><span data-stu-id="b33b8-141">Requirements</span></span>  
 <span data-ttu-id="b33b8-142">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b33b8-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b33b8-143">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b33b8-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b33b8-144">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b33b8-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b33b8-145">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b33b8-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b33b8-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="b33b8-146">See Also</span></span>  
 [<span data-ttu-id="b33b8-147">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="b33b8-147">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="b33b8-148">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="b33b8-148">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="b33b8-149">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="b33b8-149">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
