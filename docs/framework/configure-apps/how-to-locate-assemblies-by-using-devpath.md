---
title: 如何：通过使用 devpath 查找程序集查找程序集
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
ms.openlocfilehash: 5c4041f42b0a9d1d1e4bc8438e662911534daa42
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826676"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="f52b3-102">如何：通过使用 devpath 查找程序集查找程序集</span><span class="sxs-lookup"><span data-stu-id="f52b3-102">How to: Locate Assemblies by Using DEVPATH</span></span>
<span data-ttu-id="f52b3-103">开发人员可能想要确保它们生成的共享程序集与多个应用程序一起正常运行。</span><span class="sxs-lookup"><span data-stu-id="f52b3-103">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="f52b3-104">而不是不断地将在全局程序集缓存中的程序集放在开发周期中，开发人员可以创建指向程序集的生成输出目录 DEVPATH 环境变量。</span><span class="sxs-lookup"><span data-stu-id="f52b3-104">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="f52b3-105">例如，假设您要构建调用 MySharedAssembly 共享程序集和输出目录是 C:\MySharedAssembly\Debug。</span><span class="sxs-lookup"><span data-stu-id="f52b3-105">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="f52b3-106">可以将 C:\MySharedAssembly\Debug 放 devpath 查找程序集变量中。</span><span class="sxs-lookup"><span data-stu-id="f52b3-106">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="f52b3-107">然后，必须指定[ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md)计算机配置文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="f52b3-107">You must then specify the [\<developmentMode>](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="f52b3-108">此元素指示公共语言运行时使用 devpath 查找程序集来定位程序集。</span><span class="sxs-lookup"><span data-stu-id="f52b3-108">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="f52b3-109">共享程序集必须可由运行时检测到。</span><span class="sxs-lookup"><span data-stu-id="f52b3-109">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="f52b3-110">若要指定用于解析程序集引用使用的专用目录[ \<b a s e > 元素](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)或[\<探测 > 元素](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)在配置文件中，如中所述[指定程序集位置](../../../docs/framework/configure-apps/specify-assembly-location.md)。</span><span class="sxs-lookup"><span data-stu-id="f52b3-110">To specify a private directory for resolving assembly references use the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) or [\<probing> Element](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  <span data-ttu-id="f52b3-111">此外可以将程序集放置在应用程序目录的子目录中。</span><span class="sxs-lookup"><span data-stu-id="f52b3-111">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="f52b3-112">有关更多信息，请参阅 [运行时如何定位程序集](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="f52b3-112">For more information, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f52b3-113">这是一项高级的功能，仅供开发。</span><span class="sxs-lookup"><span data-stu-id="f52b3-113">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="f52b3-114">下面的示例演示如何会导致运行时用于搜索由 DEVPATH 环境变量指定的目录中的程序集。</span><span class="sxs-lookup"><span data-stu-id="f52b3-114">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f52b3-115">示例</span><span class="sxs-lookup"><span data-stu-id="f52b3-115">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="f52b3-116">此设置默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="f52b3-116">This setting defaults to false.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f52b3-117">仅在开发期间使用此设置。</span><span class="sxs-lookup"><span data-stu-id="f52b3-117">Use this setting only at development time.</span></span> <span data-ttu-id="f52b3-118">在运行时不会检查位于 devpath 查找程序集强名称的程序集上的版本。</span><span class="sxs-lookup"><span data-stu-id="f52b3-118">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="f52b3-119">它只需使用它找到的第一个程序集。</span><span class="sxs-lookup"><span data-stu-id="f52b3-119">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f52b3-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="f52b3-120">See also</span></span>

- [<span data-ttu-id="f52b3-121">使用配置文件配置应用程序</span><span class="sxs-lookup"><span data-stu-id="f52b3-121">Configuring Apps by using Configuration Files</span></span>](index.md)
