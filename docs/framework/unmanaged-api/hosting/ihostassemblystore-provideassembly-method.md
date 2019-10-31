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
ms.openlocfilehash: a93d700c9c398076d87156cd2eb9c6d0d08cccfd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124490"
---
# <a name="ihostassemblystoreprovideassembly-method"></a><span data-ttu-id="475a6-102">IHostAssemblyStore::ProvideAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="475a6-102">IHostAssemblyStore::ProvideAssembly Method</span></span>
<span data-ttu-id="475a6-103">获取对程序集的引用，该程序集未由从[IHostAssemblyManager：： GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)返回的[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)引用。</span><span class="sxs-lookup"><span data-stu-id="475a6-103">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that is returned from [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span> <span data-ttu-id="475a6-104">公共语言运行时（CLR）对列表中未显示的每个程序集调用 `ProvideAssembly`。</span><span class="sxs-lookup"><span data-stu-id="475a6-104">The common language runtime (CLR) calls `ProvideAssembly` for each assembly that does not appear in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="475a6-105">语法</span><span class="sxs-lookup"><span data-stu-id="475a6-105">Syntax</span></span>  
  
```cpp  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="475a6-106">参数</span><span class="sxs-lookup"><span data-stu-id="475a6-106">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="475a6-107">中指向[AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)实例的指针，主机使用该实例来确定特定的绑定特征，包括是否存在任何版本控制策略以及要绑定到的程序集。</span><span class="sxs-lookup"><span data-stu-id="475a6-107">[in] A pointer to an [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) instance that the host uses to determine certain bind characteristics, including the presence or absence of any versioning policy, and which assembly to bind to.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="475a6-108">弄一个指针，指向该 `IStream`所请求的程序集的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="475a6-108">[out] A pointer to a unique identifier for the requested assembly for this `IStream`.</span></span>  
  
 `pHostContext`  
 <span data-ttu-id="475a6-109">弄指向特定于主机的数据的指针，用于在不需要平台调用的情况下确定请求的程序集的证据。</span><span class="sxs-lookup"><span data-stu-id="475a6-109">[out] A pointer to host-specific data that is used to determine the evidence of the requested assembly without the need of a platform invoke call.</span></span> <span data-ttu-id="475a6-110">`pHostContext` 对应于托管 <xref:System.Reflection.Assembly> 类的 <xref:System.Reflection.Assembly.HostContext%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="475a6-110">`pHostContext` corresponds to the <xref:System.Reflection.Assembly.HostContext%2A> property of the managed <xref:System.Reflection.Assembly> class.</span></span>  
  
 `ppStmAssemblyImage`  
 <span data-ttu-id="475a6-111">弄指向包含要加载的可移植可执行（PE）映像的 `IStream` 的地址的指针; 如果找不到该程序集，则为 null。</span><span class="sxs-lookup"><span data-stu-id="475a6-111">[out] A pointer to the address of an `IStream` that contains the portable executable (PE) image to be loaded, or null if the assembly could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="475a6-112">弄指向包含程序调试（PDB）信息的 `IStream` 的地址的指针; 如果找不到 .pdb 文件，则为 null。</span><span class="sxs-lookup"><span data-stu-id="475a6-112">[out] A pointer to the address of an `IStream` that contains the program debug (PDB) information, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="475a6-113">返回值</span><span class="sxs-lookup"><span data-stu-id="475a6-113">Return Value</span></span>  
  
|<span data-ttu-id="475a6-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="475a6-114">HRESULT</span></span>|<span data-ttu-id="475a6-115">描述</span><span class="sxs-lookup"><span data-stu-id="475a6-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="475a6-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="475a6-116">S_OK</span></span>|<span data-ttu-id="475a6-117">`ProvideAssembly` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="475a6-117">`ProvideAssembly` returned successfully.</span></span>|  
|<span data-ttu-id="475a6-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="475a6-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="475a6-119">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="475a6-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="475a6-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="475a6-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="475a6-121">调用超时。</span><span class="sxs-lookup"><span data-stu-id="475a6-121">The call timed out.</span></span>|  
|<span data-ttu-id="475a6-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="475a6-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="475a6-123">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="475a6-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="475a6-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="475a6-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="475a6-125">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="475a6-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="475a6-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="475a6-126">E_FAIL</span></span>|<span data-ttu-id="475a6-127">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="475a6-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="475a6-128">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="475a6-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="475a6-129">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="475a6-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="475a6-130">COR_E_FILENOTFOUND （0x80070002）</span><span class="sxs-lookup"><span data-stu-id="475a6-130">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="475a6-131">找不到请求的程序集。</span><span class="sxs-lookup"><span data-stu-id="475a6-131">The requested assembly could not be located.</span></span>|  
|<span data-ttu-id="475a6-132">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="475a6-132">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="475a6-133">`pAssemblyId` 指定的缓冲区大小不够大，无法容纳主机需要返回的标识符。</span><span class="sxs-lookup"><span data-stu-id="475a6-133">The buffer size specified by `pAssemblyId` is not large enough to hold the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="475a6-134">备注</span><span class="sxs-lookup"><span data-stu-id="475a6-134">Remarks</span></span>  
 <span data-ttu-id="475a6-135">为 `pAssemblyId` 返回的标识值由主机指定。</span><span class="sxs-lookup"><span data-stu-id="475a6-135">The identity value returned for `pAssemblyId` is specified by the host.</span></span> <span data-ttu-id="475a6-136">标识符在进程的生存期内必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="475a6-136">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="475a6-137">CLR 使用此值作为流的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="475a6-137">The CLR uses this value as a unique identifier for the stream.</span></span> <span data-ttu-id="475a6-138">它会对照 `ProvideAssembly`的其他调用返回的 `pAssemblyId` 的值检查每个值。</span><span class="sxs-lookup"><span data-stu-id="475a6-138">It checks each value against the values for `pAssemblyId` returned by other calls to `ProvideAssembly`.</span></span> <span data-ttu-id="475a6-139">如果主机返回其他 `IStream`的相同 `pAssemblyId` 值，则 CLR 将检查是否已映射该流的内容。</span><span class="sxs-lookup"><span data-stu-id="475a6-139">If the host returns the same `pAssemblyId` value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="475a6-140">如果是这样，则运行时加载映像的现有副本，而不是映射一个新副本。</span><span class="sxs-lookup"><span data-stu-id="475a6-140">If so, the runtime loads the existing copy of the image instead of mapping a new one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="475a6-141">要求</span><span class="sxs-lookup"><span data-stu-id="475a6-141">Requirements</span></span>  
 <span data-ttu-id="475a6-142">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="475a6-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="475a6-143">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="475a6-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="475a6-144">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="475a6-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="475a6-145">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="475a6-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="475a6-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="475a6-146">See also</span></span>

- [<span data-ttu-id="475a6-147">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="475a6-147">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="475a6-148">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="475a6-148">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="475a6-149">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="475a6-149">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
