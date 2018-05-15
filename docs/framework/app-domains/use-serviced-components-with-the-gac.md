---
title: 在服务组件中使用全局程序集缓存
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache), serviced components
- serviced components, global assembly cache
- global assembly cache, serviced components
ms.assetid: 3423e5d9-234c-4571-8161-e35f6d130128
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 703e71661c7a679b85e60726f53b275fce1a4d6a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="using-serviced-components-with-the-global-assembly-cache"></a><span data-ttu-id="f2488-102">在服务组件中使用全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="f2488-102">Using Serviced Components with the Global Assembly Cache</span></span>
<span data-ttu-id="f2488-103">服务组件（托管代码 COM+ 组件）应置于全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="f2488-103">Serviced components (managed code COM+ components) should be put in the Global Assembly Cache.</span></span> <span data-ttu-id="f2488-104">在有些方案中，公共语言运行时和 COM+ 服务能够处理不在全局程序集缓存中的服务组件，而在有些方案中则不能。</span><span class="sxs-lookup"><span data-stu-id="f2488-104">In some scenarios, the Common Language Runtime and COM+ Services can handle serviced components that are not in the Global Assembly Cache; in other scenarios, they cannot.</span></span> <span data-ttu-id="f2488-105">以下方案对此进行了说明：</span><span class="sxs-lookup"><span data-stu-id="f2488-105">The following scenarios illustrate this:</span></span>  
  
-   <span data-ttu-id="f2488-106">对于 COM+ 服务器应用程序中的服务组件，包含组件的程序集必须位于全局程序集缓存中，因为 Dllhost.exe 不在包含服务组件的目录中运行。</span><span class="sxs-lookup"><span data-stu-id="f2488-106">For serviced components in a COM+ Server application, the assembly containing the components must be in the Global Assembly Cache, because Dllhost.exe does not run in the same directory as the one that contains the serviced components.</span></span>  
  
-   <span data-ttu-id="f2488-107">对于 COM+ 库应用程序中的服务组件，运行时和 COM+ 服务可通过搜索当前目录来解析对包含组件的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="f2488-107">For serviced components in a COM+ Library application, the runtime and COM+ Services can resolve the reference to the assembly containing the components by searching in the current directory.</span></span> <span data-ttu-id="f2488-108">在这种情况下，程序集不需要位于全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="f2488-108">In this case, the assembly does not have to be in the global assembly cache.</span></span>  
  
-   <span data-ttu-id="f2488-109">对于 ASP.NET 应用程序中的服务组件，情况则有所不同。</span><span class="sxs-lookup"><span data-stu-id="f2488-109">For serviced components in an ASP.NET application, the situation is different.</span></span> <span data-ttu-id="f2488-110">如果将包含服务组件的程序集放在应用程序基的 bin 目录中，并使用按需注册，程序集将被卷影复制到下载缓存，因为 ASP.NET 需利用运行时的卷影功能。</span><span class="sxs-lookup"><span data-stu-id="f2488-110">If you place the assembly containing the serviced components in the bin directory of the application base and use on-demand registration, the assembly will be shadow-copied into the download cache because ASP.NET leverages the shadow capabilities of the runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2488-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2488-111">See Also</span></span>  
 [<span data-ttu-id="f2488-112">使用程序集和全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="f2488-112">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="f2488-113">Gacutil.exe（全局程序集缓存工具）</span><span class="sxs-lookup"><span data-stu-id="f2488-113">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
