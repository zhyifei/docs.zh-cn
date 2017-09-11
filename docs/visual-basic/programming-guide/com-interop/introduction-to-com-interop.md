---
title: "COM 互操作 (Visual Basic 中) 的简介 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- interop assemblies
- COM interop, about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6a50a89db3f24d7e34c1fc683b5f712f3a6992bf
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="introduction-to-com-interop-visual-basic"></a><span data-ttu-id="be257-102">COM 互操作介绍 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be257-102">Introduction to COM Interop (Visual Basic)</span></span>
<span data-ttu-id="be257-103">组件对象模型 (COM)，可以对其他组件和主机应用程序公开其功能的对象。</span><span class="sxs-lookup"><span data-stu-id="be257-103">The Component Object Model (COM) lets an object expose its functionality to other components and to host applications.</span></span> <span data-ttu-id="be257-104">虽然 COM 对象已被 Windows 多年编程的基础，面向公共语言运行时 (CLR) 的应用程序提供了许多优点。</span><span class="sxs-lookup"><span data-stu-id="be257-104">While COM objects have been fundamental to Windows programming for many years, applications designed for the common language runtime (CLR) offer many advantages.</span></span>  
  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]<span data-ttu-id="be257-105">应用程序将最终取代那些 com 开发</span><span class="sxs-lookup"><span data-stu-id="be257-105"> applications will eventually replace those developed with COM.</span></span> <span data-ttu-id="be257-106">到那时，你可能需要使用或创建 COM 对象使用[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="be257-106">Until then, you may have to use or create COM objects by using [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)].</span></span> <span data-ttu-id="be257-107">通过 COM 互操作性或*COM 互操作*，使您能够使用现有的 COM 对象时转换到[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]按您自己的节奏。</span><span class="sxs-lookup"><span data-stu-id="be257-107">Interoperability with COM, or *COM interop*, enables you to use existing COM objects while transitioning to the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] at your own pace.</span></span>  
  
 <span data-ttu-id="be257-108">通过使用[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]若要创建 COM 组件，可以使用免注册 COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="be257-108">By using the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] to create COM components, you can use registration-free COM interop.</span></span> <span data-ttu-id="be257-109">这样就可以控制哪些 DLL 版本启用多个版本已安装的计算机上，并且可让最终用户使用 XCOPY 或 FTP 将复制到其计算机上的相应目录的应用程序可以运行时。</span><span class="sxs-lookup"><span data-stu-id="be257-109">This lets you control which DLL version is enabled when more than one version is installed on a computer, and lets end users use XCOPY or FTP to copy your application to an appropriate directory on their computer where it can be run.</span></span> <span data-ttu-id="be257-110">有关详细信息，请参阅[免注册 COM 互操作](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd)。</span><span class="sxs-lookup"><span data-stu-id="be257-110">For more information, see [Registration-Free COM Interop](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd).</span></span>  
  
## <a name="managed-code-and-data"></a><span data-ttu-id="be257-111">托管的代码和数据</span><span class="sxs-lookup"><span data-stu-id="be257-111">Managed Code and Data</span></span>  
 <span data-ttu-id="be257-112">有关开发的代码[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]称为*托管代码*，并包含由 CLR 使用元数据。</span><span class="sxs-lookup"><span data-stu-id="be257-112">Code developed for the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] is referred to as *managed code*, and contains metadata that is used by CLR.</span></span> <span data-ttu-id="be257-113">所使用的数据[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]应用程序称为*托管数据*因为运行时管理与数据相关的任务，比如分配和回收内存以及执行类型检查。</span><span class="sxs-lookup"><span data-stu-id="be257-113">Data used by [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] applications is called *managed data* because the runtime manages data-related tasks such as allocating and reclaiming memory and performing type checking.</span></span> <span data-ttu-id="be257-114">默认情况下，[!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)]使用托管代码和数据，但是您可以访问的非托管的代码和数据的 COM 对象使用互操作程序集 （请参阅本页后面的说明）。</span><span class="sxs-lookup"><span data-stu-id="be257-114">By default, [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] uses managed code and data, but you can access the unmanaged code and data of COM objects using interop assemblies (described later on this page).</span></span>  
  
## <a name="assemblies"></a><span data-ttu-id="be257-115">程序集</span><span class="sxs-lookup"><span data-stu-id="be257-115">Assemblies</span></span>  
 <span data-ttu-id="be257-116">程序集是主要构建基块的[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="be257-116">An assembly is the primary building block of a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] application.</span></span> <span data-ttu-id="be257-117">它是功能的一个已生成、 版本控制，并作为单个实现单元包含一个或多个文件已部署的集合。</span><span class="sxs-lookup"><span data-stu-id="be257-117">It is a collection of functionality that is built, versioned, and deployed as a single implementation unit containing one or more files.</span></span> <span data-ttu-id="be257-118">每个程序集包含程序集清单。</span><span class="sxs-lookup"><span data-stu-id="be257-118">Each assembly contains an assembly manifest.</span></span>  
  
## <a name="type-libraries-and-assembly-manifests"></a><span data-ttu-id="be257-119">类型库和程序集清单</span><span class="sxs-lookup"><span data-stu-id="be257-119">Type Libraries and Assembly Manifests</span></span>  
 <span data-ttu-id="be257-120">类型库描述 COM 对象，如成员名称和数据类型的特征。</span><span class="sxs-lookup"><span data-stu-id="be257-120">Type libraries describe characteristics of COM objects, such as member names and data types.</span></span> <span data-ttu-id="be257-121">程序集清单执行的相同函数[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="be257-121">Assembly manifests perform the same function for [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] applications.</span></span> <span data-ttu-id="be257-122">它们包括以下信息︰</span><span class="sxs-lookup"><span data-stu-id="be257-122">They include information about the following:</span></span>  
  
-   <span data-ttu-id="be257-123">程序集标识、 版本、 区域性和数字签名。</span><span class="sxs-lookup"><span data-stu-id="be257-123">Assembly identity, version, culture, and digital signature.</span></span>  
  
-   <span data-ttu-id="be257-124">组成程序集实现的文件。</span><span class="sxs-lookup"><span data-stu-id="be257-124">Files that make up the assembly implementation.</span></span>  
  
-   <span data-ttu-id="be257-125">类型和构成该程序集的资源。</span><span class="sxs-lookup"><span data-stu-id="be257-125">Types and resources that make up the assembly.</span></span> <span data-ttu-id="be257-126">这包括那些从其导出。</span><span class="sxs-lookup"><span data-stu-id="be257-126">This includes those that are exported from it.</span></span>  
  
-   <span data-ttu-id="be257-127">对其他程序集的编译时依赖项。</span><span class="sxs-lookup"><span data-stu-id="be257-127">Compile-time dependencies on other assemblies.</span></span>  
  
-   <span data-ttu-id="be257-128">要正确运行所必需的程序集所需的权限。</span><span class="sxs-lookup"><span data-stu-id="be257-128">Permissions required for the assembly to run correctly.</span></span>  
  
 <span data-ttu-id="be257-129">有关程序集和程序集清单的详细信息，请参阅[程序集和全局程序集缓存](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)。</span><span class="sxs-lookup"><span data-stu-id="be257-129">For more information about assemblies and assembly manifests, see [Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).</span></span>  
  
### <a name="importing-and-exporting-type-libraries"></a><span data-ttu-id="be257-130">导入和导出类型库</span><span class="sxs-lookup"><span data-stu-id="be257-130">Importing and Exporting Type Libraries</span></span>  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]<span data-ttu-id="be257-131">包含一个实用工具，Tlbimp，它允许您将信息导入从类型库到[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="be257-131"> contains a utility, Tlbimp, that lets you import information from a type library into a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] application.</span></span> <span data-ttu-id="be257-132">通过使用 Tlbexp 实用程序，可以从程序集生成类型库。</span><span class="sxs-lookup"><span data-stu-id="be257-132">You can generate type libraries from assemblies by using the Tlbexp utility.</span></span>  
  
 <span data-ttu-id="be257-133">Tlbimp 和 Tlbexp 有关的信息，请参阅[Tlbimp.exe （类型库导入程序）](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)和[Tlbexp.exe （类型库导出程序）](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)。</span><span class="sxs-lookup"><span data-stu-id="be257-133">For information about Tlbimp and Tlbexp, see [Tlbimp.exe (Type Library Importer)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382) and [Tlbexp.exe (Type Library Exporter)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d).</span></span>  
  
## <a name="interop-assemblies"></a><span data-ttu-id="be257-134">互操作程序集</span><span class="sxs-lookup"><span data-stu-id="be257-134">Interop Assemblies</span></span>  
 <span data-ttu-id="be257-135">互操作程序集是[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]代码的桥之间托管和非托管的程序集，将 COM 对象成员映射到等效[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]托管成员。</span><span class="sxs-lookup"><span data-stu-id="be257-135">Interop assemblies are [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies that bridge between managed and unmanaged code, mapping COM object members to equivalent [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] managed members.</span></span> <span data-ttu-id="be257-136">互操作程序集由创建[!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)]处理很多使用 COM 对象，如互操作封送处理的详细信息。</span><span class="sxs-lookup"><span data-stu-id="be257-136">Interop assemblies created by [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] handle many of the details of working with COM objects, such as interoperability marshaling.</span></span>  
  
## <a name="interoperability-marshaling"></a><span data-ttu-id="be257-137">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="be257-137">Interoperability Marshaling</span></span>  
 <span data-ttu-id="be257-138">所有[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]应用程序共享一组实现的对象，而不考虑使用的编程语言的互操作性的公共类型。</span><span class="sxs-lookup"><span data-stu-id="be257-138">All [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] applications share a set of common types that enable interoperability of objects, regardless of the programming language that is used.</span></span> <span data-ttu-id="be257-139">参数和返回值的 COM 对象有时使用不同于在托管代码中使用的数据类型。</span><span class="sxs-lookup"><span data-stu-id="be257-139">The parameters and return values of COM objects sometimes use data types that differ from those used in managed code.</span></span> <span data-ttu-id="be257-140">*互操作封送处理*为它们移动到和从 COM 对象包装参数和返回值为等效的数据类型的过程。</span><span class="sxs-lookup"><span data-stu-id="be257-140">*Interoperability marshaling* is the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="be257-141">有关详细信息，请参阅[互操作封送处理](http://msdn.microsoft.com/library/115f7a2f-d422-4605-ab36-13a8dd28142a)。</span><span class="sxs-lookup"><span data-stu-id="be257-141">For more information, see [Interop Marshaling](http://msdn.microsoft.com/library/115f7a2f-d422-4605-ab36-13a8dd28142a).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be257-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be257-142">See Also</span></span>  
 <span data-ttu-id="be257-143">[COM 互操作](../../../visual-basic/programming-guide/com-interop/index.md) </span><span class="sxs-lookup"><span data-stu-id="be257-143">[COM Interop](../../../visual-basic/programming-guide/com-interop/index.md) </span></span>  
<span data-ttu-id="be257-144"> [演练︰ 用 COM 对象实现继承](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md) </span><span class="sxs-lookup"><span data-stu-id="be257-144"> [Walkthrough: Implementing Inheritance with COM Objects](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md) </span></span>  
<span data-ttu-id="be257-145"> [与非托管代码交互操作](https://msdn.microsoft.com/library/sd10k43k) </span><span class="sxs-lookup"><span data-stu-id="be257-145"> [Interoperating with Unmanaged Code](https://msdn.microsoft.com/library/sd10k43k) </span></span>  
<span data-ttu-id="be257-146"> [互操作性疑难解答](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md) </span><span class="sxs-lookup"><span data-stu-id="be257-146"> [Troubleshooting Interoperability](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md) </span></span>  
<span data-ttu-id="be257-147"> [程序集和全局程序集缓存](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="be257-147"> [Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="be257-148"> [Tlbimp.exe （类型库导入程序）](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382) </span><span class="sxs-lookup"><span data-stu-id="be257-148"> [Tlbimp.exe (Type Library Importer)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382) </span></span>  
<span data-ttu-id="be257-149"> [Tlbexp.exe （类型库导出程序）](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d) </span><span class="sxs-lookup"><span data-stu-id="be257-149"> [Tlbexp.exe (Type Library Exporter)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d) </span></span>  
<span data-ttu-id="be257-150"> [互操作封送处理](http://msdn.microsoft.com/library/115f7a2f-d422-4605-ab36-13a8dd28142a) </span><span class="sxs-lookup"><span data-stu-id="be257-150"> [Interop Marshaling](http://msdn.microsoft.com/library/115f7a2f-d422-4605-ab36-13a8dd28142a) </span></span>  
<span data-ttu-id="be257-151"> [免注册 COM 互操作](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd)</span><span class="sxs-lookup"><span data-stu-id="be257-151"> [Registration-Free COM Interop](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd)</span></span>
