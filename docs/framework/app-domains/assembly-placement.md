---
title: "程序集位置"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f5f80649e214583dae52ed8ec7933b77bf72fca5
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="assembly-placement"></a><span data-ttu-id="31aaa-102">程序集位置</span><span class="sxs-lookup"><span data-stu-id="31aaa-102">Assembly Placement</span></span>
<span data-ttu-id="31aaa-103">对于大多数 .NET Framework 应用程序而言，您可以在以下位置找到构成该应用程序的程序集，这些位置包括：该应用程序的目录中，该应用程序目录的子目录中，或全局程序集缓存中（如果该程序集是共享的话）。</span><span class="sxs-lookup"><span data-stu-id="31aaa-103">For most .NET Framework applications, you locate assemblies that make up an application in the application's directory, in a subdirectory of the application's directory, or in the global assembly cache (if the assembly is shared).</span></span> <span data-ttu-id="31aaa-104">可以通过在配置文件中使用 [\<codeBase> 元素](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)替代公共语言运行时查找某一程序集的位置。</span><span class="sxs-lookup"><span data-stu-id="31aaa-104">You can override where the common language runtime looks for an assembly by using the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) in a configuration file.</span></span> <span data-ttu-id="31aaa-105">如果程序集没有强名称，则使用 [\<codeBase> 元素](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)指定的位置限制为应用程序目录或子目录。</span><span class="sxs-lookup"><span data-stu-id="31aaa-105">If the assembly does not have a strong name, the location specified using the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) is restricted to the application directory or a subdirectory.</span></span> <span data-ttu-id="31aaa-106">如果程序集具有强名称，则 [\<codeBase> 元素](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)能够指定计算机或网络上的任意位置。</span><span class="sxs-lookup"><span data-stu-id="31aaa-106">If the assembly has a strong name, the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) can specify any location on the computer or on a network.</span></span>  
  
 <span data-ttu-id="31aaa-107">当在使用非托管代码或 COM 互操作 应用程序的过程中查找程序集的位置时，类似的规则同样适用：如果该程序集将由多个应用程序共享，则此程序集应被安装到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="31aaa-107">Similar rules apply to locating assemblies when working with unmanaged code or COM interop applications: if the assembly will be shared by multiple applications, it should be installed into the global assembly cache.</span></span> <span data-ttu-id="31aaa-108">和非托管代码一起使用的程序集必须作为类型库导出并注册。</span><span class="sxs-lookup"><span data-stu-id="31aaa-108">Assemblies used with unmanaged code must be exported as a type library and registered.</span></span> <span data-ttu-id="31aaa-109">由 COM 互操作 使用的程序集必须在目录中进行注册，尽管有些情况下会自动进行此注册。</span><span class="sxs-lookup"><span data-stu-id="31aaa-109">Assemblies used by COM interop must be registered in the catalog, although in some cases this registration occurs automatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31aaa-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31aaa-110">See Also</span></span>  
 <span data-ttu-id="31aaa-111">[运行时如何定位程序集](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="31aaa-111">[How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md) </span></span>  
 <span data-ttu-id="31aaa-112">[配置应用](../../../docs/framework/configure-apps/index.md) </span><span class="sxs-lookup"><span data-stu-id="31aaa-112">[Configuring Apps](../../../docs/framework/configure-apps/index.md) </span></span>  
 <span data-ttu-id="31aaa-113">[高级 COM 互操作性](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb) </span><span class="sxs-lookup"><span data-stu-id="31aaa-113">[Advanced COM Interoperability](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb) </span></span>  
 <span data-ttu-id="31aaa-114">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)（公共语言运行时中的程序集）</span><span class="sxs-lookup"><span data-stu-id="31aaa-114">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)</span></span>

