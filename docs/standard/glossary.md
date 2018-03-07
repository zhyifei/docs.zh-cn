---
title: ".NET 术语表"
description: "了解 .NET 文档中所用的选定术语的含义。"
keywords: ".NET 术语表, .NET 字典, .NET 术语, .NET 平台, .NET framework, .NET 运行时"
author: tdykstra
ms.author: tdykstra
ms.date: 07/08/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 33123732514a53574036f6f8e948b2cf9acb9229
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="net-glossary"></a><span data-ttu-id="89c06-104">.NET 术语表</span><span class="sxs-lookup"><span data-stu-id="89c06-104">.NET Glossary</span></span>

<span data-ttu-id="89c06-105">此术语表的主要目的是阐明所选术语和缩写词的含义，这些词频繁出现在 .NET 文档中但没有定义。</span><span class="sxs-lookup"><span data-stu-id="89c06-105">The primary goal of this glossary is to clarify meanings of selected terms and acronyms that appear frequently in the .NET documentation without definitions.</span></span>

## <a name="aot"></a><span data-ttu-id="89c06-106">AOT</span><span class="sxs-lookup"><span data-stu-id="89c06-106">AOT</span></span>

<span data-ttu-id="89c06-107">预编译器。</span><span class="sxs-lookup"><span data-stu-id="89c06-107">Ahead-of-time compiler.</span></span>

<span data-ttu-id="89c06-108">与 [JIT](#jit) 类似，此编译器还可将 [IL](#il) 转换为机器代码。</span><span class="sxs-lookup"><span data-stu-id="89c06-108">Similar to [JIT](#jit), this compiler also translates [IL](#il) to machine code.</span></span> <span data-ttu-id="89c06-109">与 JIT 编译相比，AOT 编译在应用程序执行前进行并且通常在不同计算机上执行。</span><span class="sxs-lookup"><span data-stu-id="89c06-109">In contrast to JIT compilation, AOT compilation happens before the application is executed and is usually performed on a different machine.</span></span> <span data-ttu-id="89c06-110">由于在运行时 AOT 工具链不编译，因此它们不需要最大程度地减少编译所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="89c06-110">Because AOT tool chains don't compile at runtime, they don't have to minimize time spent compiling.</span></span> <span data-ttu-id="89c06-111">这意味着它们可花更多的时间进行优化。</span><span class="sxs-lookup"><span data-stu-id="89c06-111">That means they can spend more time optimizing.</span></span> <span data-ttu-id="89c06-112">由于 AOT 的上下文是整个应用程序，因此 AOT 编译器还会执行跨模块链接和全程序分析，这意味着之后会进行所有引用并会生成单个可执行文件。</span><span class="sxs-lookup"><span data-stu-id="89c06-112">Since the context of AOT is the entire application, the AOT compiler also performs cross-module linking and whole-program analysis, which means that all references are followed and a single executable is produced.</span></span>

## <a name="aspnet"></a><span data-ttu-id="89c06-113">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="89c06-113">ASP.NET</span></span> 

<span data-ttu-id="89c06-114">随 .NET Framework 一起提供的原始 ASP.NET 实现。</span><span class="sxs-lookup"><span data-stu-id="89c06-114">The original ASP.NET implementation that ships with the .NET Framework.</span></span>

<span data-ttu-id="89c06-115">有时 ASP.NET 是一个涵盖性术语，指包含 ASP.NET Core 在内的两个 ASP.NET 实现。</span><span class="sxs-lookup"><span data-stu-id="89c06-115">Sometimes ASP.NET is an umbrella term that refers to both ASP.NET implementations including ASP.NET Core.</span></span> <span data-ttu-id="89c06-116">该术语在任何给定实例中的含义取决于上下文。</span><span class="sxs-lookup"><span data-stu-id="89c06-116">The meaning that the term carries in any given instance is determined by context.</span></span> <span data-ttu-id="89c06-117">若要指明不要使用 ASP.NET 表示这两种实现，请参考 ASP.NET 4.x。</span><span class="sxs-lookup"><span data-stu-id="89c06-117">Refer to ASP.NET 4.x when you want to make it clear that you’re not using ASP.NET to mean both implementations.</span></span> 

<span data-ttu-id="89c06-118">请参阅 [ASP.NET 文档](/aspnet/#pivot=aspnet)。</span><span class="sxs-lookup"><span data-stu-id="89c06-118">See [ASP.NET documentation](/aspnet/#pivot=aspnet).</span></span>

## <a name="aspnet-core"></a><span data-ttu-id="89c06-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="89c06-119">ASP.NET Core</span></span>

<span data-ttu-id="89c06-120">.NET Core 上生成的跨平台、高性能、 开放源 ASP.NET 实现。</span><span class="sxs-lookup"><span data-stu-id="89c06-120">A cross-platform, high-performance, open source implementation of ASP.NET built on .NET Core.</span></span>

<span data-ttu-id="89c06-121">请参阅 [ASP.NET Core 文档](/aspnet/#pivot=core)。</span><span class="sxs-lookup"><span data-stu-id="89c06-121">See [ASP.NET Core documentation](/aspnet/#pivot=core).</span></span>

## <a name="assembly"></a><span data-ttu-id="89c06-122">程序集</span><span class="sxs-lookup"><span data-stu-id="89c06-122">assembly</span></span>

<span data-ttu-id="89c06-123">.dll/.exe 文件，其中包含一组可由应用或其他程序集调用的 API。</span><span class="sxs-lookup"><span data-stu-id="89c06-123">A *.dll*/*.exe* file that can contain a collection of APIs that can be called by apps or other assemblies.</span></span>

<span data-ttu-id="89c06-124">程序集可以包括接口、类、结构、枚举和委托等类型。</span><span class="sxs-lookup"><span data-stu-id="89c06-124">An assembly may include types such as interfaces, classes, structures, enumerations, and delegates.</span></span> <span data-ttu-id="89c06-125">有时，项目的 bin 文件夹中的程序集被称为二进制文件。</span><span class="sxs-lookup"><span data-stu-id="89c06-125">Assemblies in a project's *bin* folder are sometimes referred to as *binaries*.</span></span> <span data-ttu-id="89c06-126">另请参阅[库](#library)。</span><span class="sxs-lookup"><span data-stu-id="89c06-126">See also [library](#library).</span></span>

## <a name="clr"></a><span data-ttu-id="89c06-127">CLR</span><span class="sxs-lookup"><span data-stu-id="89c06-127">CLR</span></span>

<span data-ttu-id="89c06-128">公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="89c06-128">Common Language Runtime.</span></span>

<span data-ttu-id="89c06-129">确切含义取决于上下文，但它通常指 .NET Framework 的运行时。</span><span class="sxs-lookup"><span data-stu-id="89c06-129">The exact meaning depends on the context, but this usually refers to the runtime of the .NET Framework.</span></span> <span data-ttu-id="89c06-130">CLR 处理内存分配和管理。</span><span class="sxs-lookup"><span data-stu-id="89c06-130">The CLR handles memory allocation and management.</span></span> <span data-ttu-id="89c06-131">CLR 也是一个虚拟机，不仅可执行应用，还可使用 JIT 编译器快速生成和编译代码。</span><span class="sxs-lookup"><span data-stu-id="89c06-131">The CLR is also a virtual machine that not only executes apps but also generates and compiles code on-the-fly using a JIT compiler.</span></span> <span data-ttu-id="89c06-132">当前的 Microsoft CLR 实现仅限 Windows。</span><span class="sxs-lookup"><span data-stu-id="89c06-132">The current Microsoft CLR implementation is Windows only.</span></span>

## <a name="coreclr"></a><span data-ttu-id="89c06-133">CoreCLR</span><span class="sxs-lookup"><span data-stu-id="89c06-133">CoreCLR</span></span>

<span data-ttu-id="89c06-134">.NET Core 公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="89c06-134">.NET Core Common Language Runtime.</span></span>

<span data-ttu-id="89c06-135">此 CLR 是采用与 CLR 相同的基本代码生成的。</span><span class="sxs-lookup"><span data-stu-id="89c06-135">This CLR is built from the same code base as the CLR.</span></span> <span data-ttu-id="89c06-136">最初，CoreCLR 是 Silverlight 的运行时，专为在多个平台（特别是 Windows 和 OS X）上运行而开发。CoreCLR 现属于 .NET Core 并表示 CLR 的简化版本。</span><span class="sxs-lookup"><span data-stu-id="89c06-136">Originally, CoreCLR was the runtime of Silverlight and was designed to run on multiple platforms, specifically Windows and OS X. CoreCLR is now part of .NET Core and represents a simplified version of the CLR.</span></span> <span data-ttu-id="89c06-137">它仍是跨平台运行时，现包括针对许多 Linux 分发的支持。</span><span class="sxs-lookup"><span data-stu-id="89c06-137">It's still a cross platform runtime, now including support for many Linux distributions.</span></span> <span data-ttu-id="89c06-138">CoreCLR 也是具有 JIT 和代码执行功能的虚拟机。</span><span class="sxs-lookup"><span data-stu-id="89c06-138">CoreCLR is also a virtual machine with JIT and code execution capabilities.</span></span>

## <a name="corefx"></a><span data-ttu-id="89c06-139">CoreFX</span><span class="sxs-lookup"><span data-stu-id="89c06-139">CoreFX</span></span>

<span data-ttu-id="89c06-140">.NET Core 基类库 (BCL)</span><span class="sxs-lookup"><span data-stu-id="89c06-140">.NET Core Base Class Library (BCL)</span></span>

<span data-ttu-id="89c06-141">一组构成 System.*（在一定的程度上构成 Microsoft.*）命名空间的库。</span><span class="sxs-lookup"><span data-stu-id="89c06-141">A set of libraries that comprise the System.* (and to a limited extent  Microsoft.*) namespaces.</span></span> <span data-ttu-id="89c06-142">BCL 是用于生成 ASP.NET Core 等较高级应用程序框架的较低级通用框架。</span><span class="sxs-lookup"><span data-stu-id="89c06-142">The BCL is a general purpose, lower-level framework that higher-level application frameworks, such as ASP.NET Core, build on.</span></span> <span data-ttu-id="89c06-143">.NET Core BCL 的源代码包含在 [CoreFX 存储库](https://github.com/dotnet/corefx)中。</span><span class="sxs-lookup"><span data-stu-id="89c06-143">The source code of the .NET Core BCL is contained in the [CoreFX repository](https://github.com/dotnet/corefx).</span></span> <span data-ttu-id="89c06-144">但大部分 .NET Core API 也可在 .NET Framework 中使用，因此可将 CoreFX 视为 .NET Framework BCL 的一个分支。</span><span class="sxs-lookup"><span data-stu-id="89c06-144">However, the majority of the .NET Core APIs are also available in the .NET Framework, so you can think of CoreFX as a fork of the .NET Framework BCL.</span></span>

## <a name="corert"></a><span data-ttu-id="89c06-145">CoreRT</span><span class="sxs-lookup"><span data-stu-id="89c06-145">CoreRT</span></span>

<span data-ttu-id="89c06-146">.NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="89c06-146">.NET Core runtime.</span></span>

<span data-ttu-id="89c06-147">与 CLR/CoreCLR 相比，CoreRT 不是虚拟机，这意味着它不包含用于快速生成并运行代码的功能，因为它不包括 [JIT](#jit)。</span><span class="sxs-lookup"><span data-stu-id="89c06-147">In contrast to the CLR/CoreCLR, CoreRT is not a virtual machine, which means it doesn't include the facilities to generate and run code on-the-fly because it doesn't include a [JIT](#jit).</span></span> <span data-ttu-id="89c06-148">但它包含 [GC](#gc) 以及运行时类型标识 (RTTI) 和反射功能。</span><span class="sxs-lookup"><span data-stu-id="89c06-148">It does, however, include the [GC](#gc) and the ability for runtime type identification (RTTI) and reflection.</span></span> <span data-ttu-id="89c06-149">只是由于设计有类型系统，因此并不需要元数据反射功能。</span><span class="sxs-lookup"><span data-stu-id="89c06-149">However, its type system is designed so that metadata for reflection isn't required.</span></span> <span data-ttu-id="89c06-150">包含这些功能使它具有 [AOT](#aot) 工具链，该工具链可去除多余的元数据，更重要的是可识别应用不使用的代码。</span><span class="sxs-lookup"><span data-stu-id="89c06-150">This enables having an [AOT](#aot) tool chain that can link away superfluous metadata and (more importantly) identify code that the app doesn't use.</span></span> <span data-ttu-id="89c06-151">CoreRT 正在开发中。</span><span class="sxs-lookup"><span data-stu-id="89c06-151">CoreRT is in development.</span></span>

<span data-ttu-id="89c06-152">请参阅 [.NET Native 和 CoreRT 简介](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span><span class="sxs-lookup"><span data-stu-id="89c06-152">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="ecosystem"></a><span data-ttu-id="89c06-153">生态系统</span><span class="sxs-lookup"><span data-stu-id="89c06-153">ecosystem</span></span>

<span data-ttu-id="89c06-154">所有针对给定技术生成和运行应用程序的运行时软件、开发工具和社区资源。</span><span class="sxs-lookup"><span data-stu-id="89c06-154">All of the runtime software, development tools, and community resources that are used to build and run applications for a given technology.</span></span>

<span data-ttu-id="89c06-155">在所包含的第三方应用和库方面，术语“.NET 生态系统”不同于类似的“.NET 堆栈”等术语。</span><span class="sxs-lookup"><span data-stu-id="89c06-155">The term ".NET ecosystem" differs from similar terms such as ".NET stack" in its inclusion of third-party apps and libraries.</span></span> <span data-ttu-id="89c06-156">请看以下这一句示例：</span><span class="sxs-lookup"><span data-stu-id="89c06-156">Here's an example in a sentence:</span></span>

- <span data-ttu-id="89c06-157">“推出 [.NET Standard](#net-standard) 的背后动机是要提高 .NET 生态系统中的一致性。”</span><span class="sxs-lookup"><span data-stu-id="89c06-157">"The motivation behind the [.NET Standard](#net-standard) is to establish greater uniformity in the .NET ecosystem."</span></span> 

## <a name="framework"></a><span data-ttu-id="89c06-158">框架</span><span class="sxs-lookup"><span data-stu-id="89c06-158">framework</span></span>

<span data-ttu-id="89c06-159">一般指一个综合 API 集合，便于开发和部署基于特定技术的应用程序。</span><span class="sxs-lookup"><span data-stu-id="89c06-159">In general, a comprehensive collection of APIs that facilitates development and deployment of applications that are based on a particular technology.</span></span> <span data-ttu-id="89c06-160">从此常规意义上来说，ASP.NET Core 和 Windows 窗体都是示例应用程序框架。</span><span class="sxs-lookup"><span data-stu-id="89c06-160">In this general sense, ASP.NET Core and Windows Forms are examples of application frameworks.</span></span> <span data-ttu-id="89c06-161">另请参阅[库](#library)。</span><span class="sxs-lookup"><span data-stu-id="89c06-161">See also [library](#library).</span></span>

<span data-ttu-id="89c06-162">“框架”一词在以下术语中有更具体的技术含义：</span><span class="sxs-lookup"><span data-stu-id="89c06-162">The word "framework" has a more specific technical meaning in the following terms:</span></span>
* [<span data-ttu-id="89c06-163">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="89c06-163">.NET Framework</span></span>](#net-framework)
* [<span data-ttu-id="89c06-164">目标框架</span><span class="sxs-lookup"><span data-stu-id="89c06-164">target framework</span></span>](#target-framework)
* [<span data-ttu-id="89c06-165">TFM（目标框架名字对象）</span><span class="sxs-lookup"><span data-stu-id="89c06-165">TFM (target framework moniker)</span></span>](#tfm)

<span data-ttu-id="89c06-166">在现有的文档中，“框架”有时指 [.NET 的实现](#implementation-of-net)。</span><span class="sxs-lookup"><span data-stu-id="89c06-166">In the existing documentation, "framework" sometimes refers to an [implementation of .NET](#implementation-of-net).</span></span> <span data-ttu-id="89c06-167">例如，某文章可能会将 .NET Core 称为框架。</span><span class="sxs-lookup"><span data-stu-id="89c06-167">For example, an article may call .NET Core a framework.</span></span> <span data-ttu-id="89c06-168">我们计划从文档中去掉这种令人困惑的用法。</span><span class="sxs-lookup"><span data-stu-id="89c06-168">We plan to eliminate this confusing usage from the documentation.</span></span>

## <a name="gc"></a><span data-ttu-id="89c06-169">“GC”</span><span class="sxs-lookup"><span data-stu-id="89c06-169">GC</span></span>

<span data-ttu-id="89c06-170">垃圾回收器。</span><span class="sxs-lookup"><span data-stu-id="89c06-170">Garbage collector.</span></span>

<span data-ttu-id="89c06-171">垃圾回收器是自动内存管理的实现。</span><span class="sxs-lookup"><span data-stu-id="89c06-171">The garbage collector is an implementation of automatic memory management.</span></span>  <span data-ttu-id="89c06-172">GC 可释放对象占用的不再使用的内存。</span><span class="sxs-lookup"><span data-stu-id="89c06-172">The GC frees memory occupied by objects that are no longer in use.</span></span> 

<span data-ttu-id="89c06-173">请参阅[垃圾回收](garbage-collection/index.md)。</span><span class="sxs-lookup"><span data-stu-id="89c06-173">See [Garbage Collection](garbage-collection/index.md).</span></span>

## <a name="il"></a><span data-ttu-id="89c06-174">IL</span><span class="sxs-lookup"><span data-stu-id="89c06-174">IL</span></span>

<span data-ttu-id="89c06-175">中间语言。</span><span class="sxs-lookup"><span data-stu-id="89c06-175">Intermediate language.</span></span>

<span data-ttu-id="89c06-176">C# 等较高级的 .NET 语言编译为称为中间语言 (IL) 的硬件无关性指令集。</span><span class="sxs-lookup"><span data-stu-id="89c06-176">Higher-level .NET languages, such as C#, compile down to a hardware-agnostic instruction set, which is called Intermediate Language (IL).</span></span> <span data-ttu-id="89c06-177">IL 有时被称为 MSIL (Microsoft IL) 或 CIL（通用 IL）。</span><span class="sxs-lookup"><span data-stu-id="89c06-177">IL is sometimes referred to as MSIL (Microsoft IL) or CIL (Common IL).</span></span>

## <a name="jit"></a><span data-ttu-id="89c06-178">JIT</span><span class="sxs-lookup"><span data-stu-id="89c06-178">JIT</span></span>

<span data-ttu-id="89c06-179">实时编译器。</span><span class="sxs-lookup"><span data-stu-id="89c06-179">Just-in-time compiler.</span></span>

<span data-ttu-id="89c06-180">与 [AOT](#aot) 类似，此编译器将 [IL](#il) 转换为处理器可理解的计算机代码。</span><span class="sxs-lookup"><span data-stu-id="89c06-180">Similar to [AOT](#aot), this compiler translates [IL](#il) to machine code that the processor understands.</span></span> <span data-ttu-id="89c06-181">与 AOT 不同，JIT 编译在需要运行代码的同一台计算机上按需执行。</span><span class="sxs-lookup"><span data-stu-id="89c06-181">Unlike AOT, JIT compilation happens on demand and is performed on the same machine that the code needs to run on.</span></span> <span data-ttu-id="89c06-182">由于 JIT 编译在应用程序的执行过程中发生，因此编译时是运行时的一部分。</span><span class="sxs-lookup"><span data-stu-id="89c06-182">Since JIT compilation occurs during execution of the application, compile time is part of the run time.</span></span> <span data-ttu-id="89c06-183">因此，JIT 编译器需要平衡优化代码所花费的时间与生成代码时可节约的时间。</span><span class="sxs-lookup"><span data-stu-id="89c06-183">Thus, JIT compilers have to balance time spent optimizing code against the savings that the resulting code can produce.</span></span> <span data-ttu-id="89c06-184">但 JIT 知道实际硬件，这样开发人员就无需提供不同的实现。</span><span class="sxs-lookup"><span data-stu-id="89c06-184">But a JIT knows the actual hardware and can free developers from having to ship different implementations.</span></span>

## <a name="implementation-of-net"></a><span data-ttu-id="89c06-185">.NET 实现</span><span class="sxs-lookup"><span data-stu-id="89c06-185">implementation of .NET</span></span>

<span data-ttu-id="89c06-186">.NET 的实现包括以下项：</span><span class="sxs-lookup"><span data-stu-id="89c06-186">An implementation of .NET includes the following:</span></span>

- <span data-ttu-id="89c06-187">一个或多个运行时。</span><span class="sxs-lookup"><span data-stu-id="89c06-187">One or more runtimes.</span></span> <span data-ttu-id="89c06-188">示例：CLR、CoreCLR、CoreRT。</span><span class="sxs-lookup"><span data-stu-id="89c06-188">Examples: CLR, CoreCLR, CoreRT.</span></span>
- <span data-ttu-id="89c06-189">实现 .NET Standard 的某版本并且可能包含其他 API 的类库。</span><span class="sxs-lookup"><span data-stu-id="89c06-189">A class library that implements a version of the .NET Standard and may include additional APIs.</span></span> <span data-ttu-id="89c06-190">示例：.NET Framework 基类库、.NET Core 基类库。</span><span class="sxs-lookup"><span data-stu-id="89c06-190">Examples: .NET Framework Base Class Library, .NET Core Base Class Library.</span></span>
- <span data-ttu-id="89c06-191">可选择包含一个或多个应用程序框架。</span><span class="sxs-lookup"><span data-stu-id="89c06-191">Optionally, one or more application frameworks.</span></span> <span data-ttu-id="89c06-192">示例： ASP.NET、Windows 窗体和 WPF 包含在 .NET Framework 中。</span><span class="sxs-lookup"><span data-stu-id="89c06-192">Examples: ASP.NET, Windows Forms, and WPF are included in the .NET Framework.</span></span>
- <span data-ttu-id="89c06-193">可包含开发工具。</span><span class="sxs-lookup"><span data-stu-id="89c06-193">Optionally, development tools.</span></span> <span data-ttu-id="89c06-194">某些开发工具在多个实现之间共享。</span><span class="sxs-lookup"><span data-stu-id="89c06-194">Some development tools are shared among multiple implementations.</span></span>

<span data-ttu-id="89c06-195">.NET 实现的示例：</span><span class="sxs-lookup"><span data-stu-id="89c06-195">Examples of .NET implementations:</span></span>

- [<span data-ttu-id="89c06-196">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="89c06-196">.NET Framework</span></span>](#net-framework)
- [<span data-ttu-id="89c06-197">.NET Core</span><span class="sxs-lookup"><span data-stu-id="89c06-197">.NET Core</span></span>](#net-core)
- [<span data-ttu-id="89c06-198">通用 Windows 平台 (UWP)</span><span class="sxs-lookup"><span data-stu-id="89c06-198">Universal Windows Platform (UWP)</span></span>](#uwp)

## <a name="library"></a><span data-ttu-id="89c06-199">库</span><span class="sxs-lookup"><span data-stu-id="89c06-199">library</span></span>

<span data-ttu-id="89c06-200">可由应用或其他库调用的 API 集合。</span><span class="sxs-lookup"><span data-stu-id="89c06-200">A collection of APIs that can be called by apps or other libraries.</span></span> <span data-ttu-id="89c06-201">.NET 库由一个或多个[程序集](#assembly)组成。</span><span class="sxs-lookup"><span data-stu-id="89c06-201">A .NET library is composed of one or more [assemblies](#assembly).</span></span>

<span data-ttu-id="89c06-202">词库和[框架](#framework)通常作同义词使用。</span><span class="sxs-lookup"><span data-stu-id="89c06-202">The words library and [framework](#framework) are often used synonymously.</span></span>

## <a name="metapackage"></a><span data-ttu-id="89c06-203">元包</span><span class="sxs-lookup"><span data-stu-id="89c06-203">metapackage</span></span>

<span data-ttu-id="89c06-204">一个 NuGet 包，没有自己的库，而只是一个依赖项列表。</span><span class="sxs-lookup"><span data-stu-id="89c06-204">A NuGet package that has no library of its own but is only a list of dependencies.</span></span> <span data-ttu-id="89c06-205">所含包可选择建立目标框架的 API。</span><span class="sxs-lookup"><span data-stu-id="89c06-205">The included packages can optionally establish the API for a target framework.</span></span>

<span data-ttu-id="89c06-206">请参阅[包、元包和框架](../core/packages.md)</span><span class="sxs-lookup"><span data-stu-id="89c06-206">See [Packages, Metapackages and Frameworks](../core/packages.md)</span></span>

## <a name="mono"></a><span data-ttu-id="89c06-207">Mono</span><span class="sxs-lookup"><span data-stu-id="89c06-207">Mono</span></span>

<span data-ttu-id="89c06-208">Mono 是主要在需要小型运行时使用的 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="89c06-208">Mono is a .NET implementation that is mainly used when a small runtime is required.</span></span> <span data-ttu-id="89c06-209">它是运行时，在 Android、Mac、iOS、tvOS 和 watchOS 上为 Xamarin 应用程序提供技术支持，主要针对内存占用少的应用程序。</span><span class="sxs-lookup"><span data-stu-id="89c06-209">It is the runtime that powers Xamarin applications on Android, Mac, iOS, tvOS and watchOS and is focused primarily on apps that require a small footprint.</span></span>

<span data-ttu-id="89c06-210">它支持所有当前已发布的 .NET Standard 版本。</span><span class="sxs-lookup"><span data-stu-id="89c06-210">It supports all of the currently published .NET Standard versions.</span></span>

<span data-ttu-id="89c06-211">以前，Mono 实现更大的 .NET Framework API 并模拟一些 Unix 上最常用的功能。</span><span class="sxs-lookup"><span data-stu-id="89c06-211">Historically, Mono implemented the larger API of the .NET Framework and emulated some of the most popular capabilities on Unix.</span></span> <span data-ttu-id="89c06-212">有时使用它运行依赖 Unix 上的这些功能的 .NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="89c06-212">It is sometimes used to run .NET applications that rely on those capabilities on Unix.</span></span>

<span data-ttu-id="89c06-213">Mono 通常与实时编译器一起使用，但它也提供在 iOS 之类的平台使用的完整静态编译器（预先编译）。</span><span class="sxs-lookup"><span data-stu-id="89c06-213">Mono is typically used with a just-in-time compiler, but it also features a full static compiler (ahead-of-time compilation) that is used on platforms like iOS.</span></span>

<span data-ttu-id="89c06-214">若要了解有关 Mono 的详细信息，请参阅 [Mono 文档](http://www.mono-project.com/docs/)。</span><span class="sxs-lookup"><span data-stu-id="89c06-214">To learn more about Mono, see the [Mono documentation](http://www.mono-project.com/docs/).</span></span>

## <a name="net"></a><span data-ttu-id="89c06-215">.NET</span><span class="sxs-lookup"><span data-stu-id="89c06-215">.NET</span></span>

<span data-ttu-id="89c06-216">[.NET Standard](#net-standard) 和所有 [.NET 实现](#implementation-of-net)及工作负荷的涵盖性术语。</span><span class="sxs-lookup"><span data-stu-id="89c06-216">The umbrella term for [.NET Standard](#net-standard) and all [.NET implementations](#implementation-of-net) and workloads.</span></span> <span data-ttu-id="89c06-217">始终采用大写形式，请勿使用“.Net”。</span><span class="sxs-lookup"><span data-stu-id="89c06-217">Always capitalized, never ".Net".</span></span>

<span data-ttu-id="89c06-218">请参阅 [.NET 指南](index.md)</span><span class="sxs-lookup"><span data-stu-id="89c06-218">See the [.NET Guide](index.md)</span></span>

## <a name="net-core"></a><span data-ttu-id="89c06-219">.NET 核心</span><span class="sxs-lookup"><span data-stu-id="89c06-219">.NET Core</span></span> 

<span data-ttu-id="89c06-220">一种跨平台、高性能的开放源 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="89c06-220">A cross-platform, high-performance, open source implementation of .NET.</span></span> <span data-ttu-id="89c06-221">包括 Core 公共语言运行时 (CoreCLR)、Core AOT 运行时（正在开发的 CoreRT）、Core 基类库和 Core SDK。</span><span class="sxs-lookup"><span data-stu-id="89c06-221">Includes the Core Common Language Runtime (CoreCLR), the Core AOT Runtime (CoreRT, in development), the Core Base Class Library, and the Core SDK.</span></span>

<span data-ttu-id="89c06-222">请参阅 [.NET Core](../core/index.md)。</span><span class="sxs-lookup"><span data-stu-id="89c06-222">See [.NET Core](../core/index.md).</span></span>

## <a name="net-core-cli"></a><span data-ttu-id="89c06-223">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="89c06-223">.NET Core CLI</span></span>

<span data-ttu-id="89c06-224">用于开发 .NET Core 应用程序的跨平台工具链。</span><span class="sxs-lookup"><span data-stu-id="89c06-224">A cross-platform toolchain for developing .NET Core applications.</span></span>

<span data-ttu-id="89c06-225">请参阅 [.NET Core 命令行接口 (CLI) 工具](../core/tools/index.md)。</span><span class="sxs-lookup"><span data-stu-id="89c06-225">See [.NET Core command-line interface (CLI) tools](../core/tools/index.md).</span></span>

## <a name="net-core-sdk"></a><span data-ttu-id="89c06-226">.NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="89c06-226">.NET Core SDK</span></span>

<span data-ttu-id="89c06-227">一组库和工具，开发人员可用其创建 .NET Core 应用程序和库。</span><span class="sxs-lookup"><span data-stu-id="89c06-227">A set of libraries and tools that allow developers to create .NET Core applications and libraries.</span></span> <span data-ttu-id="89c06-228">包括用于生成应用的 [.NET Core CLI](#net-core-cli)、用于生成和运行应用的 .NET Core 库以及运行 CLI 命令和运行应用程序的 dotnet 可执行文件 (dotnet.exe)。</span><span class="sxs-lookup"><span data-stu-id="89c06-228">Includes the [.NET Core CLI](#net-core-cli) for building apps, .NET Core libraries and runtime for building and running apps, and the dotnet executable (*dotnet.exe*) that runs CLI commands and runs applications.</span></span>

<span data-ttu-id="89c06-229">请参阅 [.NET Core SDK 概述](../core/sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="89c06-229">See [.NET Core SDK Overview](../core/sdk.md).</span></span>

## <a name="net-framework"></a><span data-ttu-id="89c06-230">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="89c06-230">.NET Framework</span></span>

<span data-ttu-id="89c06-231">仅在 Windows 上运行的 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="89c06-231">An implementation of .NET that runs only on Windows.</span></span> <span data-ttu-id="89c06-232">包括公共语言运行时 (CLR)、基类库和 ASP.NET、Windows 窗体和 WPF 之类的应用程序框架库。</span><span class="sxs-lookup"><span data-stu-id="89c06-232">Includes the Common Language Runtime (CLR), the Base Class Library, and application framework libraries such as ASP.NET, Windows Forms, and WPF.</span></span>

<span data-ttu-id="89c06-233">请查阅 [.NET Framework 指南](../framework/index.md)。</span><span class="sxs-lookup"><span data-stu-id="89c06-233">See [.NET Framework Guide](../framework/index.md).</span></span>

## <a name="net-native"></a><span data-ttu-id="89c06-234">.NET Native</span><span class="sxs-lookup"><span data-stu-id="89c06-234">.NET Native</span></span>

<span data-ttu-id="89c06-235">编译器工具链，可预先 (AOT) 生成，而非实时 (JIT) 生成本机代码。</span><span class="sxs-lookup"><span data-stu-id="89c06-235">A compiler tool chain that produces native code ahead-of-time (AOT), as opposed to just-in-time (JIT).</span></span>

<span data-ttu-id="89c06-236">编译采用与 C++ 编译器和链接器类似的工作方式在开发人员计算机上进行。</span><span class="sxs-lookup"><span data-stu-id="89c06-236">Compilation happens on the developer's machine similar to the way a C++ compiler and linker works.</span></span> <span data-ttu-id="89c06-237">它删除了未使用的代码，留出更多时间进行优化。</span><span class="sxs-lookup"><span data-stu-id="89c06-237">It removes unused code and spends more time optimizing it.</span></span> <span data-ttu-id="89c06-238">它从库中提取代码，将它们合并到可执行文件中。</span><span class="sxs-lookup"><span data-stu-id="89c06-238">It extracts code from libraries and merges them into the executable.</span></span> <span data-ttu-id="89c06-239">结果是表示整个应用的单个模块。</span><span class="sxs-lookup"><span data-stu-id="89c06-239">The result is a single module that represents the entire app.</span></span>

<span data-ttu-id="89c06-240">UWP 是 .NET Native 支持的首个应用程序框架。</span><span class="sxs-lookup"><span data-stu-id="89c06-240">UWP was the first application framework supported by .NET Native.</span></span> <span data-ttu-id="89c06-241">现在，我们支持为 Windows、macOS 和 Linux 生成本机控制台应用。</span><span class="sxs-lookup"><span data-stu-id="89c06-241">Now, we support building native console apps for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="89c06-242">请参阅 [.NET Native 和 CoreRT 简介](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span><span class="sxs-lookup"><span data-stu-id="89c06-242">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="net-standard"></a><span data-ttu-id="89c06-243">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="89c06-243">.NET Standard</span></span>

<span data-ttu-id="89c06-244">在每个 .NET 实现中都可用的 .NET API 正式规范。</span><span class="sxs-lookup"><span data-stu-id="89c06-244">A formal specification of .NET APIs that are available in each .NET implementation.</span></span>

<span data-ttu-id="89c06-245">.NET Standard 规范有时被称为文档中的库。</span><span class="sxs-lookup"><span data-stu-id="89c06-245">The .NET Standard specification is sometimes called a library in the documentation.</span></span> <span data-ttu-id="89c06-246">由于库不仅包括规范（接口），还包括 API 实现，所以会误将 .NET Standard 称为“库”。</span><span class="sxs-lookup"><span data-stu-id="89c06-246">Because a library includes API implementations, not only specifications (interfaces), it's misleading to call .NET Standard a "library."</span></span> <span data-ttu-id="89c06-247">我们计划从本文档中去除该用法，引用 .NET Standard 元包 (`NETStandard.Library`) 的名称除外。</span><span class="sxs-lookup"><span data-stu-id="89c06-247">We plan to eliminate that usage from the documentation, except in reference to the name of the .NET Standard metapackage (`NETStandard.Library`).</span></span>

<span data-ttu-id="89c06-248">请参阅 [.NET Standard](net-standard.md)。</span><span class="sxs-lookup"><span data-stu-id="89c06-248">See [.NET Standard](net-standard.md).</span></span>

## <a name="ngen"></a><span data-ttu-id="89c06-249">NGEN</span><span class="sxs-lookup"><span data-stu-id="89c06-249">NGEN</span></span>

<span data-ttu-id="89c06-250">本机（映像）生成。</span><span class="sxs-lookup"><span data-stu-id="89c06-250">Native (image) generation.</span></span>

<span data-ttu-id="89c06-251">可将此方法视为永久性 JIT 编译器。</span><span class="sxs-lookup"><span data-stu-id="89c06-251">You can think of this technology as a persistent JIT compiler.</span></span> <span data-ttu-id="89c06-252">它通常在执行代码的计算机上编译该代码，但通常在安装时进行编译。</span><span class="sxs-lookup"><span data-stu-id="89c06-252">It usually compiles code on the machine where the code is executed, but compilation typically occurs at install time.</span></span>

## <a name="package"></a><span data-ttu-id="89c06-253">包</span><span class="sxs-lookup"><span data-stu-id="89c06-253">package</span></span>

<span data-ttu-id="89c06-254">NuGet 包 &mdash; 或只是一个包 &mdash; 是一个 .zip 文件，其中具有一个或多个名称相同的程序集以及作者姓名等其他元数据。</span><span class="sxs-lookup"><span data-stu-id="89c06-254">A NuGet package &mdash; or just a package &mdash; is a *.zip* file with one or more assemblies of the same name along with additional metadata such as the author name.</span></span>

<span data-ttu-id="89c06-255">.zip 文件的扩展名为 .nupkg，且可以包含在多个目标框架和版本中使用的资产（如 .dll 文件和 .xml 文件）。</span><span class="sxs-lookup"><span data-stu-id="89c06-255">The *.zip* file has a *.nupkg* extension and may contain assets, such as *.dll* files and *.xml* files, for use with multiple target frameworks and versions.</span></span> <span data-ttu-id="89c06-256">在应用或库中安装时，会根据应用或库指定的目标框架选择相应的资产。</span><span class="sxs-lookup"><span data-stu-id="89c06-256">When installed in an app or library, the appropriate assets are selected based on the target framework specified by the app or library.</span></span> <span data-ttu-id="89c06-257">定义接口的资产位于 ref 文件夹，而定义实现的资产位于 lib文件夹。</span><span class="sxs-lookup"><span data-stu-id="89c06-257">The assets that define the interface are in the *ref* folder, and the assets that define the implementation are in the *lib* folder.</span></span>

## <a name="platform"></a><span data-ttu-id="89c06-258">平台</span><span class="sxs-lookup"><span data-stu-id="89c06-258">platform</span></span>

<span data-ttu-id="89c06-259">操作系统以及运行它的硬件，例如 Windows、macOS、Linux、iOS 和 Android。</span><span class="sxs-lookup"><span data-stu-id="89c06-259">An operating system and the hardware it runs on, such as Windows, macOS, Linux, iOS, and Android.</span></span>

<span data-ttu-id="89c06-260">下面是在句子中使用的示例：</span><span class="sxs-lookup"><span data-stu-id="89c06-260">Here are examples of usage in sentences:</span></span>

- <span data-ttu-id="89c06-261">“.NET Core 是一个跨平台 .NET 实现。”</span><span class="sxs-lookup"><span data-stu-id="89c06-261">".NET Core is a cross-platform implementation of .NET."</span></span> 
- <span data-ttu-id="89c06-262">“PCL 配置文件代表 Microsoft 平台，而 .NET Standard 与平台无关。”</span><span class="sxs-lookup"><span data-stu-id="89c06-262">"PCL profiles represent Microsoft platforms, while the .NET Standard is agnostic to platform."</span></span>

<span data-ttu-id="89c06-263">.NET 文档经常使用“.NET 平台”表示一个 .NET 实现或包括所有实现的 .NET 堆栈。</span><span class="sxs-lookup"><span data-stu-id="89c06-263">The .NET documentation frequently uses ".NET platform" to mean either an implementation of .NET or the .NET stack including all implementations.</span></span> <span data-ttu-id="89c06-264">这两种用法往往会与主（OS/硬件）含义混淆，因此我们计划从文档中去除这些用法。</span><span class="sxs-lookup"><span data-stu-id="89c06-264">Both of these usages tend to get confused with the primary (OS/hardware) meaning, so we plan to eliminate these usages from the documentation.</span></span>

## <a name="runtime"></a><span data-ttu-id="89c06-265">Runtime — 运行时</span><span class="sxs-lookup"><span data-stu-id="89c06-265">runtime</span></span>

<span data-ttu-id="89c06-266">用于托管程序的执行环境。</span><span class="sxs-lookup"><span data-stu-id="89c06-266">The execution environment for a managed program.</span></span>

<span data-ttu-id="89c06-267">OS 属于运行时环境，但不属于 .NET 运行时。</span><span class="sxs-lookup"><span data-stu-id="89c06-267">The OS is part of the runtime environment but is not part of the .NET runtime.</span></span> <span data-ttu-id="89c06-268">下面是 .NET 运行时的一些示例：</span><span class="sxs-lookup"><span data-stu-id="89c06-268">Here are some examples of .NET runtimes:</span></span>

- <span data-ttu-id="89c06-269">公共语言运行时 (CLR)</span><span class="sxs-lookup"><span data-stu-id="89c06-269">Common Language Runtime (CLR)</span></span>
- <span data-ttu-id="89c06-270">Core 公共语言运行时 (CoreCLR)</span><span class="sxs-lookup"><span data-stu-id="89c06-270">Core Common Language Runtime (CoreCLR)</span></span>
- <span data-ttu-id="89c06-271">.NET Native（适用于 UWP）</span><span class="sxs-lookup"><span data-stu-id="89c06-271">.NET Native (for UWP)</span></span>
- <span data-ttu-id="89c06-272">Mono 运行时</span><span class="sxs-lookup"><span data-stu-id="89c06-272">Mono runtime</span></span>

<span data-ttu-id="89c06-273">.NET 文档有时使用“运行时”表示 .NET 的实现。</span><span class="sxs-lookup"><span data-stu-id="89c06-273">The .NET documentation sometimes uses "runtime" to mean an implementation of .NET.</span></span> <span data-ttu-id="89c06-274">例如，在以下句子中应使用“实现”替换“运行时”：</span><span class="sxs-lookup"><span data-stu-id="89c06-274">For example, in the following sentences "runtime" should be replaced with "implementation":</span></span>

- <span data-ttu-id="89c06-275">“各种 .NET 运行时实现特定版本的 .NET Standard。”</span><span class="sxs-lookup"><span data-stu-id="89c06-275">"The various .NET runtimes implement specific versions of .NET Standard."</span></span>
- <span data-ttu-id="89c06-276">“计划在多个运行时上运行的库应将此框架作为目标。”</span><span class="sxs-lookup"><span data-stu-id="89c06-276">"Libraries that are intended to run on multiple runtimes should target this framework."</span></span> <span data-ttu-id="89c06-277">（参阅 .NET Standard）</span><span class="sxs-lookup"><span data-stu-id="89c06-277">(referring to .NET Standard)</span></span>
- <span data-ttu-id="89c06-278">“各种 .NET 运行时实现特定版本的 .NET Standard。</span><span class="sxs-lookup"><span data-stu-id="89c06-278">"The various .NET runtimes implement specific versions of .NET Standard.</span></span> <span data-ttu-id="89c06-279">…</span><span class="sxs-lookup"><span data-stu-id="89c06-279">…</span></span> <span data-ttu-id="89c06-280">每个 .NET 运行时版本都将会公布它所支持的最高 .NET Standard 版本...”</span><span class="sxs-lookup"><span data-stu-id="89c06-280">Each .NET runtime version advertises the highest .NET Standard version it supports …"</span></span>

<span data-ttu-id="89c06-281">我们计划消除此不一致的用法。</span><span class="sxs-lookup"><span data-stu-id="89c06-281">We plan to eliminate this inconsistent usage.</span></span> 

## <a name="stack"></a><span data-ttu-id="89c06-282">堆栈</span><span class="sxs-lookup"><span data-stu-id="89c06-282">stack</span></span>

<span data-ttu-id="89c06-283">一组编程方法，一起用于生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="89c06-283">A set of programming technologies that are used together to build and run applications.</span></span>

<span data-ttu-id="89c06-284">“.NET 堆栈”指 .NET Standard 和所有 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="89c06-284">"The .NET stack" refers to the .NET Standard and all .NET implementations.</span></span> <span data-ttu-id="89c06-285">短语“一个 .NET 堆栈”可能指一种 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="89c06-285">The phrase "a .NET stack" may refer to one implementation of .NET.</span></span> 

## <a name="target-framework"></a><span data-ttu-id="89c06-286">Target Framework — 目标 Framework</span><span class="sxs-lookup"><span data-stu-id="89c06-286">target framework</span></span>

<span data-ttu-id="89c06-287">.NET 应用或库依赖的 API 集合。</span><span class="sxs-lookup"><span data-stu-id="89c06-287">The collection of APIs that a .NET app or library relies on.</span></span>

<span data-ttu-id="89c06-288">应用或库可将某版本的 .NET Standard（例如 .NET Standard 2.0）作为目标，这是所有 .NET 实现中一组标准化 API 的规范。</span><span class="sxs-lookup"><span data-stu-id="89c06-288">An app or library can target a version of .NET Standard (for example, .NET Standard 2.0), which is specification for a standardized set of APIs across all .NET implementations.</span></span> <span data-ttu-id="89c06-289">应用或库还能以特定 .NET 的某版本实现为目标，这样便可获得特定于实现的 API 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="89c06-289">An app or library can also target a version of a specific .NET implementation, in which case it gets access to implementation-specific APIs.</span></span> <span data-ttu-id="89c06-290">例如，面向 Xamarin.iOS 的应用有权访问 Xamarin 提供的 iOS API 包装器。</span><span class="sxs-lookup"><span data-stu-id="89c06-290">For example, an app that targets Xamarin.iOS gets access to Xamarin-provided iOS API wrappers.</span></span>

<span data-ttu-id="89c06-291">对于某些目标框架（例如 .NET Framework），可用 API 由 .NET 实现在系统上安装的程序集定义，其中可能包括应用程序框架 API（例如 ASP.NET、WinForms）。</span><span class="sxs-lookup"><span data-stu-id="89c06-291">For some target frameworks (for example, the .NET Framework) the available APIs are defined by the assemblies that a .NET implementation installs on a system, which may include application framework APIs (for example, ASP.NET, WinForms).</span></span> <span data-ttu-id="89c06-292">对于基于包的目标框架（例如 .NET Standard 和 .NET Core），框架 API 由安装在应用或库中的包定义。</span><span class="sxs-lookup"><span data-stu-id="89c06-292">For package-based target frameworks (such as .NET Standard and .NET Core), the framework APIs are defined by the packages installed in the app or library.</span></span> <span data-ttu-id="89c06-293">在这种情况下，目标框架隐式指定一个元包，该元包引用一起构成框架的所有包。</span><span class="sxs-lookup"><span data-stu-id="89c06-293">In that case, the target framework implicitly specifies a metapackage that references all the packages that together make up the framework.</span></span>

<span data-ttu-id="89c06-294">请参阅[目标框架](frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="89c06-294">See [Target Frameworks](frameworks.md).</span></span>

## <a name="tfm"></a><span data-ttu-id="89c06-295">TFM</span><span class="sxs-lookup"><span data-stu-id="89c06-295">TFM</span></span>

<span data-ttu-id="89c06-296">目标框架名字对象。</span><span class="sxs-lookup"><span data-stu-id="89c06-296">Target framework moniker.</span></span>

<span data-ttu-id="89c06-297">一个标准化令牌格式，用于指定 .NET 应用或库的目标框架。</span><span class="sxs-lookup"><span data-stu-id="89c06-297">A standardized token format for specifying the target framework of a .NET app or library.</span></span> <span data-ttu-id="89c06-298">目标框架通常由短名称（如 `net462`）引用。</span><span class="sxs-lookup"><span data-stu-id="89c06-298">Target frameworks are typically referenced by a short name, such as `net462`.</span></span> <span data-ttu-id="89c06-299">存在长格式的 TFM（如 .NETFramework,Version=4.6.2），但通常不用来指定目标框架。</span><span class="sxs-lookup"><span data-stu-id="89c06-299">Long-form TFMs (such as .NETFramework,Version=4.6.2) exist but are not generally used to specify a target framework.</span></span>

<span data-ttu-id="89c06-300">请参阅[目标框架](frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="89c06-300">See [Target Frameworks](frameworks.md).</span></span>

## <a name="uwp"></a><span data-ttu-id="89c06-301">UWP</span><span class="sxs-lookup"><span data-stu-id="89c06-301">UWP</span></span>

<span data-ttu-id="89c06-302">通用 Windows 平台。</span><span class="sxs-lookup"><span data-stu-id="89c06-302">Universal Windows Platform.</span></span>

<span data-ttu-id="89c06-303">用于为物联网 (IoT) 生成新式触控 Windows 应用程序和软件的 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="89c06-303">An implementation of .NET that is used for building modern, touch-enabled Windows applications and software for the Internet of Things (IoT).</span></span> <span data-ttu-id="89c06-304">它旨在统一可能想要以其为目标的不同类型的设备，包括电脑、平板电脑、平板手机、电话，甚至 Xbox。</span><span class="sxs-lookup"><span data-stu-id="89c06-304">It's designed to unify the different types of devices that you may want to target, including PCs, tablets, phablets, phones, and even the Xbox.</span></span> <span data-ttu-id="89c06-305">UWP 提供许多服务，如集中式应用商店、执行环境 (AppContainer) 和一组 Windows API（用于代替 Win32 (WinRT)）。</span><span class="sxs-lookup"><span data-stu-id="89c06-305">UWP provides many services, such as a centralized app store, an execution environment (AppContainer), and a set of Windows APIs to use instead of Win32 (WinRT).</span></span> <span data-ttu-id="89c06-306">应用可采用 C++、C#、VB.NET 和 JavaScript 编写。</span><span class="sxs-lookup"><span data-stu-id="89c06-306">Apps can be written in C++, C#, VB.NET, and JavaScript.</span></span> <span data-ttu-id="89c06-307">使用 C# 和 VB.NET 时，.NET API 由 .NET Core 提供。</span><span class="sxs-lookup"><span data-stu-id="89c06-307">When using C# and VB.NET, the .NET APIs are provided by .NET Core.</span></span>

## <a name="see-also"></a><span data-ttu-id="89c06-308">请参阅</span><span class="sxs-lookup"><span data-stu-id="89c06-308">See also</span></span>

[<span data-ttu-id="89c06-309">.NET 指南</span><span class="sxs-lookup"><span data-stu-id="89c06-309">.NET Guide</span></span>](index.md)  
[<span data-ttu-id="89c06-310">.NET Framework 指南</span><span class="sxs-lookup"><span data-stu-id="89c06-310">.NET Framework Guide</span></span>](../framework/index.md)  
[<span data-ttu-id="89c06-311">.NET Core</span><span class="sxs-lookup"><span data-stu-id="89c06-311">.NET Core</span></span>](../core/index.md)  
[<span data-ttu-id="89c06-312">ASP.NET 概述</span><span class="sxs-lookup"><span data-stu-id="89c06-312">ASP.NET Overview</span></span>](/aspnet/index#pivot=aspnet)  
[<span data-ttu-id="89c06-313"> 概述</span><span class="sxs-lookup"><span data-stu-id="89c06-313">ASP.NET Core Overview</span></span>](/aspnet/index#pivot=core)  

