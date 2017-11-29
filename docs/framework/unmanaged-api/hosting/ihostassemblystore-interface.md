---
title: "IHostAssemblyStore 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyStore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyStore
helpviewer_keywords: IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 284afbe73bea28a0aafe8d5e9e030c43be94aea4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="151d2-102">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="151d2-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="151d2-103">提供使主机可在加载程序集和模块独立于公共语言运行时 (CLR) 的方法。</span><span class="sxs-lookup"><span data-stu-id="151d2-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="151d2-104">方法</span><span class="sxs-lookup"><span data-stu-id="151d2-104">Methods</span></span>  
  
|<span data-ttu-id="151d2-105">方法</span><span class="sxs-lookup"><span data-stu-id="151d2-105">Method</span></span>|<span data-ttu-id="151d2-106">描述</span><span class="sxs-lookup"><span data-stu-id="151d2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="151d2-107">ProvideAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="151d2-107">ProvideAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="151d2-108">获取未被引用程序集的引用[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)从调用返回[ihostassemblymanager:: Getnonhoststoreassemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)。</span><span class="sxs-lookup"><span data-stu-id="151d2-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="151d2-109">ProvideModule 方法</span><span class="sxs-lookup"><span data-stu-id="151d2-109">ProvideModule Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|<span data-ttu-id="151d2-110">解析程序集或链接的 （不使用嵌入） 资源文件内的模块。</span><span class="sxs-lookup"><span data-stu-id="151d2-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="151d2-111">备注</span><span class="sxs-lookup"><span data-stu-id="151d2-111">Remarks</span></span>  
 <span data-ttu-id="151d2-112">`IHostAssemblyStore`提供的主机以加载程序集有效地基于程序集标识的方法。</span><span class="sxs-lookup"><span data-stu-id="151d2-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="151d2-113">主机加载程序集通过返回`IStream`直接指向字节的实例。</span><span class="sxs-lookup"><span data-stu-id="151d2-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="151d2-114">CLR 确定主机是否具有实现`IHostAssemblyStore`通过调用`IHostAssemblyManager::GetNonHostAssemblyStores`在初始化时。</span><span class="sxs-lookup"><span data-stu-id="151d2-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="151d2-115">这样主机，例如，若要控制对用户程序集的绑定，但依赖于要将绑定到.NET Framework 程序集的运行时。</span><span class="sxs-lookup"><span data-stu-id="151d2-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="151d2-116">在提供的实现`IHostAssemblyStore`，主机指定其试图解决未被引用的所有程序集`ICLRAssemblyReferenceList`从返回`IHostAssemblyManager::GetNonHostStoreAssemblies`。</span><span class="sxs-lookup"><span data-stu-id="151d2-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="151d2-117">.NET Framework 2.0 版不提供主机加载本机映像程序集的一种方法，因为由提供[本机映像生成器 (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)实用程序。</span><span class="sxs-lookup"><span data-stu-id="151d2-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="151d2-118">要求</span><span class="sxs-lookup"><span data-stu-id="151d2-118">Requirements</span></span>  
 <span data-ttu-id="151d2-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="151d2-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="151d2-120">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="151d2-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="151d2-121">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="151d2-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="151d2-122">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="151d2-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="151d2-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="151d2-123">See Also</span></span>  
 [<span data-ttu-id="151d2-124">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="151d2-124">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="151d2-125">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="151d2-125">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="151d2-126">承载接口</span><span class="sxs-lookup"><span data-stu-id="151d2-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
