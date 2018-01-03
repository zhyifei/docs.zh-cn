---
title: "COM 互操作介绍 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interop assemblies
- COM interop [Visual Basic], about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 39a4245b51c1199a6aeb0c23282b1917f51164d2
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="introduction-to-com-interop-visual-basic"></a><span data-ttu-id="7eacf-102">COM 互操作介绍 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7eacf-102">Introduction to COM Interop (Visual Basic)</span></span>
<span data-ttu-id="7eacf-103">组件对象模型 (COM) 允许到其他组件和承载应用程序公开其功能的对象。</span><span class="sxs-lookup"><span data-stu-id="7eacf-103">The Component Object Model (COM) lets an object expose its functionality to other components and to host applications.</span></span> <span data-ttu-id="7eacf-104">COM 对象进行了 Windows 编程多年的基础，而应用程序面向公共语言运行时 (CLR) 提供了许多优点。</span><span class="sxs-lookup"><span data-stu-id="7eacf-104">While COM objects have been fundamental to Windows programming for many years, applications designed for the common language runtime (CLR) offer many advantages.</span></span>  
  
 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]<span data-ttu-id="7eacf-105">com 开发的那些，最终将取代应用程序</span><span class="sxs-lookup"><span data-stu-id="7eacf-105"> applications will eventually replace those developed with COM.</span></span> <span data-ttu-id="7eacf-106">到那时，你可能必须使用或通过创建 COM 对象[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7eacf-106">Until then, you may have to use or create COM objects by using [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span></span> <span data-ttu-id="7eacf-107">与 COM 互操作性或*COM 互操作*，使你能够使用现有的 COM 对象时转换到[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]在自己的进度。</span><span class="sxs-lookup"><span data-stu-id="7eacf-107">Interoperability with COM, or *COM interop*, enables you to use existing COM objects while transitioning to the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] at your own pace.</span></span>  
  
 <span data-ttu-id="7eacf-108">通过使用[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]若要创建 COM 组件，你可以使用免注册 COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="7eacf-108">By using the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] to create COM components, you can use registration-free COM interop.</span></span> <span data-ttu-id="7eacf-109">这使您控制当多个版本的计算机上，安装并允许最终用户使用 XCOPY 或 FTP 将复制到其计算机上的相应目录的应用程序可以运行它的位置时，才启用哪个 DLL 版本。</span><span class="sxs-lookup"><span data-stu-id="7eacf-109">This lets you control which DLL version is enabled when more than one version is installed on a computer, and lets end users use XCOPY or FTP to copy your application to an appropriate directory on their computer where it can be run.</span></span> <span data-ttu-id="7eacf-110">有关详细信息，请参阅[免注册 COM 互操作](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd)。</span><span class="sxs-lookup"><span data-stu-id="7eacf-110">For more information, see [Registration-Free COM Interop](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd).</span></span>  
  
## <a name="managed-code-and-data"></a><span data-ttu-id="7eacf-111">托管的代码和数据</span><span class="sxs-lookup"><span data-stu-id="7eacf-111">Managed Code and Data</span></span>  
 <span data-ttu-id="7eacf-112">有关开发代码[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]称为*托管代码*，并包含由 CLR 的元数据。</span><span class="sxs-lookup"><span data-stu-id="7eacf-112">Code developed for the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] is referred to as *managed code*, and contains metadata that is used by the CLR.</span></span> <span data-ttu-id="7eacf-113">使用的数据[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]应用程序称为*托管的数据*因为运行时管理数据相关的任务，比如分配和回收内存以及执行类型检查。</span><span class="sxs-lookup"><span data-stu-id="7eacf-113">Data used by [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] applications is called *managed data* because the runtime manages data-related tasks such as allocating and reclaiming memory and performing type checking.</span></span> <span data-ttu-id="7eacf-114">默认情况下，Visual Basic.NET 中使用托管的代码和数据，但你可以访问非托管的代码和 COM 对象使用互操作程序集 （后面将介绍在此页上） 的数据。</span><span class="sxs-lookup"><span data-stu-id="7eacf-114">By default, Visual Basic .NET uses managed code and data, but you can access the unmanaged code and data of COM objects using interop assemblies (described later on this page).</span></span>  
  
## <a name="assemblies"></a><span data-ttu-id="7eacf-115">程序集</span><span class="sxs-lookup"><span data-stu-id="7eacf-115">Assemblies</span></span>  
 <span data-ttu-id="7eacf-116">程序集是主要构建基块的[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="7eacf-116">An assembly is the primary building block of a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] application.</span></span> <span data-ttu-id="7eacf-117">它是功能的一个已生成、 版本控制的并作为单个实现单元包含一个或多个文件已部署的集合。</span><span class="sxs-lookup"><span data-stu-id="7eacf-117">It is a collection of functionality that is built, versioned, and deployed as a single implementation unit containing one or more files.</span></span> <span data-ttu-id="7eacf-118">每个程序集包含程序集清单。</span><span class="sxs-lookup"><span data-stu-id="7eacf-118">Each assembly contains an assembly manifest.</span></span>  
  
## <a name="type-libraries-and-assembly-manifests"></a><span data-ttu-id="7eacf-119">类型库和程序集清单</span><span class="sxs-lookup"><span data-stu-id="7eacf-119">Type Libraries and Assembly Manifests</span></span>  
 <span data-ttu-id="7eacf-120">类型库描述的 COM 对象，例如成员名称和数据类型的特征。</span><span class="sxs-lookup"><span data-stu-id="7eacf-120">Type libraries describe characteristics of COM objects, such as member names and data types.</span></span> <span data-ttu-id="7eacf-121">程序集清单执行的相同函数[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="7eacf-121">Assembly manifests perform the same function for [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="7eacf-122">它们包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="7eacf-122">They include information about the following:</span></span>  
  
-   <span data-ttu-id="7eacf-123">程序集标识、 版本、 区域性和数字签名。</span><span class="sxs-lookup"><span data-stu-id="7eacf-123">Assembly identity, version, culture, and digital signature.</span></span>  
  
-   <span data-ttu-id="7eacf-124">构成程序集实现的文件。</span><span class="sxs-lookup"><span data-stu-id="7eacf-124">Files that make up the assembly implementation.</span></span>  
  
-   <span data-ttu-id="7eacf-125">类型和构成该程序集的资源。</span><span class="sxs-lookup"><span data-stu-id="7eacf-125">Types and resources that make up the assembly.</span></span> <span data-ttu-id="7eacf-126">这包括那些从其导出。</span><span class="sxs-lookup"><span data-stu-id="7eacf-126">This includes those that are exported from it.</span></span>  
  
-   <span data-ttu-id="7eacf-127">编译时对其他程序集的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="7eacf-127">Compile-time dependencies on other assemblies.</span></span>  
  
-   <span data-ttu-id="7eacf-128">要正确运行的程序集所需的权限。</span><span class="sxs-lookup"><span data-stu-id="7eacf-128">Permissions required for the assembly to run correctly.</span></span>  
  
 <span data-ttu-id="7eacf-129">有关程序集和程序集清单的详细信息，请参阅[程序集和全局程序集缓存](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)。</span><span class="sxs-lookup"><span data-stu-id="7eacf-129">For more information about assemblies and assembly manifests, see [Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).</span></span>  
  
### <a name="importing-and-exporting-type-libraries"></a><span data-ttu-id="7eacf-130">导入和导出类型库</span><span class="sxs-lookup"><span data-stu-id="7eacf-130">Importing and Exporting Type Libraries</span></span>  
 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="7eacf-131">包含一个实用工具，Tlbimp，它允许你从类型库到导入信息[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="7eacf-131"> contains a utility, Tlbimp, that lets you import information from a type library into a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] application.</span></span> <span data-ttu-id="7eacf-132">通过使用 Tlbexp 实用程序，可以从程序集生成类型库。</span><span class="sxs-lookup"><span data-stu-id="7eacf-132">You can generate type libraries from assemblies by using the Tlbexp utility.</span></span>  
  
 <span data-ttu-id="7eacf-133">有关 Tlbimp 和 Tlbexp 的信息，请参阅[Tlbimp.exe （类型库导入程序）](../../../framework/tools/tlbimp-exe-type-library-importer.md)和[Tlbexp.exe （类型库导出程序）](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)。</span><span class="sxs-lookup"><span data-stu-id="7eacf-133">For information about Tlbimp and Tlbexp, see [Tlbimp.exe (Type Library Importer)](../../../framework/tools/tlbimp-exe-type-library-importer.md) and [Tlbexp.exe (Type Library Exporter)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d).</span></span>  
  
## <a name="interop-assemblies"></a><span data-ttu-id="7eacf-134">互操作程序集</span><span class="sxs-lookup"><span data-stu-id="7eacf-134">Interop Assemblies</span></span>  
 <span data-ttu-id="7eacf-135">互操作程序集是[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]代码的桥之间托管和非托管的程序集，映射到等效的 COM 对象成员[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]管理成员。</span><span class="sxs-lookup"><span data-stu-id="7eacf-135">Interop assemblies are [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies that bridge between managed and unmanaged code, mapping COM object members to equivalent [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] managed members.</span></span> <span data-ttu-id="7eacf-136">Visual Basic.net 创建的互操作程序集处理的许多使用 COM 对象，如互操作封送处理的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7eacf-136">Interop assemblies created by Visual Basic .NET handle many of the details of working with COM objects, such as interoperability marshaling.</span></span>  
  
## <a name="interoperability-marshaling"></a><span data-ttu-id="7eacf-137">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="7eacf-137">Interoperability Marshaling</span></span>  
 <span data-ttu-id="7eacf-138">所有[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]应用程序共享的一组启用的对象，而不考虑使用的编程语言的互操作性的常见类型。</span><span class="sxs-lookup"><span data-stu-id="7eacf-138">All [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] applications share a set of common types that enable interoperability of objects, regardless of the programming language that is used.</span></span> <span data-ttu-id="7eacf-139">参数和返回值的 COM 对象有时使用不同于在托管代码中使用的数据类型。</span><span class="sxs-lookup"><span data-stu-id="7eacf-139">The parameters and return values of COM objects sometimes use data types that differ from those used in managed code.</span></span> <span data-ttu-id="7eacf-140">*互操作封送处理*是打包参数和返回值为等效的数据类型的过程，因为它们移动到和从 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="7eacf-140">*Interoperability marshaling* is the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="7eacf-141">有关详细信息，请参阅[互操作封送处理](../../../framework/interop/interop-marshaling.md)。</span><span class="sxs-lookup"><span data-stu-id="7eacf-141">For more information, see [Interop Marshaling](../../../framework/interop/interop-marshaling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eacf-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="7eacf-142">See Also</span></span>  
 [<span data-ttu-id="7eacf-143">COM 互操作</span><span class="sxs-lookup"><span data-stu-id="7eacf-143">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 [<span data-ttu-id="7eacf-144">演练：使用 COM 对象实现继承</span><span class="sxs-lookup"><span data-stu-id="7eacf-144">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [<span data-ttu-id="7eacf-145">与非托管代码交互操作</span><span class="sxs-lookup"><span data-stu-id="7eacf-145">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)  
 [<span data-ttu-id="7eacf-146">互操作性疑难解答</span><span class="sxs-lookup"><span data-stu-id="7eacf-146">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 [<span data-ttu-id="7eacf-147">程序集和全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="7eacf-147">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="7eacf-148">Tlbimp.exe（类型库导入程序）</span><span class="sxs-lookup"><span data-stu-id="7eacf-148">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [<span data-ttu-id="7eacf-149">Tlbexp.exe（类型库导出程序）</span><span class="sxs-lookup"><span data-stu-id="7eacf-149">Tlbexp.exe (Type Library Exporter)</span></span>](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [<span data-ttu-id="7eacf-150">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="7eacf-150">Interop Marshaling</span></span>](../../../framework/interop/interop-marshaling.md)  
 [<span data-ttu-id="7eacf-151">免注册 COM 互操作</span><span class="sxs-lookup"><span data-stu-id="7eacf-151">Registration-Free COM Interop</span></span>](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd)
