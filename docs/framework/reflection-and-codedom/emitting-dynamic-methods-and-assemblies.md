---
title: "发出动态方法和程序集"
ms.custom: 
ms.date: 08/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 91b0cc4614834f2ad8f7b54d9364d484ca9a6990
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="emitting-dynamic-methods-and-assemblies"></a><span data-ttu-id="b38ea-102">发出动态方法和程序集</span><span class="sxs-lookup"><span data-stu-id="b38ea-102">Emitting Dynamic Methods and Assemblies</span></span>
<span data-ttu-id="b38ea-103">本节介绍 <xref:System.Reflection.Emit> 命名空间中的一组托管类型，它们允许编译器或工具在运行时发出元数据和 Microsoft 中间语言 (MSIL)，并在磁盘上生成可移植可执行 (PE) 文件（可选）。</span><span class="sxs-lookup"><span data-stu-id="b38ea-103">This section describes a set of managed types in the <xref:System.Reflection.Emit> namespace that allow a compiler or tool to emit metadata and Microsoft intermediate language (MSIL) at run time and optionally generate a portable executable (PE) file on disk.</span></span> <span data-ttu-id="b38ea-104">脚本引擎和编译器是此命名空间的主要使用者。</span><span class="sxs-lookup"><span data-stu-id="b38ea-104">Script engines and compilers are the primary users of this namespace.</span></span> <span data-ttu-id="b38ea-105">在本节中，<xref:System.Reflection.Emit> 命名空间提供的功能被称为反射发出。</span><span class="sxs-lookup"><span data-stu-id="b38ea-105">In this section, the functionality provided by the <xref:System.Reflection.Emit> namespace is referred to as reflection emit.</span></span>  
  
 <span data-ttu-id="b38ea-106">反射发出具有以下功能：</span><span class="sxs-lookup"><span data-stu-id="b38ea-106">Reflection emit provides the following capabilities:</span></span>  
  
-   <span data-ttu-id="b38ea-107">在运行时定义轻量全局方法（使用 <xref:System.Reflection.Emit.DynamicMethod> 类）并通过委托执行这些方法。</span><span class="sxs-lookup"><span data-stu-id="b38ea-107">Define lightweight global methods at run time, using the <xref:System.Reflection.Emit.DynamicMethod> class, and execute them using delegates.</span></span>  
  
-   <span data-ttu-id="b38ea-108">在运行时定义程序集，然后运行程序集以及/或者将程序集保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="b38ea-108">Define assemblies at run time and then run them and/or save them to disk.</span></span>  
  
-   <span data-ttu-id="b38ea-109">在运行时定义程序集，运行程序集，然后卸载程序集并允许垃圾回收回收其资源。</span><span class="sxs-lookup"><span data-stu-id="b38ea-109">Define assemblies at run time, run them, and then unload them and allow garbage collection to reclaim their resources.</span></span>  
  
-   <span data-ttu-id="b38ea-110">在运行时在新的程序集中定义模块，然后运行模块以及/或者将模块保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="b38ea-110">Define modules in new assemblies at run time and then run and/or save them to disk.</span></span>  
  
-   <span data-ttu-id="b38ea-111">在运行时在模块中定义类型，创建这些类型的实例并调用其方法。</span><span class="sxs-lookup"><span data-stu-id="b38ea-111">Define types in modules at run time, create instances of these types, and invoke their methods.</span></span>  
  
-   <span data-ttu-id="b38ea-112">为已定义模块定义可供工具（如调试器和代码探查器）使用的符号化信息。</span><span class="sxs-lookup"><span data-stu-id="b38ea-112">Define symbolic information for defined modules that can be used by tools such as debuggers and code profilers.</span></span>  
  
 <span data-ttu-id="b38ea-113">除了 <xref:System.Reflection.Emit> 命名空间中的托管类型，还有非托管元数据接口，非托管元数据接口在[元数据接口](../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)参考文档中介绍。</span><span class="sxs-lookup"><span data-stu-id="b38ea-113">In addition to the managed types in the <xref:System.Reflection.Emit> namespace, there are unmanaged metadata interfaces which are described in the [Metadata Interfaces](../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) reference documentation.</span></span> <span data-ttu-id="b38ea-114">托管的反射发出提供比非托管元数据接口更强的语义错误检查和更高级别的元数据抽象。</span><span class="sxs-lookup"><span data-stu-id="b38ea-114">Managed reflection emit provides stronger semantic error checking and a higher level of abstraction of the metadata than the unmanaged metadata interfaces.</span></span>  
  
 <span data-ttu-id="b38ea-115">元数据和 MSIL 的另一个有用资源是《公共语言基础结构 (CLI)》文档，尤其是“第二部分：元数据定义和语义”和“第三部分: CIL 指令集”。</span><span class="sxs-lookup"><span data-stu-id="b38ea-115">Another useful resource for working with metadata and MSIL is the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set".</span></span> <span data-ttu-id="b38ea-116">该文档可在 [MSDN](http://go.microsoft.com/fwlink/?LinkID=65555) 和 [Ecma 网站](http://go.microsoft.com/fwlink/?LinkId=116487)上联机获取。</span><span class="sxs-lookup"><span data-stu-id="b38ea-116">The documentation is available online on [MSDN](http://go.microsoft.com/fwlink/?LinkID=65555) and at the [Ecma Web site](http://go.microsoft.com/fwlink/?LinkId=116487).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b38ea-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="b38ea-117">In This Section</span></span>
  
[<span data-ttu-id="b38ea-118">反射发出中的安全问题</span><span class="sxs-lookup"><span data-stu-id="b38ea-118">Security issues in reflection emit</span></span>](../../../docs/framework/reflection-and-codedom/security-issues-in-reflection-emit.md)  
<span data-ttu-id="b38ea-119">介绍与使用反射发出创建动态程序集相关的安全问题。</span><span class="sxs-lookup"><span data-stu-id="b38ea-119">Describes security issues related to creating dynamic assemblies using reflection emit.</span></span>  

<span data-ttu-id="b38ea-120">[如何： 定义和执行动态方法](how-to-define-and-execute-dynamic-methods.md) </span><span class="sxs-lookup"><span data-stu-id="b38ea-120">[How to: Define and execute dynamic methods](how-to-define-and-execute-dynamic-methods.md) </span></span>  
<span data-ttu-id="b38ea-121">演示如何执行简单的动态方法和动态方法绑定到类的实例。</span><span class="sxs-lookup"><span data-stu-id="b38ea-121">Shows how to execute a simple dynamic method and a dynamic method bound to an instance of a class.</span></span>

<span data-ttu-id="b38ea-122">[如何： 定义泛型类型使用反射发出](how-to-define-a-generic-type-with-reflection-emit.md) </span><span class="sxs-lookup"><span data-stu-id="b38ea-122">[How to: Define a generic type with reflection emit](how-to-define-a-generic-type-with-reflection-emit.md) </span></span>  
<span data-ttu-id="b38ea-123">演示如何创建简单的泛型类型具有两个类型参数、 如何将类、 接口和特殊约束应用于类型参数，以及如何创建 memers 的类的类型参数用作参数类型和返回类型。</span><span class="sxs-lookup"><span data-stu-id="b38ea-123">Shows how to create a simple generic type with two type parameters, how to apply class, interface, and special constraints to the type parameters, and how to create memers that use the type parameters of the class as parameter types and return types.</span></span>

<span data-ttu-id="b38ea-124">[如何： 定义一个泛型方法，使用反射发出](how-to-define-a-generic-method-with-reflection-emit.md) </span><span class="sxs-lookup"><span data-stu-id="b38ea-124">[How to: Define a generic method with reflection emit](how-to-define-a-generic-method-with-reflection-emit.md) </span></span>  
<span data-ttu-id="b38ea-125">演示如何创建、 发出，并调用简单的泛型方法。</span><span class="sxs-lookup"><span data-stu-id="b38ea-125">Shows how to create, emit, and invoke a simple generic method.</span></span>

<span data-ttu-id="b38ea-126">[动态类型生成可回收程序集](collectible-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="b38ea-126">[Collectible assemblies for dynamic type generation](collectible-assemblies.md) </span></span>  
<span data-ttu-id="b38ea-127">引入了可回收程序集，它们是可以无需卸载在其中创建它们的应用程序域中卸载的动态程序集。</span><span class="sxs-lookup"><span data-stu-id="b38ea-127">Introduces collectible assemblies, which are dynamic assemblies that can be unloaded without unloading the application domain in which they were created.</span></span>
  
## <a name="reference"></a><span data-ttu-id="b38ea-128">参考</span><span class="sxs-lookup"><span data-stu-id="b38ea-128">Reference</span></span>  
 <xref:System.Reflection.Emit.OpCodes>  
 <span data-ttu-id="b38ea-129">编录可用于生成方法体的 MSIL 指令代码。</span><span class="sxs-lookup"><span data-stu-id="b38ea-129">Catalogs the MSIL instruction codes you can use to build method bodies.</span></span>  
  
 <xref:System.Reflection.Emit>  
 <span data-ttu-id="b38ea-130">包含用于发出动态方法、程序集和类型的托管类。</span><span class="sxs-lookup"><span data-stu-id="b38ea-130">Contains managed classes used to emit dynamic methods, assemblies, and types.</span></span>  
  
 <xref:System.Type>  
 <span data-ttu-id="b38ea-131">介绍 <xref:System.Type> 类，该类代表托管反射和反射发出中的类型，它是使用这些技术的关键。</span><span class="sxs-lookup"><span data-stu-id="b38ea-131">Describes the <xref:System.Type> class, which represents types in managed reflection and reflection emit, and which is key to the use of these technologies.</span></span>  
  
 <xref:System.Reflection>  
 <span data-ttu-id="b38ea-132">包含用于浏览元数据和托管代码的托管类。</span><span class="sxs-lookup"><span data-stu-id="b38ea-132">Contains managed classes used to explore metadata and managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b38ea-133">相关章节</span><span class="sxs-lookup"><span data-stu-id="b38ea-133">Related Sections</span></span>  
 [<span data-ttu-id="b38ea-134">反射</span><span class="sxs-lookup"><span data-stu-id="b38ea-134">Reflection</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="b38ea-135">说明如何浏览元数据和托管代码。</span><span class="sxs-lookup"><span data-stu-id="b38ea-135">Explains how to explore metadata and managed code.</span></span>  
  
 <span data-ttu-id="b38ea-136">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)（公共语言运行时中的程序集）</span><span class="sxs-lookup"><span data-stu-id="b38ea-136">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)</span></span>  
 <span data-ttu-id="b38ea-137">概述.NET 实现中的程序集。</span><span class="sxs-lookup"><span data-stu-id="b38ea-137">Provides an overview of assemblies in .NET implementations.</span></span>
