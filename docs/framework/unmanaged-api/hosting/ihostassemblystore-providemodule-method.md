---
title: IHostAssemblyStore::ProvideModule 方法
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type:
- apiref
ms.openlocfilehash: eed09a8149a21140ad61133f29391f86cb0fb929
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124475"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="e37e0-102">IHostAssemblyStore::ProvideModule 方法</span><span class="sxs-lookup"><span data-stu-id="e37e0-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="e37e0-103">解析程序集或链接的（但不是嵌入的）资源文件中的模块。</span><span class="sxs-lookup"><span data-stu-id="e37e0-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e37e0-104">语法</span><span class="sxs-lookup"><span data-stu-id="e37e0-104">Syntax</span></span>  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e37e0-105">参数</span><span class="sxs-lookup"><span data-stu-id="e37e0-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="e37e0-106">中指向[ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)实例的指针，该实例描述请求的模块的 <xref:System.AppDomain>、程序集和模块名称。</span><span class="sxs-lookup"><span data-stu-id="e37e0-106">[in] A pointer to a [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="e37e0-107">弄一个指针，指向包含已加载模块的 `IStream` 的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e37e0-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="e37e0-108">弄指向 `IStream` 对象（其中包含要加载的可移植可执行（PE）映像）的地址的指针; 如果找不到该模块，则为 null。</span><span class="sxs-lookup"><span data-stu-id="e37e0-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="e37e0-109">弄指向 `IStream` 对象的地址的指针，该对象包含请求的模块的程序调试（PDB）信息; 如果找不到 .pdb 文件，则为 null。</span><span class="sxs-lookup"><span data-stu-id="e37e0-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e37e0-110">返回值</span><span class="sxs-lookup"><span data-stu-id="e37e0-110">Return Value</span></span>  
  
|<span data-ttu-id="e37e0-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e37e0-111">HRESULT</span></span>|<span data-ttu-id="e37e0-112">描述</span><span class="sxs-lookup"><span data-stu-id="e37e0-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e37e0-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="e37e0-113">S_OK</span></span>|<span data-ttu-id="e37e0-114">`ProvideModule` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="e37e0-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="e37e0-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e37e0-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e37e0-116">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="e37e0-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e37e0-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e37e0-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e37e0-118">调用超时。</span><span class="sxs-lookup"><span data-stu-id="e37e0-118">The call timed out.</span></span>|  
|<span data-ttu-id="e37e0-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e37e0-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e37e0-120">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="e37e0-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e37e0-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e37e0-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e37e0-122">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="e37e0-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e37e0-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e37e0-123">E_FAIL</span></span>|<span data-ttu-id="e37e0-124">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="e37e0-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e37e0-125">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="e37e0-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e37e0-126">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="e37e0-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e37e0-127">COR_E_FILENOTFOUND （0x80070002）</span><span class="sxs-lookup"><span data-stu-id="e37e0-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="e37e0-128">找不到请求的程序集或链接的资源。</span><span class="sxs-lookup"><span data-stu-id="e37e0-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="e37e0-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="e37e0-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="e37e0-130">`pdwModuleId` 不够大，无法包含主机需要返回的标识符。</span><span class="sxs-lookup"><span data-stu-id="e37e0-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e37e0-131">备注</span><span class="sxs-lookup"><span data-stu-id="e37e0-131">Remarks</span></span>  
 <span data-ttu-id="e37e0-132">为 `pdwModuleId` 返回的标识值由主机指定。</span><span class="sxs-lookup"><span data-stu-id="e37e0-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="e37e0-133">标识符在进程的生存期内必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e37e0-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="e37e0-134">CLR 使用此值作为关联流的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e37e0-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="e37e0-135">它会 `pAssemblyId` 根据对[ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)的调用返回的值以及对 `ProvideModule`的其他调用返回的 `pdwModuleId` 值来检查每个值。</span><span class="sxs-lookup"><span data-stu-id="e37e0-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="e37e0-136">如果主机为其他 `IStream`返回相同的标识符值，则 CLR 将检查是否已映射该流的内容。</span><span class="sxs-lookup"><span data-stu-id="e37e0-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="e37e0-137">如果是这样，CLR 将加载映像的现有副本，而不是映射一个新副本。</span><span class="sxs-lookup"><span data-stu-id="e37e0-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="e37e0-138">因此，标识符也不得与 `ProvideAssembly`返回的程序集标识符重叠。</span><span class="sxs-lookup"><span data-stu-id="e37e0-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e37e0-139">要求</span><span class="sxs-lookup"><span data-stu-id="e37e0-139">Requirements</span></span>  
 <span data-ttu-id="e37e0-140">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e37e0-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e37e0-141">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e37e0-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e37e0-142">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="e37e0-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e37e0-143">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e37e0-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e37e0-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="e37e0-144">See also</span></span>

- [<span data-ttu-id="e37e0-145">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="e37e0-145">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="e37e0-146">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="e37e0-146">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="e37e0-147">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="e37e0-147">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
