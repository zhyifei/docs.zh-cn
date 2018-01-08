---
title: "程序集内容"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- assemblies [.NET Framework], single-file
- single-file assemblies
- multifile assemblies
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a0af2a90d4951b72f8c5100affd6d78ac7f31ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="assembly-contents"></a><span data-ttu-id="e06c9-102">程序集内容</span><span class="sxs-lookup"><span data-stu-id="e06c9-102">Assembly Contents</span></span>
<span data-ttu-id="e06c9-103">通常，静态程序集可能由以下四个元素组成：</span><span class="sxs-lookup"><span data-stu-id="e06c9-103">In general, a static assembly can consist of four elements:</span></span>  
  
-   <span data-ttu-id="e06c9-104">[程序集清单](../../../docs/framework/app-domains/assembly-manifest.md)，包含程序集元数据。</span><span class="sxs-lookup"><span data-stu-id="e06c9-104">The [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md), which contains assembly metadata.</span></span>  
  
-   <span data-ttu-id="e06c9-105">类型元数据。</span><span class="sxs-lookup"><span data-stu-id="e06c9-105">Type metadata.</span></span>  
  
-   <span data-ttu-id="e06c9-106">实现这些类型的 Microsoft 中间语言 (MSIL) 代码。</span><span class="sxs-lookup"><span data-stu-id="e06c9-106">Microsoft intermediate language (MSIL) code that implements the types.</span></span>  
  
-   <span data-ttu-id="e06c9-107">资源集。</span><span class="sxs-lookup"><span data-stu-id="e06c9-107">A set of resources.</span></span>  
  
 <span data-ttu-id="e06c9-108">只有程序集清单是必需的，但也需要类型或资源来向程序集提供任何有意义的功能。</span><span class="sxs-lookup"><span data-stu-id="e06c9-108">Only the assembly manifest is required, but either types or resources are needed to give the assembly any meaningful functionality.</span></span>  
  
 <span data-ttu-id="e06c9-109">程序集中的这些元素有分组几种方法。</span><span class="sxs-lookup"><span data-stu-id="e06c9-109">There are several ways to group these elements in an assembly.</span></span> <span data-ttu-id="e06c9-110">您可以将所有元素分组到单个物理文件中，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="e06c9-110">You can group all elements in a single physical file, which is shown in the following illustration.</span></span>  
  
 <span data-ttu-id="e06c9-111">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover1.gif "assemblyover1")</span><span class="sxs-lookup"><span data-stu-id="e06c9-111">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover1.gif "assemblyover1")</span></span>  
<span data-ttu-id="e06c9-112">单文件程序集</span><span class="sxs-lookup"><span data-stu-id="e06c9-112">Single-file assembly</span></span>  
  
 <span data-ttu-id="e06c9-113">或者，可以将一个程序集的元素包含在几个文件中。</span><span class="sxs-lookup"><span data-stu-id="e06c9-113">Alternatively, the elements of an assembly can be contained in several files.</span></span> <span data-ttu-id="e06c9-114">这些文件可以是应用程序所需的编译代码 (.netmodule)、资源（例如，.bmp 或 .jpg 文件）或其他文件的模块。</span><span class="sxs-lookup"><span data-stu-id="e06c9-114">These files can be modules of compiled code (.netmodule), resources (such as .bmp or .jpg files), or other files required by the application.</span></span> <span data-ttu-id="e06c9-115">在您希望组合以不同语言编写的模块并优化应用程序的下载过程时，可创建一个多文件程序集，优化下载过程的方法是将很少使用的类型放入只在需要时才下载的模块中。</span><span class="sxs-lookup"><span data-stu-id="e06c9-115">Create a multifile assembly when you want to combine modules written in different languages and to optimize downloading an application by putting seldom used types in a module that is downloaded only when needed.</span></span>  
  
 <span data-ttu-id="e06c9-116">在下图中，一个假想应用程序的开发人员已选择将一些实用工具代码单独放入另一个模块中，同时在其原文件中保留一个较大的资源文件（在此例中为一个 .bmp 图像）。</span><span class="sxs-lookup"><span data-stu-id="e06c9-116">In the following illustration, the developer of a hypothetical application has chosen to separate some utility code into a different module and to keep a large resource file (in this case a .bmp image) in its original file.</span></span> <span data-ttu-id="e06c9-117">.NET Framework 只在文件被引用时下载该文件；通过将很少引用的代码保留在独立于应用程序的文件中来优化代码下载。</span><span class="sxs-lookup"><span data-stu-id="e06c9-117">The .NET Framework downloads a file only when it is referenced; keeping infrequently referenced code in a separate file from the application optimizes code download.</span></span>  
  
 <span data-ttu-id="e06c9-118">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover2.gif "assemblyover2")</span><span class="sxs-lookup"><span data-stu-id="e06c9-118">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover2.gif "assemblyover2")</span></span>  
<span data-ttu-id="e06c9-119">多文件程序集</span><span class="sxs-lookup"><span data-stu-id="e06c9-119">Multifile assembly</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e06c9-120">构成多文件程序集的那些文件实际上并非由文件系统来链接。</span><span class="sxs-lookup"><span data-stu-id="e06c9-120">The files that make up a multifile assembly are not physically linked by the file system.</span></span> <span data-ttu-id="e06c9-121">它们而是通过程序集清单进行链接，公共语言运行时将这些文件作为一个单元来管理。</span><span class="sxs-lookup"><span data-stu-id="e06c9-121">Rather, they are linked through the assembly manifest and the common language runtime manages them as a unit.</span></span>  
  
 <span data-ttu-id="e06c9-122">在此插图中，所有三个文件均属于一个程序集，如 MyAssembly.dll 所包含的程序集清单文件中所述。</span><span class="sxs-lookup"><span data-stu-id="e06c9-122">In this illustration, all three files belong to an assembly, as described in the assembly manifest contained in MyAssembly.dll.</span></span> <span data-ttu-id="e06c9-123">对于该文件系统，这三个文件是三个独立的文件。</span><span class="sxs-lookup"><span data-stu-id="e06c9-123">To the file system, they are three separate files.</span></span> <span data-ttu-id="e06c9-124">请注意，文件 Util.netmodule 被编译为一个模块，因为它不包含任何程序集信息。</span><span class="sxs-lookup"><span data-stu-id="e06c9-124">Note that the file Util.netmodule was compiled as a module because it contains no assembly information.</span></span> <span data-ttu-id="e06c9-125">创建程序集之后，已将该程序集清单添加到指示程序集与 Util.netmodule 和 Graphic.bmp 之间关系的 MyAssembly.dll 中。</span><span class="sxs-lookup"><span data-stu-id="e06c9-125">When the assembly was created, the assembly manifest was added to MyAssembly.dll, indicating its relationship with Util.netmodule and Graphic.bmp.</span></span>  
  
 <span data-ttu-id="e06c9-126">现在设计源代码时，你会作出有关如何将应用程序的功能划分到一个或多个文件的明确的决定。</span><span class="sxs-lookup"><span data-stu-id="e06c9-126">As you currently design your source code, you make explicit decisions about how to partition the functionality of your application into one or more files.</span></span> <span data-ttu-id="e06c9-127">在设计 .NET Framework 代码时，你也将作出类似的决定，即如何将应用程序的功能划分到一个或多个程序集中。</span><span class="sxs-lookup"><span data-stu-id="e06c9-127">When designing .NET Framework code, you will make similar decisions about how to partition the functionality into one or more assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e06c9-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="e06c9-128">See Also</span></span>  
 <span data-ttu-id="e06c9-129">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)（公共语言运行时中的程序集）</span><span class="sxs-lookup"><span data-stu-id="e06c9-129">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)</span></span>  
 [<span data-ttu-id="e06c9-130">程序集清单</span><span class="sxs-lookup"><span data-stu-id="e06c9-130">Assembly Manifest</span></span>](../../../docs/framework/app-domains/assembly-manifest.md)  
 [<span data-ttu-id="e06c9-131">程序集安全注意事项</span><span class="sxs-lookup"><span data-stu-id="e06c9-131">Assembly Security Considerations</span></span>](../../../docs/framework/app-domains/assembly-security-considerations.md)
