---
title: .NET 术语表
description: 了解 .NET 文档中所用的选定术语的含义。
author: tdykstra
ms.author: tdykstra
ms.date: 07/08/2017
ms.technology: dotnet-standard
ms.openlocfilehash: 4ffcf56ba171192048a736b58ddcfa591fd3af58
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2018
ms.locfileid: "48840266"
---
# <a name="net-glossary"></a><span data-ttu-id="ed2f2-103">.NET 术语表</span><span class="sxs-lookup"><span data-stu-id="ed2f2-103">.NET Glossary</span></span>

<span data-ttu-id="ed2f2-104">此术语表的主要目的是阐明所选术语和缩写词的含义，这些词频繁出现在 .NET 文档中但没有定义。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-104">The primary goal of this glossary is to clarify meanings of selected terms and acronyms that appear frequently in the .NET documentation without definitions.</span></span>

## <a name="aot"></a><span data-ttu-id="ed2f2-105">AOT</span><span class="sxs-lookup"><span data-stu-id="ed2f2-105">AOT</span></span>

<span data-ttu-id="ed2f2-106">预编译器。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-106">Ahead-of-time compiler.</span></span>

<span data-ttu-id="ed2f2-107">与 [JIT](#jit) 类似，此编译器还可将 [IL](#il) 转换为机器代码。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-107">Similar to [JIT](#jit), this compiler also translates [IL](#il) to machine code.</span></span> <span data-ttu-id="ed2f2-108">与 JIT 编译相比，AOT 编译在应用程序执行前进行并且通常在不同计算机上执行。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-108">In contrast to JIT compilation, AOT compilation happens before the application is executed and is usually performed on a different machine.</span></span> <span data-ttu-id="ed2f2-109">由于在运行时 AOT 工具链不编译，因此它们不需要最大程度地减少编译所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-109">Because AOT tool chains don't compile at runtime, they don't have to minimize time spent compiling.</span></span> <span data-ttu-id="ed2f2-110">这意味着它们可花更多的时间进行优化。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-110">That means they can spend more time optimizing.</span></span> <span data-ttu-id="ed2f2-111">由于 AOT 的上下文是整个应用程序，因此 AOT 编译器还会执行跨模块链接和全程序分析，这意味着之后会进行所有引用并会生成单个可执行文件。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-111">Since the context of AOT is the entire application, the AOT compiler also performs cross-module linking and whole-program analysis, which means that all references are followed and a single executable is produced.</span></span>

## <a name="aspnet"></a><span data-ttu-id="ed2f2-112">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ed2f2-112">ASP.NET</span></span> 

<span data-ttu-id="ed2f2-113">随 .NET Framework 一起提供的原始 ASP.NET 实现。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-113">The original ASP.NET implementation that ships with the .NET Framework.</span></span>

<span data-ttu-id="ed2f2-114">有时 ASP.NET 是一个涵盖性术语，指包含 ASP.NET Core 在内的两个 ASP.NET 实现。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-114">Sometimes ASP.NET is an umbrella term that refers to both ASP.NET implementations including ASP.NET Core.</span></span> <span data-ttu-id="ed2f2-115">该术语在任何给定实例中的含义取决于上下文。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-115">The meaning that the term carries in any given instance is determined by context.</span></span> <span data-ttu-id="ed2f2-116">若要指明不要使用 ASP.NET 表示这两种实现，请参考 ASP.NET 4.x。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-116">Refer to ASP.NET 4.x when you want to make it clear that you’re not using ASP.NET to mean both implementations.</span></span> 

<span data-ttu-id="ed2f2-117">请参阅 [ASP.NET 文档](/aspnet/#pivot=aspnet)。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-117">See [ASP.NET documentation](/aspnet/#pivot=aspnet).</span></span>

## <a name="aspnet-core"></a><span data-ttu-id="ed2f2-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ed2f2-118">ASP.NET Core</span></span>

<span data-ttu-id="ed2f2-119">.NET Core 上生成的跨平台、高性能、 开放源 ASP.NET 实现。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-119">A cross-platform, high-performance, open source implementation of ASP.NET built on .NET Core.</span></span>

<span data-ttu-id="ed2f2-120">请参阅 [ASP.NET Core 文档](/aspnet/#pivot=core)。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-120">See [ASP.NET Core documentation](/aspnet/#pivot=core).</span></span>

## <a name="assembly"></a><span data-ttu-id="ed2f2-121">程序集</span><span class="sxs-lookup"><span data-stu-id="ed2f2-121">assembly</span></span>

<span data-ttu-id="ed2f2-122">.dll/.exe 文件，其中包含一组可由应用程序或其他程序集调用的 API。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-122">A *.dll*/*.exe* file that can contain a collection of APIs that can be called by applications or other assemblies.</span></span>

<span data-ttu-id="ed2f2-123">程序集可以包括接口、类、结构、枚举和委托等类型。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-123">An assembly may include types such as interfaces, classes, structures, enumerations, and delegates.</span></span> <span data-ttu-id="ed2f2-124">有时，项目的 bin 文件夹中的程序集被称为二进制文件。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-124">Assemblies in a project's *bin* folder are sometimes referred to as *binaries*.</span></span> <span data-ttu-id="ed2f2-125">另请参阅[库](#library)。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-125">See also [library](#library).</span></span>

## <a name="clr"></a><span data-ttu-id="ed2f2-126">CLR</span><span class="sxs-lookup"><span data-stu-id="ed2f2-126">CLR</span></span>

<span data-ttu-id="ed2f2-127">公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-127">Common Language Runtime.</span></span>

<span data-ttu-id="ed2f2-128">确切含义取决于上下文，但它通常指 .NET Framework 的运行时。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-128">The exact meaning depends on the context, but this usually refers to the runtime of the .NET Framework.</span></span> <span data-ttu-id="ed2f2-129">CLR 处理内存分配和管理。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-129">The CLR handles memory allocation and management.</span></span> <span data-ttu-id="ed2f2-130">CLR 也是一个虚拟机，不仅可执行应用，还可使用 [JIT](#jit) 编译器快速生成和编译代码。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-130">The CLR is also a virtual machine that not only executes apps but also generates and compiles code on-the-fly using a [JIT](#jit) compiler.</span></span> <span data-ttu-id="ed2f2-131">当前的 Microsoft CLR 实现仅限 Windows。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-131">The current Microsoft CLR implementation is Windows only.</span></span>

## <a name="coreclr"></a><span data-ttu-id="ed2f2-132">CoreCLR</span><span class="sxs-lookup"><span data-stu-id="ed2f2-132">CoreCLR</span></span>

<span data-ttu-id="ed2f2-133">.NET Core 公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-133">.NET Core Common Language Runtime.</span></span>

<span data-ttu-id="ed2f2-134">此 CLR 是采用与 CLR 相同的基本代码生成的。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-134">This CLR is built from the same code base as the CLR.</span></span> <span data-ttu-id="ed2f2-135">最初，CoreCLR 是 Silverlight 的运行时，专为在多个平台（特别是 Windows 和 OS X）上运行而开发。CoreCLR 现属于 .NET Core 并表示 CLR 的简化版本。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-135">Originally, CoreCLR was the runtime of Silverlight and was designed to run on multiple platforms, specifically Windows and OS X. CoreCLR is now part of .NET Core and represents a simplified version of the CLR.</span></span> <span data-ttu-id="ed2f2-136">它仍是[跨平台](#cross-platform)运行时，现包括针对许多 Linux 分发的支持。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-136">It's still a [cross-platform](#cross-platform) runtime, now including support for many Linux distributions.</span></span> <span data-ttu-id="ed2f2-137">CoreCLR 也是具有 JIT 和代码执行功能的虚拟机。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-137">CoreCLR is also a virtual machine with JIT and code execution capabilities.</span></span>

## <a name="corefx"></a><span data-ttu-id="ed2f2-138">CoreFX</span><span class="sxs-lookup"><span data-stu-id="ed2f2-138">CoreFX</span></span>

<span data-ttu-id="ed2f2-139">.NET Core 基类库 (BCL)</span><span class="sxs-lookup"><span data-stu-id="ed2f2-139">.NET Core Base Class Library (BCL)</span></span>

<span data-ttu-id="ed2f2-140">一组构成 System.\*（在一定的程度上构成 Microsoft.\*）命名空间的库。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-140">A set of libraries that comprise the System.\* (and to a limited extent  Microsoft.\*) namespaces.</span></span> <span data-ttu-id="ed2f2-141">BCL 是用于生成 ASP.NET Core 等较高级应用程序框架的较低级通用框架。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-141">The BCL is a general purpose, lower-level framework that higher-level application frameworks, such as ASP.NET Core, build on.</span></span> <span data-ttu-id="ed2f2-142">.NET Core BCL 的源代码包含在 [CoreFX 存储库](https://github.com/dotnet/corefx)中。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-142">The source code of the .NET Core BCL is contained in the [CoreFX repository](https://github.com/dotnet/corefx).</span></span> <span data-ttu-id="ed2f2-143">但大部分 .NET Core API 也可在 .NET Framework 中使用，因此可将 CoreFX 视为 .NET Framework BCL 的一个分支。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-143">However, the majority of the .NET Core APIs are also available in the .NET Framework, so you can think of CoreFX as a fork of the .NET Framework BCL.</span></span>

## <a name="corert"></a><span data-ttu-id="ed2f2-144">CoreRT</span><span class="sxs-lookup"><span data-stu-id="ed2f2-144">CoreRT</span></span>

<span data-ttu-id="ed2f2-145">.NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-145">.NET Core runtime.</span></span>

<span data-ttu-id="ed2f2-146">与 CLR/CoreCLR 相比，CoreRT 不是虚拟机，这意味着它不包含用于快速生成并运行代码的功能，因为它不包括 [JIT](#jit)。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-146">In contrast to the CLR/CoreCLR, CoreRT is not a virtual machine, which means it doesn't include the facilities to generate and run code on-the-fly because it doesn't include a [JIT](#jit).</span></span> <span data-ttu-id="ed2f2-147">但它包含 [GC](#gc) 以及运行时类型标识 (RTTI) 和反射功能。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-147">It does, however, include the [GC](#gc) and the ability for runtime type identification (RTTI) and reflection.</span></span> <span data-ttu-id="ed2f2-148">只是由于设计有类型系统，因此并不需要元数据反射功能。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-148">However, its type system is designed so that metadata for reflection isn't required.</span></span> <span data-ttu-id="ed2f2-149">包含这些功能使它具有 [AOT](#aot) 工具链，该工具链可去除多余的元数据，更重要的是可识别应用不使用的代码。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-149">This enables having an [AOT](#aot) tool chain that can link away superfluous metadata and (more importantly) identify code that the app doesn't use.</span></span> <span data-ttu-id="ed2f2-150">CoreRT 正在开发中。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-150">CoreRT is in development.</span></span>

<span data-ttu-id="ed2f2-151">请参阅 [.NET Native 和 CoreRT 简介](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span><span class="sxs-lookup"><span data-stu-id="ed2f2-151">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="cross-platform"></a><span data-ttu-id="ed2f2-152">跨平台</span><span class="sxs-lookup"><span data-stu-id="ed2f2-152">cross-platform</span></span>

<span data-ttu-id="ed2f2-153">能够开发并执行可在多个不同操作系统（如 Linux、Windows 和 iOS）上使用的应用程序，而无需专门针对每个操作系统进行重新编写。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-153">The ability to develop and execute an application that can be used on multiple different operating systems, such as Linux, Windows and iOS, without having to re-write specifically for each one.</span></span> <span data-ttu-id="ed2f2-154">这样，可以在不同平台上的应用程序之间重复使用代码并保持一致性。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-154">This enables code re-use and consistency between applications on different platforms.</span></span>

## <a name="ecosystem"></a><span data-ttu-id="ed2f2-155">生态系统</span><span class="sxs-lookup"><span data-stu-id="ed2f2-155">ecosystem</span></span>

<span data-ttu-id="ed2f2-156">所有针对给定技术生成和运行应用程序的运行时软件、开发工具和社区资源。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-156">All of the runtime software, development tools, and community resources that are used to build and run applications for a given technology.</span></span>

<span data-ttu-id="ed2f2-157">在所包含的第三方应用和库方面，术语“.NET 生态系统”不同于类似的“.NET 堆栈”等术语。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-157">The term ".NET ecosystem" differs from similar terms such as ".NET stack" in its inclusion of third-party apps and libraries.</span></span> <span data-ttu-id="ed2f2-158">请看以下这一句示例：</span><span class="sxs-lookup"><span data-stu-id="ed2f2-158">Here's an example in a sentence:</span></span>

- <span data-ttu-id="ed2f2-159">“推出 [.NET Standard](#net-standard) 的背后动机是要提高 .NET 生态系统中的一致性。”</span><span class="sxs-lookup"><span data-stu-id="ed2f2-159">"The motivation behind the [.NET Standard](#net-standard) is to establish greater uniformity in the .NET ecosystem."</span></span> 

## <a name="framework"></a><span data-ttu-id="ed2f2-160">框架</span><span class="sxs-lookup"><span data-stu-id="ed2f2-160">framework</span></span>

<span data-ttu-id="ed2f2-161">一般指一个综合 API 集合，便于开发和部署基于特定技术的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-161">In general, a comprehensive collection of APIs that facilitates development and deployment of applications that are based on a particular technology.</span></span> <span data-ttu-id="ed2f2-162">从此常规意义上来说，ASP.NET Core 和 Windows 窗体都是示例应用程序框架。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-162">In this general sense, ASP.NET Core and Windows Forms are examples of application frameworks.</span></span> <span data-ttu-id="ed2f2-163">另请参阅[库](#library)。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-163">See also [library](#library).</span></span>

<span data-ttu-id="ed2f2-164">“框架”一词在以下术语中有更具体的技术含义：</span><span class="sxs-lookup"><span data-stu-id="ed2f2-164">The word "framework" has a more specific technical meaning in the following terms:</span></span>
* [<span data-ttu-id="ed2f2-165">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="ed2f2-165">.NET Framework</span></span>](#net-framework)
* [<span data-ttu-id="ed2f2-166">目标框架</span><span class="sxs-lookup"><span data-stu-id="ed2f2-166">target framework</span></span>](#target-framework)
* [<span data-ttu-id="ed2f2-167">TFM（目标框架名字对象）</span><span class="sxs-lookup"><span data-stu-id="ed2f2-167">TFM (target framework moniker)</span></span>](#tfm)

<span data-ttu-id="ed2f2-168">在现有的文档中，“框架”有时指 [.NET 的实现](#implementation-of-net)。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-168">In the existing documentation, "framework" sometimes refers to an [implementation of .NET](#implementation-of-net).</span></span> <span data-ttu-id="ed2f2-169">例如，某文章可能会将 .NET Core 称为框架。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-169">For example, an article may call .NET Core a framework.</span></span> <span data-ttu-id="ed2f2-170">我们计划从文档中去掉这种令人困惑的用法。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-170">We plan to eliminate this confusing usage from the documentation.</span></span>

## <a name="gc"></a><span data-ttu-id="ed2f2-171">“GC”</span><span class="sxs-lookup"><span data-stu-id="ed2f2-171">GC</span></span>

<span data-ttu-id="ed2f2-172">垃圾回收器。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-172">Garbage collector.</span></span>

<span data-ttu-id="ed2f2-173">垃圾回收器是自动内存管理的实现。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-173">The garbage collector is an implementation of automatic memory management.</span></span>  <span data-ttu-id="ed2f2-174">GC 可释放对象占用的不再使用的内存。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-174">The GC frees memory occupied by objects that are no longer in use.</span></span> 

<span data-ttu-id="ed2f2-175">请参阅[垃圾回收](garbage-collection/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-175">See [Garbage Collection](garbage-collection/index.md).</span></span>

## <a name="il"></a><span data-ttu-id="ed2f2-176">IL</span><span class="sxs-lookup"><span data-stu-id="ed2f2-176">IL</span></span>

<span data-ttu-id="ed2f2-177">中间语言。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-177">Intermediate language.</span></span>

<span data-ttu-id="ed2f2-178">C# 等较高级的 .NET 语言编译为称为中间语言 (IL) 的硬件无关性指令集。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-178">Higher-level .NET languages, such as C#, compile down to a hardware-agnostic instruction set, which is called Intermediate Language (IL).</span></span> <span data-ttu-id="ed2f2-179">IL 有时被称为 MSIL (Microsoft IL) 或 CIL（通用 IL）。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-179">IL is sometimes referred to as MSIL (Microsoft IL) or CIL (Common IL).</span></span>

## <a name="jit"></a><span data-ttu-id="ed2f2-180">JIT</span><span class="sxs-lookup"><span data-stu-id="ed2f2-180">JIT</span></span>

<span data-ttu-id="ed2f2-181">实时编译器。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-181">Just-in-time compiler.</span></span>

<span data-ttu-id="ed2f2-182">与 [AOT](#aot) 类似，此编译器将 [IL](#il) 转换为处理器可理解的计算机代码。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-182">Similar to [AOT](#aot), this compiler translates [IL](#il) to machine code that the processor understands.</span></span> <span data-ttu-id="ed2f2-183">与 AOT 不同，JIT 编译在需要运行代码的同一台计算机上按需执行。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-183">Unlike AOT, JIT compilation happens on demand and is performed on the same machine that the code needs to run on.</span></span> <span data-ttu-id="ed2f2-184">由于 JIT 编译在应用程序的执行过程中发生，因此编译时是运行时的一部分。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-184">Since JIT compilation occurs during execution of the application, compile time is part of the run time.</span></span> <span data-ttu-id="ed2f2-185">因此，JIT 编译器需要平衡优化代码所花费的时间与生成代码时可节约的时间。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-185">Thus, JIT compilers have to balance time spent optimizing code against the savings that the resulting code can produce.</span></span> <span data-ttu-id="ed2f2-186">但 JIT 知道实际硬件，这样开发人员就无需提供不同的实现。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-186">But a JIT knows the actual hardware and can free developers from having to ship different implementations.</span></span>

## <a name="implementation-of-net"></a><span data-ttu-id="ed2f2-187">.NET 实现</span><span class="sxs-lookup"><span data-stu-id="ed2f2-187">implementation of .NET</span></span>

<span data-ttu-id="ed2f2-188">.NET 的实现包括以下项：</span><span class="sxs-lookup"><span data-stu-id="ed2f2-188">An implementation of .NET includes the following:</span></span>

- <span data-ttu-id="ed2f2-189">一个或多个运行时。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-189">One or more runtimes.</span></span> <span data-ttu-id="ed2f2-190">示例：CLR、CoreCLR、CoreRT。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-190">Examples: CLR, CoreCLR, CoreRT.</span></span>
- <span data-ttu-id="ed2f2-191">实现 .NET Standard 的某版本并且可能包含其他 API 的类库。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-191">A class library that implements a version of the .NET Standard and may include additional APIs.</span></span> <span data-ttu-id="ed2f2-192">示例：.NET Framework 基类库、.NET Core 基类库。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-192">Examples: .NET Framework Base Class Library, .NET Core Base Class Library.</span></span>
- <span data-ttu-id="ed2f2-193">可选择包含一个或多个应用程序框架。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-193">Optionally, one or more application frameworks.</span></span> <span data-ttu-id="ed2f2-194">示例： ASP.NET、Windows 窗体和 WPF 包含在 .NET Framework 中。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-194">Examples: ASP.NET, Windows Forms, and WPF are included in the .NET Framework.</span></span>
- <span data-ttu-id="ed2f2-195">可包含开发工具。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-195">Optionally, development tools.</span></span> <span data-ttu-id="ed2f2-196">某些开发工具在多个实现之间共享。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-196">Some development tools are shared among multiple implementations.</span></span>

<span data-ttu-id="ed2f2-197">.NET 实现的示例：</span><span class="sxs-lookup"><span data-stu-id="ed2f2-197">Examples of .NET implementations:</span></span>

- [<span data-ttu-id="ed2f2-198">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="ed2f2-198">.NET Framework</span></span>](#net-framework)
- [<span data-ttu-id="ed2f2-199">.NET Core</span><span class="sxs-lookup"><span data-stu-id="ed2f2-199">.NET Core</span></span>](#net-core)
- [<span data-ttu-id="ed2f2-200">通用 Windows 平台 (UWP)</span><span class="sxs-lookup"><span data-stu-id="ed2f2-200">Universal Windows Platform (UWP)</span></span>](#uwp)

## <a name="library"></a><span data-ttu-id="ed2f2-201">库</span><span class="sxs-lookup"><span data-stu-id="ed2f2-201">library</span></span>

<span data-ttu-id="ed2f2-202">可由应用或其他库调用的 API 集合。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-202">A collection of APIs that can be called by apps or other libraries.</span></span> <span data-ttu-id="ed2f2-203">.NET 库由一个或多个[程序集](#assembly)组成。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-203">A .NET library is composed of one or more [assemblies](#assembly).</span></span>

<span data-ttu-id="ed2f2-204">词库和[框架](#framework)通常作同义词使用。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-204">The words library and [framework](#framework) are often used synonymously.</span></span>

## <a name="metapackage"></a><span data-ttu-id="ed2f2-205">元包</span><span class="sxs-lookup"><span data-stu-id="ed2f2-205">metapackage</span></span>

<span data-ttu-id="ed2f2-206">一个 NuGet 包，没有自己的库，而只是一个依赖项列表。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-206">A NuGet package that has no library of its own but is only a list of dependencies.</span></span> <span data-ttu-id="ed2f2-207">所含包可选择建立目标框架的 API。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-207">The included packages can optionally establish the API for a target framework.</span></span>

<span data-ttu-id="ed2f2-208">请参阅[包、元包和框架](../core/packages.md)</span><span class="sxs-lookup"><span data-stu-id="ed2f2-208">See [Packages, Metapackages and Frameworks](../core/packages.md)</span></span>

## <a name="mono"></a><span data-ttu-id="ed2f2-209">Mono</span><span class="sxs-lookup"><span data-stu-id="ed2f2-209">Mono</span></span>

<span data-ttu-id="ed2f2-210">Mono 是主要在需要小型运行时使用的开放源、[跨平台](#cross-platform) .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-210">Mono is an open source, [cross-platform](#cross-platform) .NET implementation that is mainly used when a small runtime is required.</span></span> <span data-ttu-id="ed2f2-211">它是运行时，在 Android、Mac、iOS、tvOS 和 watchOS 上为 Xamarin 应用程序提供技术支持，主要针对内存占用少的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-211">It is the runtime that powers Xamarin applications on Android, Mac, iOS, tvOS and watchOS and is focused primarily on apps that require a small footprint.</span></span>

<span data-ttu-id="ed2f2-212">它支持所有当前已发布的 .NET Standard 版本。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-212">It supports all of the currently published .NET Standard versions.</span></span>

<span data-ttu-id="ed2f2-213">以前，Mono 实现更大的 .NET Framework API 并模拟一些 Unix 上最常用的功能。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-213">Historically, Mono implemented the larger API of the .NET Framework and emulated some of the most popular capabilities on Unix.</span></span> <span data-ttu-id="ed2f2-214">有时使用它运行依赖 Unix 上的这些功能的 .NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-214">It is sometimes used to run .NET applications that rely on those capabilities on Unix.</span></span>

<span data-ttu-id="ed2f2-215">Mono 通常与实时编译器一起使用，但它也提供在 iOS 之类的平台使用的完整静态编译器（预先编译）。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-215">Mono is typically used with a just-in-time compiler, but it also features a full static compiler (ahead-of-time compilation) that is used on platforms like iOS.</span></span>

<span data-ttu-id="ed2f2-216">若要了解有关 Mono 的详细信息，请参阅 [Mono 文档](https://www.mono-project.com/docs/)。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-216">To learn more about Mono, see the [Mono documentation](https://www.mono-project.com/docs/).</span></span>

## <a name="net"></a><span data-ttu-id="ed2f2-217">.NET</span><span class="sxs-lookup"><span data-stu-id="ed2f2-217">.NET</span></span>

<span data-ttu-id="ed2f2-218">[.NET Standard](#net-standard) 和所有 [.NET 实现](#implementation-of-net)及工作负荷的涵盖性术语。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-218">The umbrella term for [.NET Standard](#net-standard) and all [.NET implementations](#implementation-of-net) and workloads.</span></span> <span data-ttu-id="ed2f2-219">始终采用大写形式，请勿使用“.Net”。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-219">Always capitalized, never ".Net".</span></span>

<span data-ttu-id="ed2f2-220">请参阅 [.NET 指南](index.md)</span><span class="sxs-lookup"><span data-stu-id="ed2f2-220">See the [.NET Guide](index.md)</span></span>

## <a name="net-core"></a><span data-ttu-id="ed2f2-221">.NET Core</span><span class="sxs-lookup"><span data-stu-id="ed2f2-221">.NET Core</span></span> 

<span data-ttu-id="ed2f2-222">一种跨平台、高性能的开放源 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-222">A cross-platform, high-performance, open source implementation of .NET.</span></span> <span data-ttu-id="ed2f2-223">包括 Core 公共语言运行时 (CoreCLR)、Core AOT 运行时（正在开发的 CoreRT）、Core 基类库和 Core SDK。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-223">Includes the Core Common Language Runtime (CoreCLR), the Core AOT Runtime (CoreRT, in development), the Core Base Class Library, and the Core SDK.</span></span>

<span data-ttu-id="ed2f2-224">请参阅 [.NET Core](../core/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-224">See [.NET Core](../core/index.md).</span></span>

## <a name="net-core-cli"></a><span data-ttu-id="ed2f2-225">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="ed2f2-225">.NET Core CLI</span></span>

<span data-ttu-id="ed2f2-226">用于开发 .NET Core 应用程序的跨平台工具链。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-226">A cross-platform toolchain for developing .NET Core applications.</span></span>

<span data-ttu-id="ed2f2-227">请参阅 [.NET Core 命令行接口 (CLI) 工具](../core/tools/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-227">See [.NET Core command-line interface (CLI) tools](../core/tools/index.md).</span></span>

## <a name="net-core-sdk"></a><span data-ttu-id="ed2f2-228">.NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="ed2f2-228">.NET Core SDK</span></span>

<span data-ttu-id="ed2f2-229">一组库和工具，开发人员可用其创建 .NET Core 应用程序和库。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-229">A set of libraries and tools that allow developers to create .NET Core applications and libraries.</span></span> <span data-ttu-id="ed2f2-230">包括用于生成应用的 [.NET Core CLI](#net-core-cli)、用于生成和运行应用的 .NET Core 库以及运行 CLI 命令和运行应用程序的 dotnet 可执行文件 (dotnet.exe)。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-230">Includes the [.NET Core CLI](#net-core-cli) for building apps, .NET Core libraries and runtime for building and running apps, and the dotnet executable (*dotnet.exe*) that runs CLI commands and runs applications.</span></span>

<span data-ttu-id="ed2f2-231">请参阅 [.NET Core SDK 概述](../core/sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-231">See [.NET Core SDK Overview](../core/sdk.md).</span></span>

## <a name="net-framework"></a><span data-ttu-id="ed2f2-232">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="ed2f2-232">.NET Framework</span></span>

<span data-ttu-id="ed2f2-233">仅在 Windows 上运行的 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-233">An implementation of .NET that runs only on Windows.</span></span> <span data-ttu-id="ed2f2-234">包括公共语言运行时 (CLR)、基类库和 ASP.NET、Windows 窗体和 WPF 之类的应用程序框架库。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-234">Includes the Common Language Runtime (CLR), the Base Class Library, and application framework libraries such as ASP.NET, Windows Forms, and WPF.</span></span>

<span data-ttu-id="ed2f2-235">请查阅 [.NET Framework 指南](../framework/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-235">See [.NET Framework Guide](../framework/index.md).</span></span>

## <a name="net-native"></a><span data-ttu-id="ed2f2-236">.NET Native</span><span class="sxs-lookup"><span data-stu-id="ed2f2-236">.NET Native</span></span>

<span data-ttu-id="ed2f2-237">编译器工具链，可预先 (AOT) 生成，而非实时 (JIT) 生成本机代码。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-237">A compiler tool chain that produces native code ahead-of-time (AOT), as opposed to just-in-time (JIT).</span></span>

<span data-ttu-id="ed2f2-238">编译采用与 C++ 编译器和链接器类似的工作方式在开发人员计算机上进行。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-238">Compilation happens on the developer's machine similar to the way a C++ compiler and linker works.</span></span> <span data-ttu-id="ed2f2-239">它删除了未使用的代码，留出更多时间进行优化。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-239">It removes unused code and spends more time optimizing it.</span></span> <span data-ttu-id="ed2f2-240">它从库中提取代码，将它们合并到可执行文件中。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-240">It extracts code from libraries and merges them into the executable.</span></span> <span data-ttu-id="ed2f2-241">结果是表示整个应用的单个模块。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-241">The result is a single module that represents the entire app.</span></span>

<span data-ttu-id="ed2f2-242">UWP 是 .NET Native 支持的首个应用程序框架。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-242">UWP was the first application framework supported by .NET Native.</span></span> <span data-ttu-id="ed2f2-243">现在，我们支持为 Windows、macOS 和 Linux 生成本机控制台应用。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-243">Now, we support building native console apps for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="ed2f2-244">请参阅 [.NET Native 和 CoreRT 简介](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span><span class="sxs-lookup"><span data-stu-id="ed2f2-244">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="net-standard"></a><span data-ttu-id="ed2f2-245">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="ed2f2-245">.NET Standard</span></span>

<span data-ttu-id="ed2f2-246">在每个 .NET 实现中都可用的 .NET API 正式规范。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-246">A formal specification of .NET APIs that are available in each .NET implementation.</span></span>

<span data-ttu-id="ed2f2-247">.NET Standard 规范有时被称为文档中的库。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-247">The .NET Standard specification is sometimes called a library in the documentation.</span></span> <span data-ttu-id="ed2f2-248">由于库不仅包括规范（接口），还包括 API 实现，所以会误将 .NET Standard 称为“库”。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-248">Because a library includes API implementations, not only specifications (interfaces), it's misleading to call .NET Standard a "library."</span></span> <span data-ttu-id="ed2f2-249">我们计划从本文档中去除该用法，引用 .NET Standard 元包 (`NETStandard.Library`) 的名称除外。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-249">We plan to eliminate that usage from the documentation, except in reference to the name of the .NET Standard metapackage (`NETStandard.Library`).</span></span>

<span data-ttu-id="ed2f2-250">请参阅 [.NET Standard](net-standard.md)。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-250">See [.NET Standard](net-standard.md).</span></span>

## <a name="ngen"></a><span data-ttu-id="ed2f2-251">NGEN</span><span class="sxs-lookup"><span data-stu-id="ed2f2-251">NGEN</span></span>

<span data-ttu-id="ed2f2-252">本机（映像）生成。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-252">Native (image) generation.</span></span>

<span data-ttu-id="ed2f2-253">可将此方法视为永久性 JIT 编译器。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-253">You can think of this technology as a persistent JIT compiler.</span></span> <span data-ttu-id="ed2f2-254">它通常在执行代码的计算机上编译该代码，但通常在安装时进行编译。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-254">It usually compiles code on the machine where the code is executed, but compilation typically occurs at install time.</span></span>

## <a name="package"></a><span data-ttu-id="ed2f2-255">包</span><span class="sxs-lookup"><span data-stu-id="ed2f2-255">package</span></span>

<span data-ttu-id="ed2f2-256">NuGet 包 &mdash; 或只是一个包 &mdash; 是一个 .zip 文件，其中具有一个或多个名称相同的程序集以及作者姓名等其他元数据。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-256">A NuGet package &mdash; or just a package &mdash; is a *.zip* file with one or more assemblies of the same name along with additional metadata such as the author name.</span></span>

<span data-ttu-id="ed2f2-257">.zip 文件的扩展名为 .nupkg，且可以包含在多个目标框架和版本中使用的资产（如 .dll 文件和 .xml 文件）。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-257">The *.zip* file has a *.nupkg* extension and may contain assets, such as *.dll* files and *.xml* files, for use with multiple target frameworks and versions.</span></span> <span data-ttu-id="ed2f2-258">在应用或库中安装时，会根据应用或库指定的目标框架选择相应的资产。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-258">When installed in an app or library, the appropriate assets are selected based on the target framework specified by the app or library.</span></span> <span data-ttu-id="ed2f2-259">定义接口的资产位于 ref 文件夹，而定义实现的资产位于 lib文件夹。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-259">The assets that define the interface are in the *ref* folder, and the assets that define the implementation are in the *lib* folder.</span></span>

## <a name="platform"></a><span data-ttu-id="ed2f2-260">平台</span><span class="sxs-lookup"><span data-stu-id="ed2f2-260">platform</span></span>

<span data-ttu-id="ed2f2-261">操作系统以及运行它的硬件，例如 Windows、macOS、Linux、iOS 和 Android。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-261">An operating system and the hardware it runs on, such as Windows, macOS, Linux, iOS, and Android.</span></span>

<span data-ttu-id="ed2f2-262">下面是在句子中使用的示例：</span><span class="sxs-lookup"><span data-stu-id="ed2f2-262">Here are examples of usage in sentences:</span></span>

- <span data-ttu-id="ed2f2-263">“.NET Core 是一个跨平台 .NET 实现。”</span><span class="sxs-lookup"><span data-stu-id="ed2f2-263">".NET Core is a cross-platform implementation of .NET."</span></span> 
- <span data-ttu-id="ed2f2-264">“PCL 配置文件代表 Microsoft 平台，而 .NET Standard 与平台无关。”</span><span class="sxs-lookup"><span data-stu-id="ed2f2-264">"PCL profiles represent Microsoft platforms, while the .NET Standard is agnostic to platform."</span></span>

<span data-ttu-id="ed2f2-265">.NET 文档经常使用“.NET 平台”表示一个 .NET 实现或包括所有实现的 .NET 堆栈。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-265">The .NET documentation frequently uses ".NET platform" to mean either an implementation of .NET or the .NET stack including all implementations.</span></span> <span data-ttu-id="ed2f2-266">这两种用法往往会与主（OS/硬件）含义混淆，因此我们计划从文档中去除这些用法。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-266">Both of these usages tend to get confused with the primary (OS/hardware) meaning, so we plan to eliminate these usages from the documentation.</span></span>

## <a name="runtime"></a><span data-ttu-id="ed2f2-267">Runtime — 运行时</span><span class="sxs-lookup"><span data-stu-id="ed2f2-267">runtime</span></span>

<span data-ttu-id="ed2f2-268">用于托管程序的执行环境。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-268">The execution environment for a managed program.</span></span>

<span data-ttu-id="ed2f2-269">OS 属于运行时环境，但不属于 .NET 运行时。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-269">The OS is part of the runtime environment but is not part of the .NET runtime.</span></span> <span data-ttu-id="ed2f2-270">下面是 .NET 运行时的一些示例：</span><span class="sxs-lookup"><span data-stu-id="ed2f2-270">Here are some examples of .NET runtimes:</span></span>

- <span data-ttu-id="ed2f2-271">公共语言运行时 (CLR)</span><span class="sxs-lookup"><span data-stu-id="ed2f2-271">Common Language Runtime (CLR)</span></span>
- <span data-ttu-id="ed2f2-272">Core 公共语言运行时 (CoreCLR)</span><span class="sxs-lookup"><span data-stu-id="ed2f2-272">Core Common Language Runtime (CoreCLR)</span></span>
- <span data-ttu-id="ed2f2-273">.NET Native（适用于 UWP）</span><span class="sxs-lookup"><span data-stu-id="ed2f2-273">.NET Native (for UWP)</span></span>
- <span data-ttu-id="ed2f2-274">Mono 运行时</span><span class="sxs-lookup"><span data-stu-id="ed2f2-274">Mono runtime</span></span>

<span data-ttu-id="ed2f2-275">.NET 文档有时使用“运行时”表示 .NET 的实现。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-275">The .NET documentation sometimes uses "runtime" to mean an implementation of .NET.</span></span> <span data-ttu-id="ed2f2-276">例如，在以下句子中应使用“实现”替换“运行时”：</span><span class="sxs-lookup"><span data-stu-id="ed2f2-276">For example, in the following sentences "runtime" should be replaced with "implementation":</span></span>

- <span data-ttu-id="ed2f2-277">“各种 .NET 运行时实现特定版本的 .NET Standard。”</span><span class="sxs-lookup"><span data-stu-id="ed2f2-277">"The various .NET runtimes implement specific versions of .NET Standard."</span></span>
- <span data-ttu-id="ed2f2-278">“计划在多个运行时上运行的库应将此框架作为目标。”</span><span class="sxs-lookup"><span data-stu-id="ed2f2-278">"Libraries that are intended to run on multiple runtimes should target this framework."</span></span> <span data-ttu-id="ed2f2-279">（参阅 .NET Standard）</span><span class="sxs-lookup"><span data-stu-id="ed2f2-279">(referring to .NET Standard)</span></span>
- <span data-ttu-id="ed2f2-280">“各种 .NET 运行时实现特定版本的 .NET Standard。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-280">"The various .NET runtimes implement specific versions of .NET Standard.</span></span> <span data-ttu-id="ed2f2-281">…</span><span class="sxs-lookup"><span data-stu-id="ed2f2-281">…</span></span> <span data-ttu-id="ed2f2-282">每个 .NET 运行时版本都将会公布它所支持的最高 .NET Standard 版本...”</span><span class="sxs-lookup"><span data-stu-id="ed2f2-282">Each .NET runtime version advertises the highest .NET Standard version it supports …"</span></span>

<span data-ttu-id="ed2f2-283">我们计划消除此不一致的用法。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-283">We plan to eliminate this inconsistent usage.</span></span> 

## <a name="stack"></a><span data-ttu-id="ed2f2-284">堆栈</span><span class="sxs-lookup"><span data-stu-id="ed2f2-284">stack</span></span>

<span data-ttu-id="ed2f2-285">一组编程方法，一起用于生成并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-285">A set of programming technologies that are used together to build and run applications.</span></span>

<span data-ttu-id="ed2f2-286">“.NET 堆栈”指 .NET Standard 和所有 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-286">"The .NET stack" refers to the .NET Standard and all .NET implementations.</span></span> <span data-ttu-id="ed2f2-287">短语“一个 .NET 堆栈”可能指一种 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-287">The phrase "a .NET stack" may refer to one implementation of .NET.</span></span> 

## <a name="target-framework"></a><span data-ttu-id="ed2f2-288">Target Framework — 目标 Framework</span><span class="sxs-lookup"><span data-stu-id="ed2f2-288">target framework</span></span>

<span data-ttu-id="ed2f2-289">.NET 应用或库依赖的 API 集合。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-289">The collection of APIs that a .NET app or library relies on.</span></span>

<span data-ttu-id="ed2f2-290">应用或库可将某版本的 .NET Standard（例如 .NET Standard 2.0）作为目标，这是所有 .NET 实现中一组标准化 API 的规范。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-290">An app or library can target a version of .NET Standard (for example, .NET Standard 2.0), which is specification for a standardized set of APIs across all .NET implementations.</span></span> <span data-ttu-id="ed2f2-291">应用或库还能以特定 .NET 的某版本实现为目标，这样便可获得特定于实现的 API 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-291">An app or library can also target a version of a specific .NET implementation, in which case it gets access to implementation-specific APIs.</span></span> <span data-ttu-id="ed2f2-292">例如，面向 Xamarin.iOS 的应用有权访问 Xamarin 提供的 iOS API 包装器。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-292">For example, an app that targets Xamarin.iOS gets access to Xamarin-provided iOS API wrappers.</span></span>

<span data-ttu-id="ed2f2-293">对于某些目标框架（例如 .NET Framework），可用 API 由 .NET 实现在系统上安装的程序集定义，其中可能包括应用程序框架 API（例如 ASP.NET、WinForms）。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-293">For some target frameworks (for example, the .NET Framework) the available APIs are defined by the assemblies that a .NET implementation installs on a system, which may include application framework APIs (for example, ASP.NET, WinForms).</span></span> <span data-ttu-id="ed2f2-294">对于基于包的目标框架（例如 .NET Standard 和 .NET Core），框架 API 由安装在应用或库中的包定义。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-294">For package-based target frameworks (such as .NET Standard and .NET Core), the framework APIs are defined by the packages installed in the app or library.</span></span> <span data-ttu-id="ed2f2-295">在这种情况下，目标框架隐式指定一个元包，该元包引用一起构成框架的所有包。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-295">In that case, the target framework implicitly specifies a metapackage that references all the packages that together make up the framework.</span></span>

<span data-ttu-id="ed2f2-296">请参阅[目标框架](frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-296">See [Target Frameworks](frameworks.md).</span></span>

## <a name="tfm"></a><span data-ttu-id="ed2f2-297">TFM</span><span class="sxs-lookup"><span data-stu-id="ed2f2-297">TFM</span></span>

<span data-ttu-id="ed2f2-298">目标框架名字对象。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-298">Target framework moniker.</span></span>

<span data-ttu-id="ed2f2-299">一个标准化令牌格式，用于指定 .NET 应用或库的目标框架。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-299">A standardized token format for specifying the target framework of a .NET app or library.</span></span> <span data-ttu-id="ed2f2-300">目标框架通常由短名称（如 `net462`）引用。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-300">Target frameworks are typically referenced by a short name, such as `net462`.</span></span> <span data-ttu-id="ed2f2-301">存在长格式的 TFM（如 .NETFramework,Version=4.6.2），但通常不用来指定目标框架。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-301">Long-form TFMs (such as .NETFramework,Version=4.6.2) exist but are not generally used to specify a target framework.</span></span>

<span data-ttu-id="ed2f2-302">请参阅[目标框架](frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-302">See [Target Frameworks](frameworks.md).</span></span>

## <a name="uwp"></a><span data-ttu-id="ed2f2-303">UWP</span><span class="sxs-lookup"><span data-stu-id="ed2f2-303">UWP</span></span>

<span data-ttu-id="ed2f2-304">通用 Windows 平台。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-304">Universal Windows Platform.</span></span>

<span data-ttu-id="ed2f2-305">用于为物联网 (IoT) 生成新式触控 Windows 应用程序和软件的 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-305">An implementation of .NET that is used for building modern, touch-enabled Windows applications and software for the Internet of Things (IoT).</span></span> <span data-ttu-id="ed2f2-306">它旨在统一可能想要以其为目标的不同类型的设备，包括电脑、平板电脑、平板手机、电话，甚至 Xbox。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-306">It's designed to unify the different types of devices that you may want to target, including PCs, tablets, phablets, phones, and even the Xbox.</span></span> <span data-ttu-id="ed2f2-307">UWP 提供许多服务，如集中式应用商店、执行环境 (AppContainer) 和一组 Windows API（用于代替 Win32 (WinRT)）。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-307">UWP provides many services, such as a centralized app store, an execution environment (AppContainer), and a set of Windows APIs to use instead of Win32 (WinRT).</span></span> <span data-ttu-id="ed2f2-308">应用可采用 C++、C#、VB.NET 和 JavaScript 编写。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-308">Apps can be written in C++, C#, VB.NET, and JavaScript.</span></span> <span data-ttu-id="ed2f2-309">使用 C# 和 VB.NET 时，.NET API 由 .NET Core 提供。</span><span class="sxs-lookup"><span data-stu-id="ed2f2-309">When using C# and VB.NET, the .NET APIs are provided by .NET Core.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed2f2-310">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed2f2-310">See also</span></span>

- [<span data-ttu-id="ed2f2-311">.NET 指南</span><span class="sxs-lookup"><span data-stu-id="ed2f2-311">.NET Guide</span></span>](index.md)  
- [<span data-ttu-id="ed2f2-312">.NET Framework 指南</span><span class="sxs-lookup"><span data-stu-id="ed2f2-312">.NET Framework Guide</span></span>](../framework/index.md)  
- [<span data-ttu-id="ed2f2-313">.NET Core</span><span class="sxs-lookup"><span data-stu-id="ed2f2-313">.NET Core</span></span>](../core/index.md)  
- [<span data-ttu-id="ed2f2-314">ASP.NET 概述</span><span class="sxs-lookup"><span data-stu-id="ed2f2-314">ASP.NET Overview</span></span>](/aspnet/index#pivot=aspnet)  
- [<span data-ttu-id="ed2f2-315"> 概述</span><span class="sxs-lookup"><span data-stu-id="ed2f2-315">ASP.NET Core Overview</span></span>](/aspnet/index#pivot=core)  
