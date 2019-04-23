---
title: IHostAssemblyManager 接口
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager
helpviewer_keywords:
- IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e300d4645939a131ceb8206999d95056b96a678
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118945"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="c80e5-102">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="c80e5-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="c80e5-103">提供允许主机以指定的公共语言运行时 (CLR) 或由主机应加载的程序集的方法。</span><span class="sxs-lookup"><span data-stu-id="c80e5-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c80e5-104">方法</span><span class="sxs-lookup"><span data-stu-id="c80e5-104">Methods</span></span>  
  
|<span data-ttu-id="c80e5-105">方法</span><span class="sxs-lookup"><span data-stu-id="c80e5-105">Method</span></span>|<span data-ttu-id="c80e5-106">描述</span><span class="sxs-lookup"><span data-stu-id="c80e5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c80e5-107">GetAssemblyStore 方法</span><span class="sxs-lookup"><span data-stu-id="c80e5-107">GetAssemblyStore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="c80e5-108">获取到的接口指针[IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) ，表示由宿主加载的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="c80e5-108">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="c80e5-109">GetNonHostStoreAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="c80e5-109">GetNonHostStoreAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="c80e5-110">获取到的接口指针[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)表示主机需要 CLR 加载的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="c80e5-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c80e5-111">备注</span><span class="sxs-lookup"><span data-stu-id="c80e5-111">Remarks</span></span>  
 <span data-ttu-id="c80e5-112">主机不需要实现`IHostAssemblyManager`或`IHostAssemblyStore`。</span><span class="sxs-lookup"><span data-stu-id="c80e5-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="c80e5-113">如果实现主机`IHostAssemblyManager`，它必须实现`IHostAssemblyStore`。</span><span class="sxs-lookup"><span data-stu-id="c80e5-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="c80e5-114">在运行时中查询`IHostAssemblyManager`通过调用[ihostcontrol:: Gethostmanager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)与初始化时`IID`IID_IHostAssemblyManager。</span><span class="sxs-lookup"><span data-stu-id="c80e5-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c80e5-115">要求</span><span class="sxs-lookup"><span data-stu-id="c80e5-115">Requirements</span></span>  
 <span data-ttu-id="c80e5-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c80e5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c80e5-117">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c80e5-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c80e5-118">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c80e5-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c80e5-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c80e5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c80e5-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="c80e5-120">See also</span></span>

- [<span data-ttu-id="c80e5-121">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="c80e5-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="c80e5-122">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="c80e5-122">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="c80e5-123">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="c80e5-123">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="c80e5-124">承载接口</span><span class="sxs-lookup"><span data-stu-id="c80e5-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
