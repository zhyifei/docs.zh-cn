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
ms.openlocfilehash: d9feeaf5f85d6f84a13e74a893b82c97fdaf023c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124512"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="e81f1-102">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="e81f1-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="e81f1-103">提供一些方法，这些方法允许主机指定应由公共语言运行时（CLR）或主机加载的程序集集。</span><span class="sxs-lookup"><span data-stu-id="e81f1-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e81f1-104">方法</span><span class="sxs-lookup"><span data-stu-id="e81f1-104">Methods</span></span>  
  
|<span data-ttu-id="e81f1-105">方法</span><span class="sxs-lookup"><span data-stu-id="e81f1-105">Method</span></span>|<span data-ttu-id="e81f1-106">描述</span><span class="sxs-lookup"><span data-stu-id="e81f1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e81f1-107">GetAssemblyStore 方法</span><span class="sxs-lookup"><span data-stu-id="e81f1-107">GetAssemblyStore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="e81f1-108">获取一个接口指针，该指针指向表示宿主加载的程序集列表的[IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) 。</span><span class="sxs-lookup"><span data-stu-id="e81f1-108">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="e81f1-109">GetNonHostStoreAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="e81f1-109">GetNonHostStoreAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="e81f1-110">获取一个指向[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)的接口指针，该指针表示宿主预期 CLR 加载的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="e81f1-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e81f1-111">备注</span><span class="sxs-lookup"><span data-stu-id="e81f1-111">Remarks</span></span>  
 <span data-ttu-id="e81f1-112">宿主无需实现 `IHostAssemblyManager` 或 `IHostAssemblyStore`。</span><span class="sxs-lookup"><span data-stu-id="e81f1-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="e81f1-113">如果宿主确实实现 `IHostAssemblyManager`，它还必须实现 `IHostAssemblyStore`。</span><span class="sxs-lookup"><span data-stu-id="e81f1-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="e81f1-114">运行时通过在 `IID` IID_IHostAssemblyManager 的初始化时调用[IHostControl：： GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)来查询 `IHostAssemblyManager`。</span><span class="sxs-lookup"><span data-stu-id="e81f1-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e81f1-115">要求</span><span class="sxs-lookup"><span data-stu-id="e81f1-115">Requirements</span></span>  
 <span data-ttu-id="e81f1-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e81f1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e81f1-117">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e81f1-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e81f1-118">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="e81f1-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e81f1-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e81f1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e81f1-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="e81f1-120">See also</span></span>

- [<span data-ttu-id="e81f1-121">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="e81f1-121">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="e81f1-122">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="e81f1-122">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="e81f1-123">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="e81f1-123">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="e81f1-124">承载接口</span><span class="sxs-lookup"><span data-stu-id="e81f1-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
