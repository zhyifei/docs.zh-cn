---
title: 程序集内容
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- assemblies [.NET Framework], single-file
- single-file assemblies
- multifile assemblies
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25594c55a5462c42611df7119dad37bd8a61cc2e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59149339"
---
# <a name="assembly-contents"></a><span data-ttu-id="d7e81-102">程序集内容</span><span class="sxs-lookup"><span data-stu-id="d7e81-102">Assembly Contents</span></span>
<span data-ttu-id="d7e81-103">通常，静态程序集可能由以下四个元素组成：</span><span class="sxs-lookup"><span data-stu-id="d7e81-103">In general, a static assembly can consist of four elements:</span></span>  
  
-   <span data-ttu-id="d7e81-104">[程序集清单](../../../docs/framework/app-domains/assembly-manifest.md)，包含程序集元数据。</span><span class="sxs-lookup"><span data-stu-id="d7e81-104">The [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md), which contains assembly metadata.</span></span>  
  
-   <span data-ttu-id="d7e81-105">类型元数据。</span><span class="sxs-lookup"><span data-stu-id="d7e81-105">Type metadata.</span></span>  
  
-   <span data-ttu-id="d7e81-106">实现这些类型的 Microsoft 中间语言 (MSIL) 代码。</span><span class="sxs-lookup"><span data-stu-id="d7e81-106">Microsoft intermediate language (MSIL) code that implements the types.</span></span>  
  
-   <span data-ttu-id="d7e81-107">资源集。</span><span class="sxs-lookup"><span data-stu-id="d7e81-107">A set of resources.</span></span>  
  
 <span data-ttu-id="d7e81-108">只有程序集清单是必需的，但也需要类型或资源来向程序集提供任何有意义的功能。</span><span class="sxs-lookup"><span data-stu-id="d7e81-108">Only the assembly manifest is required, but either types or resources are needed to give the assembly any meaningful functionality.</span></span>  
  
 <span data-ttu-id="d7e81-109">程序集中的这些元素有分组几种方法。</span><span class="sxs-lookup"><span data-stu-id="d7e81-109">There are several ways to group these elements in an assembly.</span></span> <span data-ttu-id="d7e81-110">您可以将所有元素分组到单个物理文件中，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="d7e81-110">You can group all elements in a single physical file, which is shown in the following illustration.</span></span>  
  
 ![显示名为 MyAssembly.dll 的单文件程序集的图表。](./media/assembly-contents/single-file-assembly.gif)  
  
 <span data-ttu-id="d7e81-112">或者，可以将一个程序集的元素包含在几个文件中。</span><span class="sxs-lookup"><span data-stu-id="d7e81-112">Alternatively, the elements of an assembly can be contained in several files.</span></span> <span data-ttu-id="d7e81-113">这些文件可以是应用程序所需的编译代码 (.netmodule)、资源（例如，.bmp 或 .jpg 文件）或其他文件的模块。</span><span class="sxs-lookup"><span data-stu-id="d7e81-113">These files can be modules of compiled code (.netmodule), resources (such as .bmp or .jpg files), or other files required by the application.</span></span> <span data-ttu-id="d7e81-114">在您希望组合以不同语言编写的模块并优化应用程序的下载过程时，可创建一个多文件程序集，优化下载过程的方法是将很少使用的类型放入只在需要时才下载的模块中。</span><span class="sxs-lookup"><span data-stu-id="d7e81-114">Create a multifile assembly when you want to combine modules written in different languages and to optimize downloading an application by putting seldom used types in a module that is downloaded only when needed.</span></span>  
  
 <span data-ttu-id="d7e81-115">在下图中，一个假想应用程序的开发人员已选择将一些实用工具代码单独放入另一个模块中，同时在其原文件中保留一个较大的资源文件（在此例中为一个 .bmp 图像）。</span><span class="sxs-lookup"><span data-stu-id="d7e81-115">In the following illustration, the developer of a hypothetical application has chosen to separate some utility code into a different module and to keep a large resource file (in this case a .bmp image) in its original file.</span></span> <span data-ttu-id="d7e81-116">.NET Framework 只在文件被引用时下载该文件；通过将很少引用的代码保留在独立于应用程序的文件中来优化代码下载。</span><span class="sxs-lookup"><span data-stu-id="d7e81-116">The .NET Framework downloads a file only when it is referenced; keeping infrequently referenced code in a separate file from the application optimizes code download.</span></span>  
  
 ![显示多文件程序集的图表。](./media/assembly-contents/multifile-assembly-diagram.gif) 
  
> [!NOTE]
>  <span data-ttu-id="d7e81-118">构成多文件程序集的那些文件实际上并非由文件系统来链接。</span><span class="sxs-lookup"><span data-stu-id="d7e81-118">The files that make up a multifile assembly are not physically linked by the file system.</span></span> <span data-ttu-id="d7e81-119">它们而是通过程序集清单进行链接，公共语言运行时将这些文件作为一个单元来管理。</span><span class="sxs-lookup"><span data-stu-id="d7e81-119">Rather, they are linked through the assembly manifest and the common language runtime manages them as a unit.</span></span>  
  
 <span data-ttu-id="d7e81-120">在此插图中，所有三个文件均属于一个程序集，如 MyAssembly.dll 所包含的程序集清单文件中所述。</span><span class="sxs-lookup"><span data-stu-id="d7e81-120">In this illustration, all three files belong to an assembly, as described in the assembly manifest contained in MyAssembly.dll.</span></span> <span data-ttu-id="d7e81-121">对于该文件系统，这三个文件是三个独立的文件。</span><span class="sxs-lookup"><span data-stu-id="d7e81-121">To the file system, they are three separate files.</span></span> <span data-ttu-id="d7e81-122">请注意，文件 Util.netmodule 被编译为一个模块，因为它不包含任何程序集信息。</span><span class="sxs-lookup"><span data-stu-id="d7e81-122">Note that the file Util.netmodule was compiled as a module because it contains no assembly information.</span></span> <span data-ttu-id="d7e81-123">创建程序集之后，已将该程序集清单添加到指示程序集与 Util.netmodule 和 Graphic.bmp 之间关系的 MyAssembly.dll 中。</span><span class="sxs-lookup"><span data-stu-id="d7e81-123">When the assembly was created, the assembly manifest was added to MyAssembly.dll, indicating its relationship with Util.netmodule and Graphic.bmp.</span></span>  
  
 <span data-ttu-id="d7e81-124">现在设计源代码时，你会作出有关如何将应用程序的功能划分到一个或多个文件的明确的决定。</span><span class="sxs-lookup"><span data-stu-id="d7e81-124">As you currently design your source code, you make explicit decisions about how to partition the functionality of your application into one or more files.</span></span> <span data-ttu-id="d7e81-125">在设计 .NET Framework 代码时，你也将作出类似的决定，即如何将应用程序的功能划分到一个或多个程序集中。</span><span class="sxs-lookup"><span data-stu-id="d7e81-125">When designing .NET Framework code, you will make similar decisions about how to partition the functionality into one or more assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7e81-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7e81-126">See also</span></span>

- <span data-ttu-id="d7e81-127">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)（公共语言运行时中的程序集）</span><span class="sxs-lookup"><span data-stu-id="d7e81-127">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)</span></span>
- [<span data-ttu-id="d7e81-128">程序集清单</span><span class="sxs-lookup"><span data-stu-id="d7e81-128">Assembly Manifest</span></span>](../../../docs/framework/app-domains/assembly-manifest.md)
- [<span data-ttu-id="d7e81-129">程序集安全注意事项</span><span class="sxs-lookup"><span data-stu-id="d7e81-129">Assembly Security Considerations</span></span>](../../../docs/framework/app-domains/assembly-security-considerations.md)
