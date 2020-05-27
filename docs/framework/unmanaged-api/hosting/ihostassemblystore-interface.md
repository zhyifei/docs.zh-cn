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
ms.openlocfilehash: 87fe0b10f0a1eefa8154c40d39b54285990c410c
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805036"
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="315ab-102">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="315ab-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="315ab-103">提供允许主机独立于公共语言运行时（CLR）加载程序集和模块的方法。</span><span class="sxs-lookup"><span data-stu-id="315ab-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="315ab-104">方法</span><span class="sxs-lookup"><span data-stu-id="315ab-104">Methods</span></span>  
  
|<span data-ttu-id="315ab-105">方法</span><span class="sxs-lookup"><span data-stu-id="315ab-105">Method</span></span>|<span data-ttu-id="315ab-106">说明</span><span class="sxs-lookup"><span data-stu-id="315ab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="315ab-107">ProvideAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="315ab-107">ProvideAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="315ab-108">获取对[IHostAssemblyManager：： GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md)调用返回的[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)未引用的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="315ab-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="315ab-109">ProvideModule 方法</span><span class="sxs-lookup"><span data-stu-id="315ab-109">ProvideModule Method</span></span>](ihostassemblystore-providemodule-method.md)|<span data-ttu-id="315ab-110">解析程序集或链接（而非嵌入）资源文件中的模块。</span><span class="sxs-lookup"><span data-stu-id="315ab-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="315ab-111">备注</span><span class="sxs-lookup"><span data-stu-id="315ab-111">Remarks</span></span>  
 <span data-ttu-id="315ab-112">`IHostAssemblyStore`提供一种方法，使主机可以根据程序集标识有效地加载程序集。</span><span class="sxs-lookup"><span data-stu-id="315ab-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="315ab-113">宿主通过返回直接指向字节的实例来加载程序集 `IStream` 。</span><span class="sxs-lookup"><span data-stu-id="315ab-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="315ab-114">CLR `IHostAssemblyStore` 通过在初始化时调用来确定宿主是否已实现 `IHostAssemblyManager::GetNonHostAssemblyStores` 。</span><span class="sxs-lookup"><span data-stu-id="315ab-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="315ab-115">例如，这允许主机控制与用户程序集的绑定，但要依赖于运行时绑定到 .NET Framework 程序集。</span><span class="sxs-lookup"><span data-stu-id="315ab-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="315ab-116">在提供的实现中 `IHostAssemblyStore` ，主机指定其意图以解析从返回的未引用的所有程序集 `ICLRAssemblyReferenceList` `IHostAssemblyManager::GetNonHostStoreAssemblies` 。</span><span class="sxs-lookup"><span data-stu-id="315ab-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="315ab-117">.NET Framework 版本2.0 不为宿主提供一种方法来加载程序集的本机映像，如[本机映像生成器（ngen.exe）](../../tools/ngen-exe-native-image-generator.md)实用程序所提供。</span><span class="sxs-lookup"><span data-stu-id="315ab-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="315ab-118">要求</span><span class="sxs-lookup"><span data-stu-id="315ab-118">Requirements</span></span>  
 <span data-ttu-id="315ab-119">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="315ab-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="315ab-120">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="315ab-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="315ab-121">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="315ab-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="315ab-122">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="315ab-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="315ab-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="315ab-123">See also</span></span>

- [<span data-ttu-id="315ab-124">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="315ab-124">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="315ab-125">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="315ab-125">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="315ab-126">承载接口</span><span class="sxs-lookup"><span data-stu-id="315ab-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
