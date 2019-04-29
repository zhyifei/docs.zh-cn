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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4067c1fbcf99c903c892eaec58262d95569114b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61930034"
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="d76ff-102">IHostAssemblyStore 接口</span><span class="sxs-lookup"><span data-stu-id="d76ff-102">IHostAssemblyStore Interface</span></span>
<span data-ttu-id="d76ff-103">提供允许主机以加载程序集和模块独立于公共语言运行时 (CLR) 的方法。</span><span class="sxs-lookup"><span data-stu-id="d76ff-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d76ff-104">方法</span><span class="sxs-lookup"><span data-stu-id="d76ff-104">Methods</span></span>  
  
|<span data-ttu-id="d76ff-105">方法</span><span class="sxs-lookup"><span data-stu-id="d76ff-105">Method</span></span>|<span data-ttu-id="d76ff-106">描述</span><span class="sxs-lookup"><span data-stu-id="d76ff-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d76ff-107">ProvideAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="d76ff-107">ProvideAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="d76ff-108">获取未被引用程序集的引用[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)从调用返回[ihostassemblymanager:: Getnonhoststoreassemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)。</span><span class="sxs-lookup"><span data-stu-id="d76ff-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="d76ff-109">ProvideModule 方法</span><span class="sxs-lookup"><span data-stu-id="d76ff-109">ProvideModule Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|<span data-ttu-id="d76ff-110">解析程序集或链接 （而不是嵌入） 的资源文件中的模块。</span><span class="sxs-lookup"><span data-stu-id="d76ff-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d76ff-111">备注</span><span class="sxs-lookup"><span data-stu-id="d76ff-111">Remarks</span></span>  
 <span data-ttu-id="d76ff-112">`IHostAssemblyStore` 提供一个主机来加载程序集有效地基于程序集标识的方法。</span><span class="sxs-lookup"><span data-stu-id="d76ff-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="d76ff-113">主机加载程序集通过返回`IStream`直接指向字节的实例。</span><span class="sxs-lookup"><span data-stu-id="d76ff-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="d76ff-114">CLR 确定主机是否已实现`IHostAssemblyStore`通过调用`IHostAssemblyManager::GetNonHostAssemblyStores`初始化时。</span><span class="sxs-lookup"><span data-stu-id="d76ff-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="d76ff-115">这样该主机，例如，控件绑定到用户程序集，而是依赖于要绑定到.NET Framework 程序集的运行时。</span><span class="sxs-lookup"><span data-stu-id="d76ff-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d76ff-116">在提供的实现`IHostAssemblyStore`，该主机指定若要解决所有未被引用的程序集其意图`ICLRAssemblyReferenceList`从返回`IHostAssemblyManager::GetNonHostStoreAssemblies`。</span><span class="sxs-lookup"><span data-stu-id="d76ff-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d76ff-117">.NET Framework 2.0 版不提供主机加载本机映像程序集的一种方法提供的[本机映像生成器 (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)实用程序。</span><span class="sxs-lookup"><span data-stu-id="d76ff-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d76ff-118">要求</span><span class="sxs-lookup"><span data-stu-id="d76ff-118">Requirements</span></span>  
 <span data-ttu-id="d76ff-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d76ff-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d76ff-120">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d76ff-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d76ff-121">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d76ff-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d76ff-122">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d76ff-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d76ff-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="d76ff-123">See also</span></span>

- [<span data-ttu-id="d76ff-124">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="d76ff-124">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="d76ff-125">IHostAssemblyManager 接口</span><span class="sxs-lookup"><span data-stu-id="d76ff-125">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="d76ff-126">承载接口</span><span class="sxs-lookup"><span data-stu-id="d76ff-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
