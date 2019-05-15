---
title: COM 互操作介绍 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interop assemblies
- COM interop [Visual Basic], about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
ms.openlocfilehash: 5eb862d75f8870da40af4cd817fa32a3d2781f38
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592724"
---
# <a name="introduction-to-com-interop-visual-basic"></a><span data-ttu-id="1b552-102">COM 互操作介绍 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b552-102">Introduction to COM Interop (Visual Basic)</span></span>
<span data-ttu-id="1b552-103">组件对象模型 (COM) 允许到其他组件和主机应用程序公开其功能的对象。</span><span class="sxs-lookup"><span data-stu-id="1b552-103">The Component Object Model (COM) lets an object expose its functionality to other components and to host applications.</span></span> <span data-ttu-id="1b552-104">虽然 COM 对象的基础 Windows 编程的许多年来，应用程序面向公共语言运行时 (CLR) 提供了许多优点。</span><span class="sxs-lookup"><span data-stu-id="1b552-104">While COM objects have been fundamental to Windows programming for many years, applications designed for the common language runtime (CLR) offer many advantages.</span></span>  
  
 <span data-ttu-id="1b552-105">.NET framework 应用程序最终将取代这些 com 开发</span><span class="sxs-lookup"><span data-stu-id="1b552-105">.NET Framework applications will eventually replace those developed with COM.</span></span> <span data-ttu-id="1b552-106">到那时，您可能需要使用或通过使用 Visual Studio 创建 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="1b552-106">Until then, you may have to use or create COM objects by using Visual Studio.</span></span> <span data-ttu-id="1b552-107">通过 COM 互操作性或*COM 互操作*，使你过渡到.NET Framework 在自己的进度时使用现有的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="1b552-107">Interoperability with COM, or *COM interop*, enables you to use existing COM objects while transitioning to the .NET Framework at your own pace.</span></span>  
  
 <span data-ttu-id="1b552-108">通过使用.NET Framework 创建 COM 组件，可以使用免注册 COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="1b552-108">By using the .NET Framework to create COM components, you can use registration-free COM interop.</span></span> <span data-ttu-id="1b552-109">这样可以控制多个版本的计算机上，安装并可让最终用户使用 XCOPY 或 FTP 复制到其计算机上的相应目录的应用程序可以运行时启用哪些 DLL 版本。</span><span class="sxs-lookup"><span data-stu-id="1b552-109">This lets you control which DLL version is enabled when more than one version is installed on a computer, and lets end users use XCOPY or FTP to copy your application to an appropriate directory on their computer where it can be run.</span></span> <span data-ttu-id="1b552-110">有关详细信息，请参阅[免注册 COM 互操作](../../../framework/interop/registration-free-com-interop.md)。</span><span class="sxs-lookup"><span data-stu-id="1b552-110">For more information, see [Registration-Free COM Interop](../../../framework/interop/registration-free-com-interop.md).</span></span>  
  
## <a name="managed-code-and-data"></a><span data-ttu-id="1b552-111">托管的代码和数据</span><span class="sxs-lookup"><span data-stu-id="1b552-111">Managed Code and Data</span></span>  
 <span data-ttu-id="1b552-112">为.NET Framework 被称为代码开发*托管代码*，并包含由 CLR 使用元数据。</span><span class="sxs-lookup"><span data-stu-id="1b552-112">Code developed for the .NET Framework is referred to as *managed code*, and contains metadata that is used by the CLR.</span></span> <span data-ttu-id="1b552-113">使用.NET Framework 应用程序的数据称为*托管数据*因为运行时管理与数据相关的任务，比如分配和回收内存以及执行类型检查。</span><span class="sxs-lookup"><span data-stu-id="1b552-113">Data used by .NET Framework applications is called *managed data* because the runtime manages data-related tasks such as allocating and reclaiming memory and performing type checking.</span></span> <span data-ttu-id="1b552-114">默认情况下，Visual Basic.NET 中使用托管的代码和数据，但您可以访问的非托管的代码和 COM 对象使用互操作程序集 （稍后介绍在此页上） 的数据。</span><span class="sxs-lookup"><span data-stu-id="1b552-114">By default, Visual Basic .NET uses managed code and data, but you can access the unmanaged code and data of COM objects using interop assemblies (described later on this page).</span></span>  
  
## <a name="assemblies"></a><span data-ttu-id="1b552-115">程序集</span><span class="sxs-lookup"><span data-stu-id="1b552-115">Assemblies</span></span>  
 <span data-ttu-id="1b552-116">程序集是.NET Framework 应用程序的主要构建基块。</span><span class="sxs-lookup"><span data-stu-id="1b552-116">An assembly is the primary building block of a .NET Framework application.</span></span> <span data-ttu-id="1b552-117">它是功能的一个已生成、 版本控制，并作为单个实现单元包含一个或多个文件已部署的集合。</span><span class="sxs-lookup"><span data-stu-id="1b552-117">It is a collection of functionality that is built, versioned, and deployed as a single implementation unit containing one or more files.</span></span> <span data-ttu-id="1b552-118">每个程序集包含程序集清单。</span><span class="sxs-lookup"><span data-stu-id="1b552-118">Each assembly contains an assembly manifest.</span></span>  
  
## <a name="type-libraries-and-assembly-manifests"></a><span data-ttu-id="1b552-119">类型库和程序集清单</span><span class="sxs-lookup"><span data-stu-id="1b552-119">Type Libraries and Assembly Manifests</span></span>  
 <span data-ttu-id="1b552-120">类型库描述 COM 对象，如成员名称和数据类型的特征。</span><span class="sxs-lookup"><span data-stu-id="1b552-120">Type libraries describe characteristics of COM objects, such as member names and data types.</span></span> <span data-ttu-id="1b552-121">程序集清单的.NET Framework 应用程序执行相同的功能。</span><span class="sxs-lookup"><span data-stu-id="1b552-121">Assembly manifests perform the same function for .NET Framework applications.</span></span> <span data-ttu-id="1b552-122">它们包括有关以下信息：</span><span class="sxs-lookup"><span data-stu-id="1b552-122">They include information about the following:</span></span>  
  
- <span data-ttu-id="1b552-123">程序集标识、 版本、 区域性和数字签名。</span><span class="sxs-lookup"><span data-stu-id="1b552-123">Assembly identity, version, culture, and digital signature.</span></span>  
  
- <span data-ttu-id="1b552-124">组成程序集实现的文件。</span><span class="sxs-lookup"><span data-stu-id="1b552-124">Files that make up the assembly implementation.</span></span>  
  
- <span data-ttu-id="1b552-125">类型和构成该程序集的资源。</span><span class="sxs-lookup"><span data-stu-id="1b552-125">Types and resources that make up the assembly.</span></span> <span data-ttu-id="1b552-126">这包括那些从其导出。</span><span class="sxs-lookup"><span data-stu-id="1b552-126">This includes those that are exported from it.</span></span>  
  
- <span data-ttu-id="1b552-127">对其他程序集的编译时依赖项。</span><span class="sxs-lookup"><span data-stu-id="1b552-127">Compile-time dependencies on other assemblies.</span></span>  
  
- <span data-ttu-id="1b552-128">要正确运行的程序集所需的权限。</span><span class="sxs-lookup"><span data-stu-id="1b552-128">Permissions required for the assembly to run correctly.</span></span>  
  
 <span data-ttu-id="1b552-129">有关程序集和程序集清单的详细信息，请参阅[.NET 中的程序集](../../../standard/assembly/index.md)。</span><span class="sxs-lookup"><span data-stu-id="1b552-129">For more information about assemblies and assembly manifests, see [Assemblies in .NET](../../../standard/assembly/index.md).</span></span>  
  
### <a name="importing-and-exporting-type-libraries"></a><span data-ttu-id="1b552-130">导入和导出类型库</span><span class="sxs-lookup"><span data-stu-id="1b552-130">Importing and Exporting Type Libraries</span></span>  
 <span data-ttu-id="1b552-131">Visual Studio 包含一个实用程序，Tlbimp，它允许您将信息从类型库导入到.NET Framework 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1b552-131">Visual Studio contains a utility, Tlbimp, that lets you import information from a type library into a .NET Framework application.</span></span> <span data-ttu-id="1b552-132">通过使用 Tlbexp 实用工具，可以从程序集生成类型库。</span><span class="sxs-lookup"><span data-stu-id="1b552-132">You can generate type libraries from assemblies by using the Tlbexp utility.</span></span>  
  
 <span data-ttu-id="1b552-133">Tlbimp 和 Tlbexp 有关的信息，请参阅[Tlbimp.exe （类型库导入程序）](../../../framework/tools/tlbimp-exe-type-library-importer.md)并[Tlbexp.exe （类型库导出程序）](../../../framework/tools/tlbexp-exe-type-library-exporter.md)。</span><span class="sxs-lookup"><span data-stu-id="1b552-133">For information about Tlbimp and Tlbexp, see [Tlbimp.exe (Type Library Importer)](../../../framework/tools/tlbimp-exe-type-library-importer.md) and [Tlbexp.exe (Type Library Exporter)](../../../framework/tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
## <a name="interop-assemblies"></a><span data-ttu-id="1b552-134">互操作程序集</span><span class="sxs-lookup"><span data-stu-id="1b552-134">Interop Assemblies</span></span>  
 <span data-ttu-id="1b552-135">互操作程序集是.NET Framework 程序集之间的桥托管和非托管的代码中，COM 对象成员映射到等效的.NET Framework 托管成员。</span><span class="sxs-lookup"><span data-stu-id="1b552-135">Interop assemblies are .NET Framework assemblies that bridge between managed and unmanaged code, mapping COM object members to equivalent .NET Framework managed members.</span></span> <span data-ttu-id="1b552-136">创建 Visual Basic.NET 的互操作程序集处理的许多使用 COM 对象，如互操作封送处理的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1b552-136">Interop assemblies created by Visual Basic .NET handle many of the details of working with COM objects, such as interoperability marshaling.</span></span>  
  
## <a name="interoperability-marshaling"></a><span data-ttu-id="1b552-137">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="1b552-137">Interoperability Marshaling</span></span>  
 <span data-ttu-id="1b552-138">所有.NET Framework 应用程序都共享一组实现的对象，无论使用的编程语言的互操作性的常见类型。</span><span class="sxs-lookup"><span data-stu-id="1b552-138">All .NET Framework applications share a set of common types that enable interoperability of objects, regardless of the programming language that is used.</span></span> <span data-ttu-id="1b552-139">参数和返回值的 COM 对象有时使用不同于托管代码中使用的数据类型。</span><span class="sxs-lookup"><span data-stu-id="1b552-139">The parameters and return values of COM objects sometimes use data types that differ from those used in managed code.</span></span> <span data-ttu-id="1b552-140">*互操作封送处理*随着对象移动到和从 COM 对象是打包参数和返回值为等效的数据类型的过程。</span><span class="sxs-lookup"><span data-stu-id="1b552-140">*Interoperability marshaling* is the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="1b552-141">有关详细信息，请参阅[互操作封送处理](../../../framework/interop/interop-marshaling.md)。</span><span class="sxs-lookup"><span data-stu-id="1b552-141">For more information, see [Interop Marshaling](../../../framework/interop/interop-marshaling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b552-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b552-142">See also</span></span>

- [<span data-ttu-id="1b552-143">COM 互操作</span><span class="sxs-lookup"><span data-stu-id="1b552-143">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
- [<span data-ttu-id="1b552-144">演练：使用 COM 对象实现继承</span><span class="sxs-lookup"><span data-stu-id="1b552-144">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [<span data-ttu-id="1b552-145">与非托管代码交互操作</span><span class="sxs-lookup"><span data-stu-id="1b552-145">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)
- [<span data-ttu-id="1b552-146">互操作性疑难解答</span><span class="sxs-lookup"><span data-stu-id="1b552-146">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
- [<span data-ttu-id="1b552-147">.NET 中的程序集</span><span class="sxs-lookup"><span data-stu-id="1b552-147">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="1b552-148">Tlbimp.exe（类型库导入程序）</span><span class="sxs-lookup"><span data-stu-id="1b552-148">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [<span data-ttu-id="1b552-149">Tlbexp.exe（类型库导出程序）</span><span class="sxs-lookup"><span data-stu-id="1b552-149">Tlbexp.exe (Type Library Exporter)</span></span>](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [<span data-ttu-id="1b552-150">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="1b552-150">Interop Marshaling</span></span>](../../../framework/interop/interop-marshaling.md)
- [<span data-ttu-id="1b552-151">免注册 COM 互操作</span><span class="sxs-lookup"><span data-stu-id="1b552-151">Registration-Free COM Interop</span></span>](../../../framework/interop/registration-free-com-interop.md)
