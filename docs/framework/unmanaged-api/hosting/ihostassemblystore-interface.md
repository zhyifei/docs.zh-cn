---
title: IHostAssemblyStore 接口
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore
helpviewer_keywords:
- IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type:
- apiref
ms.openlocfilehash: d7475e2423d4dc6f57e8928514d7991169eef232
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124504"
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="2e9dc-102">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="2e9dc-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="2e9dc-103">提供允许主机独立于公共语言运行时（CLR）加载程序集和模块的方法。</span><span class="sxs-lookup"><span data-stu-id="2e9dc-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2e9dc-104">方法</span><span class="sxs-lookup"><span data-stu-id="2e9dc-104">Methods</span></span>  
  
|<span data-ttu-id="2e9dc-105">方法</span><span class="sxs-lookup"><span data-stu-id="2e9dc-105">Method</span></span>|<span data-ttu-id="2e9dc-106">描述</span><span class="sxs-lookup"><span data-stu-id="2e9dc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2e9dc-107">ProvideAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="2e9dc-107">ProvideAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="2e9dc-108">获取对[IHostAssemblyManager：： GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)调用返回的[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)未引用的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="2e9dc-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="2e9dc-109">ProvideModule 方法</span><span class="sxs-lookup"><span data-stu-id="2e9dc-109">ProvideModule Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|<span data-ttu-id="2e9dc-110">解析程序集或链接（而非嵌入）资源文件中的模块。</span><span class="sxs-lookup"><span data-stu-id="2e9dc-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e9dc-111">备注</span><span class="sxs-lookup"><span data-stu-id="2e9dc-111">Remarks</span></span>  
 <span data-ttu-id="2e9dc-112">`IHostAssemblyStore` 提供了一种方法，使主机可以根据程序集标识有效地加载程序集。</span><span class="sxs-lookup"><span data-stu-id="2e9dc-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="2e9dc-113">宿主通过返回直接指向字节的 `IStream` 实例来加载程序集。</span><span class="sxs-lookup"><span data-stu-id="2e9dc-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="2e9dc-114">CLR 通过在初始化时调用 `IHostAssemblyManager::GetNonHostAssemblyStores` 来确定宿主是否已实现 `IHostAssemblyStore`。</span><span class="sxs-lookup"><span data-stu-id="2e9dc-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="2e9dc-115">例如，这允许主机控制与用户程序集的绑定，但要依赖于运行时绑定到 .NET Framework 程序集。</span><span class="sxs-lookup"><span data-stu-id="2e9dc-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2e9dc-116">在提供 `IHostAssemblyStore`的实现时，主机指定其目的来解析并非由 `IHostAssemblyManager::GetNonHostStoreAssemblies`返回的 `ICLRAssemblyReferenceList` 引用的所有程序集。</span><span class="sxs-lookup"><span data-stu-id="2e9dc-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2e9dc-117">.NET Framework 版本2.0 不为宿主提供一种方法来加载程序集的本机映像，如[本机映像生成器（ngen.exe）](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)实用程序所提供。</span><span class="sxs-lookup"><span data-stu-id="2e9dc-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e9dc-118">要求</span><span class="sxs-lookup"><span data-stu-id="2e9dc-118">Requirements</span></span>  
 <span data-ttu-id="2e9dc-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2e9dc-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e9dc-120">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2e9dc-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e9dc-121">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="2e9dc-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e9dc-122">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e9dc-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e9dc-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e9dc-123">See also</span></span>

- [<span data-ttu-id="2e9dc-124">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="2e9dc-124">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="2e9dc-125">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="2e9dc-125">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="2e9dc-126">承载接口</span><span class="sxs-lookup"><span data-stu-id="2e9dc-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
