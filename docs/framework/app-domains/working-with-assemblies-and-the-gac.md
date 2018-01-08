---
title: "使用程序集和全局程序集缓存"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, benefits
- ACLs [.NET Framework]
- GAC (global assembly cache), benefits
- access control lists [.NET Framework]
ms.assetid: 8a18e5c2-d41d-49ef-abcb-7c27e2469433
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6f1ee4855745573a4b73b409279d70906191bfd8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="working-with-assemblies-and-the-global-assembly-cache"></a><span data-ttu-id="33279-102">使用程序集和全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="33279-102">Working with Assemblies and the Global Assembly Cache</span></span>
<span data-ttu-id="33279-103">如果需要在几个应用程序间共享程序集，可将其安装到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="33279-103">If you intend to share an assembly among several applications, you can install it into the global assembly cache.</span></span> <span data-ttu-id="33279-104">安装了公共语言运行时的每台计算机均具有此计算机范围的代码缓存。</span><span class="sxs-lookup"><span data-stu-id="33279-104">Each computer where the common language runtime is installed has this machine-wide code cache.</span></span> <span data-ttu-id="33279-105">全局程序集缓存中存储专门指定给由计算机中若干应用程序共享的程序集。</span><span class="sxs-lookup"><span data-stu-id="33279-105">The global assembly cache stores assemblies specifically designated to be shared by several applications on the computer.</span></span> <span data-ttu-id="33279-106">程序集必须具有强名称才可安装到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="33279-106">An assembly must have a strong name to be installed in the global assembly cache.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33279-107">全局程序集缓存中放置的程序集必须具有相同的程序集名称和文件名（不包括文件扩展名）。</span><span class="sxs-lookup"><span data-stu-id="33279-107">Assemblies placed in the global assembly cache must have the same assembly name and file name (not including the file name extension).</span></span> <span data-ttu-id="33279-108">例如，程序集名称为 myAssembly 的程序集必须具有名为 myAssembly.exe 或 myAssembly.dll 的文件。</span><span class="sxs-lookup"><span data-stu-id="33279-108">For example, an assembly with the assembly name of myAssembly must have a file name of either myAssembly.exe or myAssembly.dll.</span></span>  
  
 <span data-ttu-id="33279-109">只能在需要时才通过将程序集安装到全局程序集缓存中来共享程序集。</span><span class="sxs-lookup"><span data-stu-id="33279-109">You should share assemblies by installing them into the global assembly cache only when necessary.</span></span> <span data-ttu-id="33279-110">一般原则是：程序集依赖项保持专用，并在应用程序目录中定位程序集，除非明确要求共享程序集。</span><span class="sxs-lookup"><span data-stu-id="33279-110">As a general guideline, keep assembly dependencies private and locate assemblies in the application directory unless sharing an assembly is explicitly required.</span></span> <span data-ttu-id="33279-111">另外，无需为了使程序集可以访问 COM 互操作或非托管代码而将程序集安装到全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="33279-111">In addition, you do not have to install assemblies into the global assembly cache to make them accessible to COM interop or unmanaged code.</span></span>  
  
 <span data-ttu-id="33279-112">建议将程序集安装到全局程序集缓存中的原因有以下几点：</span><span class="sxs-lookup"><span data-stu-id="33279-112">There are several reasons why you might want to install an assembly into the global assembly cache:</span></span>  
  
-   <span data-ttu-id="33279-113">共享位置。</span><span class="sxs-lookup"><span data-stu-id="33279-113">Shared location.</span></span>  
  
     <span data-ttu-id="33279-114">应该由应用程序使用的程序集可以置于全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="33279-114">Assemblies that should be used by applications can be put in the global assembly cache.</span></span> <span data-ttu-id="33279-115">例如，如果所有应用程序都应使用位于全局程序集缓存中的程序集，则可将版本策略语句添加到 Machine.config 文件中，此文件将引用重新定向到程序集。</span><span class="sxs-lookup"><span data-stu-id="33279-115">For example, if all applications should use an assembly located in the global assembly cache, a version policy statement can be added to the Machine.config file that redirects references to the assembly.</span></span>  
  
-   <span data-ttu-id="33279-116">文件安全。</span><span class="sxs-lookup"><span data-stu-id="33279-116">File security.</span></span>  
  
     <span data-ttu-id="33279-117">管理员通常使用访问控制列表 (ACL) 来保护 systemroot 目录，从而控制写入和执行访问。</span><span class="sxs-lookup"><span data-stu-id="33279-117">Administrators often protect the systemroot directory using an Access Control List (ACL) to control write and execute access.</span></span> <span data-ttu-id="33279-118">由于全局程序集缓存安装在 systemroot 目录中，因此它将继承该目录的 ACL。</span><span class="sxs-lookup"><span data-stu-id="33279-118">Because the global assembly cache is installed in the systemroot directory, it inherits that directory's ACL.</span></span> <span data-ttu-id="33279-119">建议只允许具有“管理员”权限的用户从全局程序集缓存中删除文件。</span><span class="sxs-lookup"><span data-stu-id="33279-119">It is recommended that only users with Administrator privileges be allowed to delete files from the global assembly cache.</span></span>  
  
-   <span data-ttu-id="33279-120">并行版本。</span><span class="sxs-lookup"><span data-stu-id="33279-120">Side-by-side versioning.</span></span>  
  
     <span data-ttu-id="33279-121">可在全局程序集缓存中维护名称相同但版本信息不同的程序集的多个副本。</span><span class="sxs-lookup"><span data-stu-id="33279-121">Multiple copies of assemblies with the same name but different version information can be maintained in the global assembly cache.</span></span>  
  
-   <span data-ttu-id="33279-122">其他搜索位置。</span><span class="sxs-lookup"><span data-stu-id="33279-122">Additional search location.</span></span>  
  
     <span data-ttu-id="33279-123">在探测或使用配置文件中的基本代码信息之前，公共语言运行时会先检查全局程序集缓存中符合程序集请求的程序集。</span><span class="sxs-lookup"><span data-stu-id="33279-123">The common language runtime checks the global assembly cache for an assembly that matches the assembly request before probing or using the codebase information in a configuration file.</span></span>  
  
 <span data-ttu-id="33279-124">请注意，在有些情况下，很明显不需要将程序集安装到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="33279-124">Note that there are scenarios where you explicitly do not want to install an assembly into the global assembly cache.</span></span> <span data-ttu-id="33279-125">如果将组成应用程序的某个程序集置于全局程序集缓存中，就无法再通过使用 XCOPY 复制应用程序目录来复制或安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="33279-125">If you place one of the assemblies that make up an application into the global assembly cache, you can no longer replicate or install the application by using XCOPY to copy the application directory.</span></span> <span data-ttu-id="33279-126">在这种情况下，还必须将程序集移到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="33279-126">In this case, you must also move the assembly into the global assembly cache.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="33279-127">本节内容</span><span class="sxs-lookup"><span data-stu-id="33279-127">In This Section</span></span>  
 [<span data-ttu-id="33279-128">如何：将程序集安装到全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="33279-128">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 <span data-ttu-id="33279-129">描述将程序集安装到全局程序集缓存的方法。</span><span class="sxs-lookup"><span data-stu-id="33279-129">Describes the ways to install an assembly into the global assembly cache.</span></span>  
  
 [<span data-ttu-id="33279-130">如何：查看全局程序集缓存的内容</span><span class="sxs-lookup"><span data-stu-id="33279-130">How to: View the Contents of the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/how-to-view-the-contents-of-the-gac.md)  
 <span data-ttu-id="33279-131">说明如何使用 [Gacutil.exe（全局程序集缓存工具）](../../../docs/framework/tools/gacutil-exe-gac-tool.md)来查看全局程序集缓存的内容。</span><span class="sxs-lookup"><span data-stu-id="33279-131">Explains how to use the [Gacutil.exe (Global Assembly Cache Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="33279-132">如何：从全局程序集缓存中删除程序集</span><span class="sxs-lookup"><span data-stu-id="33279-132">How to: Remove an Assembly from the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/how-to-remove-an-assembly-from-the-gac.md)  
 <span data-ttu-id="33279-133">说明如何使用 [Gacutil.exe（全局程序集缓存工具）](../../../docs/framework/tools/gacutil-exe-gac-tool.md)从全局程序集缓存中删除程序集。</span><span class="sxs-lookup"><span data-stu-id="33279-133">Explains how to use the [Gacutil.exe (Global Assembly Cache Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to remove an assembly from the global assembly cache.</span></span>  
  
 [<span data-ttu-id="33279-134">将服务组件和全局程序集缓存结合使用</span><span class="sxs-lookup"><span data-stu-id="33279-134">Using Serviced Components with the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/use-serviced-components-with-the-gac.md)  
 <span data-ttu-id="33279-135">说明服务组件（托管 COM+ 组件）应置于全局程序集缓存中的原因。</span><span class="sxs-lookup"><span data-stu-id="33279-135">Explains why serviced components (managed COM+ components) should be placed in the global assembly cache.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="33279-136">相关章节</span><span class="sxs-lookup"><span data-stu-id="33279-136">Related Sections</span></span>  
 [<span data-ttu-id="33279-137">创建程序集</span><span class="sxs-lookup"><span data-stu-id="33279-137">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 <span data-ttu-id="33279-138">概述创建程序集。</span><span class="sxs-lookup"><span data-stu-id="33279-138">Provides an overview of creating assemblies.</span></span>  
  
 [<span data-ttu-id="33279-139">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="33279-139">Global Assembly Cache</span></span>](../../../docs/framework/app-domains/gac.md)  
 <span data-ttu-id="33279-140">描述全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="33279-140">Describes the global assembly cache.</span></span>  
  
 [<span data-ttu-id="33279-141">如何：查看程序集内容</span><span class="sxs-lookup"><span data-stu-id="33279-141">How to: View Assembly Contents</span></span>](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 <span data-ttu-id="33279-142">说明如何使用 [Ildasm.exe（IL 反汇编程序）](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)来查看程序集中的 Microsoft 中间语言 (MSIL) 信息。</span><span class="sxs-lookup"><span data-stu-id="33279-142">Explains how to use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to view Microsoft intermediate language (MSIL) information in an assembly.</span></span>  
  
 [<span data-ttu-id="33279-143">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="33279-143">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 <span data-ttu-id="33279-144">描述公共语言运行时如何查找并加载构成应用程序的程序集。</span><span class="sxs-lookup"><span data-stu-id="33279-144">Describes how the common language runtime locates and loads the assemblies that make up your application.</span></span>  
  
 [<span data-ttu-id="33279-145">使用程序集编程</span><span class="sxs-lookup"><span data-stu-id="33279-145">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 <span data-ttu-id="33279-146">描述托管应用程序的构造块 - 程序集。</span><span class="sxs-lookup"><span data-stu-id="33279-146">Describes assemblies, the building blocks of managed applications.</span></span>
