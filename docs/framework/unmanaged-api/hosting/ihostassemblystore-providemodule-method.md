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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b604e1d7fc3d3c8adf7d95bd95843bc0110dbc9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440013"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="1a7ec-102">IHostAssemblyStore::ProvideModule 方法</span><span class="sxs-lookup"><span data-stu-id="1a7ec-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="1a7ec-103">解析程序集或链接 （而不是嵌入） 内的模块资源文件。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a7ec-104">语法</span><span class="sxs-lookup"><span data-stu-id="1a7ec-104">Syntax</span></span>  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a7ec-105">参数</span><span class="sxs-lookup"><span data-stu-id="1a7ec-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="1a7ec-106">[in]指向的指针[ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)描述请求的模块的实例<xref:System.AppDomain>，程序集和模块名称。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-106">[in] A pointer to a [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="1a7ec-107">[out]指向的唯一标识符的`IStream`包含加载的模块。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="1a7ec-108">[out]指向的地址的指针`IStream`对象，其中包含要加载的可移植可执行 (PE) 映像，或如果未找到该模块则为 null。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="1a7ec-109">[out]指向的地址的指针`IStream`对象，其中包含请求的模块中，与程序调试 (PDB) 信息或如果找不到.pdb 文件则为 null。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a7ec-110">返回值</span><span class="sxs-lookup"><span data-stu-id="1a7ec-110">Return Value</span></span>  
  
|<span data-ttu-id="1a7ec-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1a7ec-111">HRESULT</span></span>|<span data-ttu-id="1a7ec-112">描述</span><span class="sxs-lookup"><span data-stu-id="1a7ec-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1a7ec-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1a7ec-113">S_OK</span></span>|<span data-ttu-id="1a7ec-114">`ProvideModule` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="1a7ec-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1a7ec-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1a7ec-116">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1a7ec-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1a7ec-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1a7ec-118">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-118">The call timed out.</span></span>|  
|<span data-ttu-id="1a7ec-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1a7ec-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1a7ec-120">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1a7ec-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1a7ec-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1a7ec-122">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1a7ec-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1a7ec-123">E_FAIL</span></span>|<span data-ttu-id="1a7ec-124">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1a7ec-125">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1a7ec-126">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1a7ec-127">COR_E_FILENOTFOUND (0X80070002)</span><span class="sxs-lookup"><span data-stu-id="1a7ec-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="1a7ec-128">请求的程序集或链接的资源找不到。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="1a7ec-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="1a7ec-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="1a7ec-130">`pdwModuleId` 不大到足以包含主机想要返回的标识符。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a7ec-131">备注</span><span class="sxs-lookup"><span data-stu-id="1a7ec-131">Remarks</span></span>  
 <span data-ttu-id="1a7ec-132">返回标识值`pdwModuleId`宿主指定。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="1a7ec-133">标识符在进程的生存期内必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="1a7ec-134">CLR 使用此值关联的流作为唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="1a7ec-135">它会检查每个值对的值`pAssemblyId`返回通过调用[ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)和的值针对`pdwModuleId`返回到其他调用`ProvideModule`。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="1a7ec-136">如果主机的另一个返回相同的标识符值`IStream`，CLR 将检查是否已映射了该流的内容。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="1a7ec-137">如果是这样，CLR 加载映像而不是映射一个新的现有副本。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="1a7ec-138">因此，标识符也不能重叠从返回的程序集标识符`ProvideAssembly`。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a7ec-139">要求</span><span class="sxs-lookup"><span data-stu-id="1a7ec-139">Requirements</span></span>  
 <span data-ttu-id="1a7ec-140">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1a7ec-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a7ec-141">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1a7ec-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1a7ec-142">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1a7ec-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1a7ec-143">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a7ec-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a7ec-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a7ec-144">See Also</span></span>  
 [<span data-ttu-id="1a7ec-145">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="1a7ec-145">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="1a7ec-146">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="1a7ec-146">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="1a7ec-147">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="1a7ec-147">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
