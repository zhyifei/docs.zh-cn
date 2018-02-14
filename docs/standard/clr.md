---
title: "公共语言运行时 (CLR)"
ms.custom: updateeachrelease
ms.date: 10/17/2017
ms.prod: .net
ms.technology: dotnet-standard
ms.topic: article
helpviewer_keywords:
- compiling source code, runtime functionality
- code, execution
- managed data
- runtime
- common language runtime
- metadata, runtime functionality
- .NET Framework, common language runtime
- language compilers
- managed code
- source code execution
- code, runtime functionality
ms.assetid: 059a624e-f7db-4134-ba9f-08b676050482
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4aa9a6d37a52d5f15643e9179060450a2d7a34c4
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="common-language-runtime-clr"></a><span data-ttu-id="945f1-102">公共语言运行时 (CLR)</span><span class="sxs-lookup"><span data-stu-id="945f1-102">Common Language Runtime (CLR)</span></span>
<span data-ttu-id="945f1-103">.NET Framework 提供了一个称为公共语言运行时的运行时环境，它运行代码并提供使开发过程更轻松的服务。</span><span class="sxs-lookup"><span data-stu-id="945f1-103">The .NET Framework provides a run-time environment called the common language runtime, which runs the code and provides services that make the development process easier.</span></span>  
  
 <span data-ttu-id="945f1-104">公共语言运行时的功能通过编译器和工具公开，你可以编写利用此托管执行环境的代码。</span><span class="sxs-lookup"><span data-stu-id="945f1-104">Compilers and tools expose the common language runtime's functionality and enable you to write code that benefits from this managed execution environment.</span></span> <span data-ttu-id="945f1-105">使用基于公共语言运行时的语言编译器开发的代码称为托管代码；托管代码具有许多优点，例如：跨语言集成、跨语言异常处理、增强的安全性、版本控制和部署支持、简化的组件交互模型、调试和分析服务等。</span><span class="sxs-lookup"><span data-stu-id="945f1-105">Code that you develop with a language compiler that targets the runtime is called managed code; it benefits from features such as cross-language integration, cross-language exception handling, enhanced security, versioning and deployment support, a simplified model for component interaction, and debugging and profiling services.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="945f1-106">编译器和工具可以产生公共语言运行时可以使用的输出，因为类型系统、元数据格式和该运行时环境（虚拟执行系统）都由公共标准（ECMA 公共语言基础结构规范）定义。</span><span class="sxs-lookup"><span data-stu-id="945f1-106">Compilers and tools are able to produce output that the common language runtime can consume because the type system, the format of metadata, and the runtime environment (the virtual execution system) are all defined by a public standard, the ECMA Common Language Infrastructure specification.</span></span> <span data-ttu-id="945f1-107">有关详细信息，请参阅 [ECMA C# 和公共语言基础结构规范](https://www.visualstudio.com/license-terms/ecma-c-common-language-infrastructure-standards/)。</span><span class="sxs-lookup"><span data-stu-id="945f1-107">For more information, see [ECMA C# and Common Language Infrastructure Specifications](https://www.visualstudio.com/license-terms/ecma-c-common-language-infrastructure-standards/).</span></span>  
  
 <span data-ttu-id="945f1-108">若要使公共语言运行时能够向托管代码提供服务，语言编译器必须生成一些元数据来描述代码中的类型、成员和引用。</span><span class="sxs-lookup"><span data-stu-id="945f1-108">To enable the runtime to provide services to managed code, language compilers must emit metadata that describes the types, members, and references in your code.</span></span> <span data-ttu-id="945f1-109">元数据与代码一起存储；每个可加载的公共语言运行时可迁移执行 (PE) 文件都包含元数据。</span><span class="sxs-lookup"><span data-stu-id="945f1-109">Metadata is stored with the code; every loadable common language runtime portable executable (PE) file contains metadata.</span></span> <span data-ttu-id="945f1-110">公共语言运行时使用元数据来完成以下任务：查找和加载类，在内存中安排实例，解析方法调用，生成本机代码，强制安全性，以及设置运行时上下文边界。</span><span class="sxs-lookup"><span data-stu-id="945f1-110">The runtime uses metadata to locate and load classes, lay out instances in memory, resolve method invocations, generate native code, enforce security, and set run-time context boundaries.</span></span>  
  
 <span data-ttu-id="945f1-111">公共语言运行时自动处理对象布局并管理对象引用，当不再使用对象时释放它们。</span><span class="sxs-lookup"><span data-stu-id="945f1-111">The runtime automatically handles object layout and manages references to objects, releasing them when they are no longer being used.</span></span> <span data-ttu-id="945f1-112">按这种方式实现生存期管理的对象称为托管数据。</span><span class="sxs-lookup"><span data-stu-id="945f1-112">Objects whose lifetimes are managed in this way are called managed data.</span></span> <span data-ttu-id="945f1-113">垃圾回收消除了内存泄漏以及其他一些常见的编程错误。</span><span class="sxs-lookup"><span data-stu-id="945f1-113">Garbage collection eliminates memory leaks as well as some other common programming errors.</span></span> <span data-ttu-id="945f1-114">如果你编写的代码是托管代码，则可以在 .NET Framework 应用程序中使用托管数据、非托管数据或者同时使用这两种数据。</span><span class="sxs-lookup"><span data-stu-id="945f1-114">If your code is managed, you can use managed data, unmanaged data, or both managed and unmanaged data in your .NET Framework application.</span></span> <span data-ttu-id="945f1-115">由于语言编译器会提供自己的类型（如基元类型），因此你可能并不总是知道（或需要知道）这些数据是否是托管的。</span><span class="sxs-lookup"><span data-stu-id="945f1-115">Because language compilers supply their own types, such as primitive types, you might not always know (or need to know) whether your data is being managed.</span></span>  
  
 <span data-ttu-id="945f1-116">有了公共语言运行时，就可以很容易地设计出对象能够跨语言交互的组件和应用程序。</span><span class="sxs-lookup"><span data-stu-id="945f1-116">The common language runtime makes it easy to design components and applications whose objects interact across languages.</span></span> <span data-ttu-id="945f1-117">也就是说，用不同语言编写的对象可以互相通信，并且它们的行为可以紧密集成。</span><span class="sxs-lookup"><span data-stu-id="945f1-117">Objects written in different languages can communicate with each other, and their behaviors can be tightly integrated.</span></span> <span data-ttu-id="945f1-118">例如，可以定义一个类，然后使用不同的语言从原始类派生出另一个类或调用原始类的方法。</span><span class="sxs-lookup"><span data-stu-id="945f1-118">For example, you can define a class and then use a different language to derive a class from your original class or call a method on the original class.</span></span> <span data-ttu-id="945f1-119">还可以将一个类的实例传递到用不同的语言编写的另一个类的方法。</span><span class="sxs-lookup"><span data-stu-id="945f1-119">You can also pass an instance of a class to a method of a class written in a different language.</span></span> <span data-ttu-id="945f1-120">这种跨语言集成之所以成为可能，是因为基于公共语言运行时的语言编译器和工具使用由公共语言运行时定义的常规类型系统，而且它们遵循公共语言运行时关于定义新类型以及创建、使用、保持和绑定到类型的规则。</span><span class="sxs-lookup"><span data-stu-id="945f1-120">This cross-language integration is possible because language compilers and tools that target the runtime use a common type system defined by the runtime, and they follow the runtime's rules for defining new types, as well as for creating, using, persisting, and binding to types.</span></span>  
  
 <span data-ttu-id="945f1-121">所有托管组件都带有生成它们所基于的组件和资源的信息，这些信息构成了元数据的一部分。</span><span class="sxs-lookup"><span data-stu-id="945f1-121">As part of their metadata, all managed components carry information about the components and resources they were built against.</span></span> <span data-ttu-id="945f1-122">公共语言运行时使用这些信息确保组件或应用程序具有它需要的所有内容的指定版本，这样就使代码不太可能由于某些未满足的依赖项而发生中断。</span><span class="sxs-lookup"><span data-stu-id="945f1-122">The runtime uses this information to ensure that your component or application has the specified versions of everything it needs, which makes your code less likely to break because of some unmet dependency.</span></span> <span data-ttu-id="945f1-123">注册信息和状态数据不再保存在注册表中（因为在注册表中建立和维护这些信息很困难）。</span><span class="sxs-lookup"><span data-stu-id="945f1-123">Registration information and state data are no longer stored in the registry where they can be difficult to establish and maintain.</span></span> <span data-ttu-id="945f1-124">取而代之的是，有关你定义的类型（及其依赖项）的信息作为元数据与代码存储在一起，这样大大降低了组件复制和移除任务的复杂性。</span><span class="sxs-lookup"><span data-stu-id="945f1-124">Instead, information about the types you define (and their dependencies) is stored with the code as metadata, making the tasks of component replication and removal much less complicated.</span></span>  
  
 <span data-ttu-id="945f1-125">语言编译器和工具公开公共语言运行时的功能的方式对于开发人员来说不仅很有用，而且很直观。</span><span class="sxs-lookup"><span data-stu-id="945f1-125">Language compilers and tools expose the runtime's functionality in ways that are intended to be useful and intuitive to developers.</span></span> <span data-ttu-id="945f1-126">这意味着，公共语言运行时的某些功能可能在一个环境中比在另一个环境中更突出。</span><span class="sxs-lookup"><span data-stu-id="945f1-126">This means that some features of the runtime might be more noticeable in one environment than in another.</span></span> <span data-ttu-id="945f1-127">你对公共语言运行时的体验取决于所使用的语言编译器或工具。</span><span class="sxs-lookup"><span data-stu-id="945f1-127">How you experience the runtime depends on which language compilers or tools you use.</span></span> <span data-ttu-id="945f1-128">例如，如果你是一位 Visual Basic 开发人员，你可能会注意到：有了公共语言运行时，Visual Basic 语言的面向对象的功能比以前多了。</span><span class="sxs-lookup"><span data-stu-id="945f1-128">For example, if you are a Visual Basic developer, you might notice that with the common language runtime, the Visual Basic language has more object-oriented features than before.</span></span> <span data-ttu-id="945f1-129">运行时提供如下优点：</span><span class="sxs-lookup"><span data-stu-id="945f1-129">The runtime provides the following benefits:</span></span>  
  
-   <span data-ttu-id="945f1-130">性能得到了改进。</span><span class="sxs-lookup"><span data-stu-id="945f1-130">Performance improvements.</span></span>  
  
-   <span data-ttu-id="945f1-131">能够轻松使用用其他语言开发的组件。</span><span class="sxs-lookup"><span data-stu-id="945f1-131">The ability to easily use components developed in other languages.</span></span>  
  
-   <span data-ttu-id="945f1-132">类库提供的可扩展类型。</span><span class="sxs-lookup"><span data-stu-id="945f1-132">Extensible types provided by a class library.</span></span>  
  
-   <span data-ttu-id="945f1-133">语言功能，如面向对象的编程的继承、接口和重载。</span><span class="sxs-lookup"><span data-stu-id="945f1-133">Language features such as inheritance, interfaces, and overloading for object-oriented programming.</span></span>  
  
-   <span data-ttu-id="945f1-134">允许创建多线程的可缩放应用程序的显式自由线程处理支持。</span><span class="sxs-lookup"><span data-stu-id="945f1-134">Support for explicit free threading that allows creation of multithreaded, scalable applications.</span></span>  
  
-   <span data-ttu-id="945f1-135">结构化异常处理支持。</span><span class="sxs-lookup"><span data-stu-id="945f1-135">Support for structured exception handling.</span></span>  
  
-   <span data-ttu-id="945f1-136">自定义特性支持。</span><span class="sxs-lookup"><span data-stu-id="945f1-136">Support for custom attributes.</span></span>  
  
-   <span data-ttu-id="945f1-137">垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="945f1-137">Garbage collection.</span></span>  
  
-   <span data-ttu-id="945f1-138">使用委托取代函数指针，从而增强了类型安全和安全性。</span><span class="sxs-lookup"><span data-stu-id="945f1-138">Use of delegates instead of function pointers for increased type safety and security.</span></span> <span data-ttu-id="945f1-139">有关委派的详细信息，请参阅[通用类型系统](../../docs/standard/base-types/common-type-system.md)。</span><span class="sxs-lookup"><span data-stu-id="945f1-139">For more information about delegates, see [Common Type System](../../docs/standard/base-types/common-type-system.md).</span></span>  
  
## <a name="versions-of-the-common-language-runtime"></a><span data-ttu-id="945f1-140">公共语言运行时的版本</span><span class="sxs-lookup"><span data-stu-id="945f1-140">Versions of the Common Language Runtime</span></span>  
 <span data-ttu-id="945f1-141">.NET Framework 的版本号无需对应于它所包含的 CLR 的版本号。</span><span class="sxs-lookup"><span data-stu-id="945f1-141">The version number of the .NET Framework doesn't necessarily correspond to the version number of the CLR it includes.</span></span> <span data-ttu-id="945f1-142">下表演示了两个版本号关联的方式。</span><span class="sxs-lookup"><span data-stu-id="945f1-142">The following table shows how the two version numbers correlate.</span></span>  
  
|<span data-ttu-id="945f1-143">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="945f1-143">.NET Framework version</span></span>|<span data-ttu-id="945f1-144">包括 CLR 版本</span><span class="sxs-lookup"><span data-stu-id="945f1-144">Includes CLR version</span></span>|  
|----------------------------|--------------------------|  
|<span data-ttu-id="945f1-145">1.0</span><span class="sxs-lookup"><span data-stu-id="945f1-145">1.0</span></span>|<span data-ttu-id="945f1-146">1.0</span><span class="sxs-lookup"><span data-stu-id="945f1-146">1.0</span></span>|  
|<span data-ttu-id="945f1-147">1.1</span><span class="sxs-lookup"><span data-stu-id="945f1-147">1.1</span></span>|<span data-ttu-id="945f1-148">1.1</span><span class="sxs-lookup"><span data-stu-id="945f1-148">1.1</span></span>|  
|<span data-ttu-id="945f1-149">2.0</span><span class="sxs-lookup"><span data-stu-id="945f1-149">2.0</span></span>|<span data-ttu-id="945f1-150">2.0</span><span class="sxs-lookup"><span data-stu-id="945f1-150">2.0</span></span>|  
|<span data-ttu-id="945f1-151">3.0</span><span class="sxs-lookup"><span data-stu-id="945f1-151">3.0</span></span>|<span data-ttu-id="945f1-152">2.0</span><span class="sxs-lookup"><span data-stu-id="945f1-152">2.0</span></span>|  
|<span data-ttu-id="945f1-153">3.5</span><span class="sxs-lookup"><span data-stu-id="945f1-153">3.5</span></span>|<span data-ttu-id="945f1-154">2.0</span><span class="sxs-lookup"><span data-stu-id="945f1-154">2.0</span></span>|  
|<span data-ttu-id="945f1-155">4</span><span class="sxs-lookup"><span data-stu-id="945f1-155">4</span></span>|<span data-ttu-id="945f1-156">4</span><span class="sxs-lookup"><span data-stu-id="945f1-156">4</span></span>|  
|<span data-ttu-id="945f1-157">4.5（包括 4.5.1 和 4.5.2）</span><span class="sxs-lookup"><span data-stu-id="945f1-157">4.5 (including 4.5.1 and 4.5.2)</span></span>|<span data-ttu-id="945f1-158">4</span><span class="sxs-lookup"><span data-stu-id="945f1-158">4</span></span>|  
|<span data-ttu-id="945f1-159">4.6（包括 4.6.1 和 4.6.2）</span><span class="sxs-lookup"><span data-stu-id="945f1-159">4.6 (including 4.6.1 and 4.6.2)</span></span>|<span data-ttu-id="945f1-160">4</span><span class="sxs-lookup"><span data-stu-id="945f1-160">4</span></span>|
|<span data-ttu-id="945f1-161">4.7（包括 4.7.1）</span><span class="sxs-lookup"><span data-stu-id="945f1-161">4.7 (including 4.7.1)</span></span>|<span data-ttu-id="945f1-162">4</span><span class="sxs-lookup"><span data-stu-id="945f1-162">4</span></span>|  
  
## <a name="related-topics"></a><span data-ttu-id="945f1-163">相关主题</span><span class="sxs-lookup"><span data-stu-id="945f1-163">Related Topics</span></span>  
  
|<span data-ttu-id="945f1-164">标题</span><span class="sxs-lookup"><span data-stu-id="945f1-164">Title</span></span>|<span data-ttu-id="945f1-165">描述</span><span class="sxs-lookup"><span data-stu-id="945f1-165">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="945f1-166">托管执行过程</span><span class="sxs-lookup"><span data-stu-id="945f1-166">Managed Execution Process</span></span>](../../docs/standard/managed-execution-process.md)|<span data-ttu-id="945f1-167">描述使用公共语言运行时所需要的步骤。</span><span class="sxs-lookup"><span data-stu-id="945f1-167">Describes the steps required to take advantage of the common language runtime.</span></span>|  
|[<span data-ttu-id="945f1-168">自动内存管理</span><span class="sxs-lookup"><span data-stu-id="945f1-168">Automatic Memory Management</span></span>](../../docs/standard/automatic-memory-management.md)|<span data-ttu-id="945f1-169">描述垃圾回收器如何分配和释放内存。</span><span class="sxs-lookup"><span data-stu-id="945f1-169">Describes how the garbage collector allocates and releases memory.</span></span>|  
|[<span data-ttu-id="945f1-170">NIB：.NET Framework 概述</span><span class="sxs-lookup"><span data-stu-id="945f1-170">NIB: Overview of the .NET Framework</span></span>](http://msdn.microsoft.com/library/ea38ac1e-92af-4d1b-8db1-e8a5ea10ed85)|<span data-ttu-id="945f1-171">描述关键的 .NET Framework 概念，例如通用类型系统、跨语言互操作性、托管执行、应用程序域和程序集。</span><span class="sxs-lookup"><span data-stu-id="945f1-171">Describes key .NET Framework concepts such as the common type system, cross-language interoperability, managed execution, application domains, and assemblies.</span></span>|  
|[<span data-ttu-id="945f1-172">常规类型系统</span><span class="sxs-lookup"><span data-stu-id="945f1-172">Common Type System</span></span>](../../docs/standard/base-types/common-type-system.md)|<span data-ttu-id="945f1-173">描述在运行时中如何声明、使用和管理类型以支持跨语言集成。</span><span class="sxs-lookup"><span data-stu-id="945f1-173">Describes how types are declared, used, and managed in the runtime in support of cross-language integration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="945f1-174">请参阅</span><span class="sxs-lookup"><span data-stu-id="945f1-174">See Also</span></span>  
 [<span data-ttu-id="945f1-175">版本和依赖关系</span><span class="sxs-lookup"><span data-stu-id="945f1-175">Versions and Dependencies</span></span>](../../docs/framework/migration-guide/versions-and-dependencies.md)
