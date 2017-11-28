---
title: "如何：使用 DEVPATH 查找程序集"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 70448f7ce4c00274dde14bace603e5c8852bf148
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="685ed-102">如何：使用 DEVPATH 查找程序集</span><span class="sxs-lookup"><span data-stu-id="685ed-102">How to: Locate Assemblies by Using DEVPATH</span></span>
<span data-ttu-id="685ed-103">开发人员可能想要确保它们在构建共享程序集与多个应用程序一起正常运行。</span><span class="sxs-lookup"><span data-stu-id="685ed-103">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="685ed-104">而不是不断地将全局程序集缓存中的程序集放置在开发周期中，开发人员可以创建一个 DEVPATH 环境变量，指向程序集的生成输出目录。</span><span class="sxs-lookup"><span data-stu-id="685ed-104">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="685ed-105">例如，假定您构建了调用 MySharedAssembly 共享程序集和输出目录是 C:\MySharedAssembly\Debug。</span><span class="sxs-lookup"><span data-stu-id="685ed-105">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="685ed-106">你可以放置 C:\MySharedAssembly\Debug DEVPATH 变量中。</span><span class="sxs-lookup"><span data-stu-id="685ed-106">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="685ed-107">你必须随后指定[ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md)计算机配置文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="685ed-107">You must then specify the [\<developmentMode>](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="685ed-108">此元素指示公共语言运行时使用 DEVPATH 查找程序集。</span><span class="sxs-lookup"><span data-stu-id="685ed-108">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="685ed-109">共享程序集必须由运行时可发现。</span><span class="sxs-lookup"><span data-stu-id="685ed-109">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="685ed-110">若要指定用于解析程序集引用使用专用目录[\<基本代码 > 元素](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)或[\<探测 > 元素](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)在配置文件中中, 所述[指定程序集的位置](../../../docs/framework/configure-apps/specify-assembly-location.md)。</span><span class="sxs-lookup"><span data-stu-id="685ed-110">To specify a private directory for resolving assembly references use the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) or [\<probing> Element](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  <span data-ttu-id="685ed-111">此外可以将程序集放置在应用程序目录的子目录中。</span><span class="sxs-lookup"><span data-stu-id="685ed-111">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="685ed-112">有关更多信息，请参阅 [运行时如何定位程序集](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="685ed-112">For more information, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="685ed-113">这是一项高级的功能，仅用于开发。</span><span class="sxs-lookup"><span data-stu-id="685ed-113">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="685ed-114">下面的示例演示如何使运行时搜索 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="685ed-114">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="685ed-115">示例</span><span class="sxs-lookup"><span data-stu-id="685ed-115">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="685ed-116">此设置默认为 false。</span><span class="sxs-lookup"><span data-stu-id="685ed-116">This setting defaults to false.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="685ed-117">仅在开发期间使用此设置。</span><span class="sxs-lookup"><span data-stu-id="685ed-117">Use this setting only at development time.</span></span> <span data-ttu-id="685ed-118">运行时不会检查上 DEVPATH 中找到的具有强名称的程序集的版本。</span><span class="sxs-lookup"><span data-stu-id="685ed-118">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="685ed-119">它只需使用它找到的第一个程序集。</span><span class="sxs-lookup"><span data-stu-id="685ed-119">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="685ed-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="685ed-120">See Also</span></span>  
 [<span data-ttu-id="685ed-121">配置.NET Framework 应用</span><span class="sxs-lookup"><span data-stu-id="685ed-121">Configuring .NET Framework Apps</span></span>](http://msdn.microsoft.com/en-us/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
