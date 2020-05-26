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
ms.openlocfilehash: 8106dd70f6c4099b2246530622f0845f22a0c53f
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805044"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="24b6c-102">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="24b6c-102">IHostAssemblyManager Interface</span></span>
<span data-ttu-id="24b6c-103">提供一些方法，这些方法允许主机指定应由公共语言运行时（CLR）或主机加载的程序集集。</span><span class="sxs-lookup"><span data-stu-id="24b6c-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="24b6c-104">方法</span><span class="sxs-lookup"><span data-stu-id="24b6c-104">Methods</span></span>  
  
|<span data-ttu-id="24b6c-105">方法</span><span class="sxs-lookup"><span data-stu-id="24b6c-105">Method</span></span>|<span data-ttu-id="24b6c-106">说明</span><span class="sxs-lookup"><span data-stu-id="24b6c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="24b6c-107">GetAssemblyStore 方法</span><span class="sxs-lookup"><span data-stu-id="24b6c-107">GetAssemblyStore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="24b6c-108">获取一个接口指针，该指针指向表示宿主加载的程序集列表的[IHostAssemblyStore](ihostassemblystore-interface.md) 。</span><span class="sxs-lookup"><span data-stu-id="24b6c-108">Gets an interface pointer to an [IHostAssemblyStore](ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="24b6c-109">GetNonHostStoreAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="24b6c-109">GetNonHostStoreAssemblies Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="24b6c-110">获取一个指向[ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md)的接口指针，该指针表示宿主预期 CLR 加载的程序集的列表。</span><span class="sxs-lookup"><span data-stu-id="24b6c-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24b6c-111">备注</span><span class="sxs-lookup"><span data-stu-id="24b6c-111">Remarks</span></span>  
 <span data-ttu-id="24b6c-112">宿主无需实现 `IHostAssemblyManager` 或 `IHostAssemblyStore` 。</span><span class="sxs-lookup"><span data-stu-id="24b6c-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="24b6c-113">如果主机实现了 `IHostAssemblyManager` ，则它还必须实现 `IHostAssemblyStore` 。</span><span class="sxs-lookup"><span data-stu-id="24b6c-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="24b6c-114">运行时 `IHostAssemblyManager` 通过在使用 IID_IHostAssemblyManager 的初始化时调用[IHostControl：： GetHostManager](ihostcontrol-gethostmanager-method.md)来查询 `IID` 。</span><span class="sxs-lookup"><span data-stu-id="24b6c-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24b6c-115">要求</span><span class="sxs-lookup"><span data-stu-id="24b6c-115">Requirements</span></span>  
 <span data-ttu-id="24b6c-116">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="24b6c-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24b6c-117">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="24b6c-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="24b6c-118">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="24b6c-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="24b6c-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24b6c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24b6c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24b6c-120">See also</span></span>

- [<span data-ttu-id="24b6c-121">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="24b6c-121">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="24b6c-122">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="24b6c-122">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="24b6c-123">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="24b6c-123">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="24b6c-124">承载接口</span><span class="sxs-lookup"><span data-stu-id="24b6c-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
