---
title: 使用 .NET Native 编译引用
ms.date: 03/30/2017
helpviewer_keywords:
- native compilation
- .NET and native code
- compilation with .NET Native
- .NET Native
- C# and native compilation
ms.assetid: 47cd5648-9469-4b1d-804c-43cc04384045
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28b09bf07d831747be0006ffe1f1d8c5ac5171ce
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2019
ms.locfileid: "66052645"
---
# <a name="compiling-apps-with-net-native"></a><span data-ttu-id="f40ba-102">使用 .NET Native 编译引用</span><span class="sxs-lookup"><span data-stu-id="f40ba-102">Compiling Apps with .NET Native</span></span>
<span data-ttu-id="f40ba-103">.NET native 是 Visual Studio 2015 或更高版本包含了用于构建和部署 Windows 应用的预编译技术。</span><span class="sxs-lookup"><span data-stu-id="f40ba-103">.NET Native is a precompilation technology for building and deploying Windows apps that is included with Visual Studio 2015 and later versions.</span></span> <span data-ttu-id="f40ba-104">它自动将以托管代码（C# 或 Visual Basic）编写并面向 .NET Framework 和 Windows 10 的发布版本的应用编译为本机代码。</span><span class="sxs-lookup"><span data-stu-id="f40ba-104">It automatically compiles the release version of apps that are written in managed code (C# or Visual Basic) and that target the .NET Framework and Windows 10 to native code.</span></span>  
  
 <span data-ttu-id="f40ba-105">通常，定位于 .NET Framework 的应用会被编译到中间语言 (IL) 中。</span><span class="sxs-lookup"><span data-stu-id="f40ba-105">Typically, apps that target the .NET Framework are compiled to intermediate language (IL).</span></span> <span data-ttu-id="f40ba-106">在运行时间，及时生成 (JIT) 编译器将 IL 翻译为本机代码。</span><span class="sxs-lookup"><span data-stu-id="f40ba-106">At run time, the just-in-time (JIT) compiler translates the IL to native code.</span></span> <span data-ttu-id="f40ba-107">与此相反，.NET Native 编译为本机代码直接的 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="f40ba-107">In contrast, .NET Native compiles Windows apps directly to native code.</span></span> <span data-ttu-id="f40ba-108">对于开发者，这意味着：</span><span class="sxs-lookup"><span data-stu-id="f40ba-108">For developers, this means:</span></span>  
  
- <span data-ttu-id="f40ba-109">您的应用程序功能的本机代码的性能。</span><span class="sxs-lookup"><span data-stu-id="f40ba-109">Your apps feature the performance of native code.</span></span> <span data-ttu-id="f40ba-110">通常情况下，性能将优于第一次编译到 IL，然后编译为本机代码的 JIT 编译器的代码。</span><span class="sxs-lookup"><span data-stu-id="f40ba-110">Usually, performance will be superior to code that is first compiled to IL and then compiled to native code by the JIT compiler.</span></span> 
  
- <span data-ttu-id="f40ba-111">你可以继续用 C# 或 Visual Basic 进行编程。</span><span class="sxs-lookup"><span data-stu-id="f40ba-111">You can continue to program in C# or Visual Basic.</span></span>  
  
- <span data-ttu-id="f40ba-112">你可以继续使用 .NET Framework 提供的资源，包括类库、自动内存管理、垃圾回收和异常处理。</span><span class="sxs-lookup"><span data-stu-id="f40ba-112">You can continue to take advantage of the resources provided by the .NET Framework, including its class library, automatic memory management and garbage collection, and exception handling.</span></span>  
  
 <span data-ttu-id="f40ba-113">对于您的应用程序的用户，.NET Native 提供以下优势：</span><span class="sxs-lookup"><span data-stu-id="f40ba-113">For users of your apps, .NET Native offers these advantages:</span></span>  
  
- <span data-ttu-id="f40ba-114">对于大多数应用程序和方案的更快地执行时间。</span><span class="sxs-lookup"><span data-stu-id="f40ba-114">Faster execution times for the majority of apps and scenarios.</span></span>
  
- <span data-ttu-id="f40ba-115">对于大多数应用程序和方案更快的启动时间。</span><span class="sxs-lookup"><span data-stu-id="f40ba-115">Faster startup times for the majority of apps and scenarios.</span></span> 
  
- <span data-ttu-id="f40ba-116">部署和更新的低成本。</span><span class="sxs-lookup"><span data-stu-id="f40ba-116">Low deployment and update costs.</span></span>  
  
- <span data-ttu-id="f40ba-117">优化应用内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="f40ba-117">Optimized app memory usage.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="f40ba-118">对于绝大多数应用程序和方案，.NET Native 提供明显更快的启动时间和优异的性能与应用程序编译为 IL 或 NGEN 映像相比。</span><span class="sxs-lookup"><span data-stu-id="f40ba-118">For the vast majority of apps and scenarios, .NET Native offers significantly faster startup times and superior performance when compared to an app compiled to IL or to an NGEN image.</span></span> <span data-ttu-id="f40ba-119">但是，您的结果可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="f40ba-119">However, your results may vary.</span></span> <span data-ttu-id="f40ba-120">若要确保您的应用程序具有受益的.NET Native 的性能增强功能，应将与您的应用程序的非.NET Native 版本其性能进行比较。</span><span class="sxs-lookup"><span data-stu-id="f40ba-120">To ensure that your app has benefited from the performance enhancements of .NET Native, you should compare its performance with that of the non-.NET Native version of your app.</span></span> <span data-ttu-id="f40ba-121">有关详细信息，请参阅[性能会话概述](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview)。</span><span class="sxs-lookup"><span data-stu-id="f40ba-121">For more information, see [Performance Session Overview](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span></span>
 
<span data-ttu-id="f40ba-122">但.NET Native 涉及多个编译为本机代码。</span><span class="sxs-lookup"><span data-stu-id="f40ba-122">But .NET Native involves more than a compilation to native code.</span></span> <span data-ttu-id="f40ba-123">它会改变 .NET Framework 应用的创建和执行方式。</span><span class="sxs-lookup"><span data-stu-id="f40ba-123">It transforms the way that .NET Framework apps are built and executed.</span></span> <span data-ttu-id="f40ba-124">具体而言：</span><span class="sxs-lookup"><span data-stu-id="f40ba-124">In particular:</span></span>  
  
- <span data-ttu-id="f40ba-125">在预编译期间，所需的 .NET Framework 部分会静态连接到你的应用。</span><span class="sxs-lookup"><span data-stu-id="f40ba-125">During precompilation, required portions of the .NET Framework are statically linked into your app.</span></span> <span data-ttu-id="f40ba-126">这允许应用同 .NET Framework 的应用本地库一起运行，并且允许编译器执行全局分析，从而提供性能优势。</span><span class="sxs-lookup"><span data-stu-id="f40ba-126">This allows the app to run with app-local libraries of the .NET Framework, and the compiler to perform global analysis to deliver performance wins.</span></span> <span data-ttu-id="f40ba-127">因此，应用甚至在 .NET Framework 更新后会启动得更快。</span><span class="sxs-lookup"><span data-stu-id="f40ba-127">As a result, apps launch consistently faster even after .NET Framework updates.</span></span>  
  
- <span data-ttu-id="f40ba-128">.NET Native 运行时优化来动态预编程，并且在大多数情况下提供优异的性能。</span><span class="sxs-lookup"><span data-stu-id="f40ba-128">The .NET Native runtime is optimized for static precompilation and in the vast majority of cases offers superior performance.</span></span> <span data-ttu-id="f40ba-129">同时，它保留了开发者认为非常高效的核心反射特性。</span><span class="sxs-lookup"><span data-stu-id="f40ba-129">At the same time, it retains the core reflection features that developers find so productive.</span></span>  
  
- <span data-ttu-id="f40ba-130">.NET native 使用相同的后端为C++编译器，针对静态预编译方案进行了优化。</span><span class="sxs-lookup"><span data-stu-id="f40ba-130">.NET Native uses the same back end as the C++ compiler, which is optimized for static precompilation scenarios.</span></span>  
  
 <span data-ttu-id="f40ba-131">.NET native 是带来的性能优势C++给托管代码开发人员，因为它使用与相同或类似的工具C++实质上，此表中所示。</span><span class="sxs-lookup"><span data-stu-id="f40ba-131">.NET Native is able to bring the performance benefits of C++ to managed code developers because it uses the same or similar tools as C++ under the hood, as shown in this table.</span></span>  
  
||<span data-ttu-id="f40ba-132">.NET Native</span><span class="sxs-lookup"><span data-stu-id="f40ba-132">.NET Native</span></span>|<span data-ttu-id="f40ba-133">C++</span><span class="sxs-lookup"><span data-stu-id="f40ba-133">C++</span></span>|  
|-|----------------------------------------------------------------|-----------|  
|<span data-ttu-id="f40ba-134">库</span><span class="sxs-lookup"><span data-stu-id="f40ba-134">Libraries</span></span>|<span data-ttu-id="f40ba-135">.NET Framework + Windows 运行时</span><span class="sxs-lookup"><span data-stu-id="f40ba-135">The .NET Framework + Windows Runtime</span></span>|<span data-ttu-id="f40ba-136">Win32 + Windows 运行时</span><span class="sxs-lookup"><span data-stu-id="f40ba-136">Win32 + Windows Runtime</span></span>|  
|<span data-ttu-id="f40ba-137">编译器</span><span class="sxs-lookup"><span data-stu-id="f40ba-137">Compiler</span></span>|<span data-ttu-id="f40ba-138">UTC 优化编译器</span><span class="sxs-lookup"><span data-stu-id="f40ba-138">UTC optimizing compiler</span></span>|<span data-ttu-id="f40ba-139">UTC 优化编译器</span><span class="sxs-lookup"><span data-stu-id="f40ba-139">UTC optimizing compiler</span></span>|  
|<span data-ttu-id="f40ba-140">已部署</span><span class="sxs-lookup"><span data-stu-id="f40ba-140">Deployed</span></span>|<span data-ttu-id="f40ba-141">随时可以运行的二进制代码</span><span class="sxs-lookup"><span data-stu-id="f40ba-141">Ready-to-run binaries</span></span>|<span data-ttu-id="f40ba-142">随时可以运行的二进制代码 (ASM)</span><span class="sxs-lookup"><span data-stu-id="f40ba-142">Ready-to-run binaries (ASM)</span></span>|  
|<span data-ttu-id="f40ba-143">运行时</span><span class="sxs-lookup"><span data-stu-id="f40ba-143">Runtime</span></span>|<span data-ttu-id="f40ba-144">MRT.dll（最短 CLR 运行时）</span><span class="sxs-lookup"><span data-stu-id="f40ba-144">MRT.dll (Minimal CLR Runtime)</span></span>|<span data-ttu-id="f40ba-145">CRT.dll（C 运行时）</span><span class="sxs-lookup"><span data-stu-id="f40ba-145">CRT.dll (C Runtime)</span></span>|  
  
 <span data-ttu-id="f40ba-146">对于适用于 Windows 10 的 Windows 应用，可将应用程序包（.appx 文件）中的 .NET 本机代码编译二进制文件上载到 Windows 应用商店。</span><span class="sxs-lookup"><span data-stu-id="f40ba-146">For Windows apps for Windows 10, you upload .NET Native Code Compilation binaries in app packages (.appx files) to the Windows Store.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f40ba-147">本节内容</span><span class="sxs-lookup"><span data-stu-id="f40ba-147">In This Section</span></span>  
 <span data-ttu-id="f40ba-148">要查看有关带有 .NET Native 代码编译的应用开发的信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="f40ba-148">For more information about developing apps with .NET Native Code Compilation, see these topics:</span></span>  
  
- [<span data-ttu-id="f40ba-149">开始使用.NET Native 代码编译：开发者经验介绍</span><span class="sxs-lookup"><span data-stu-id="f40ba-149">Getting Started with .NET Native Code Compilation: The Developer Experience Walkthrough</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
  
- <span data-ttu-id="f40ba-150">[.NET native 和编译：](../../../docs/framework/net-native/net-native-and-compilation.md)如何.NET Native 编译为本机代码项目。</span><span class="sxs-lookup"><span data-stu-id="f40ba-150">[.NET Native and Compilation:](../../../docs/framework/net-native/net-native-and-compilation.md) How .NET Native compiles your project to native code.</span></span>  
  
- [<span data-ttu-id="f40ba-151">反射和 .NET Native</span><span class="sxs-lookup"><span data-stu-id="f40ba-151">Reflection and .NET Native</span></span>](../../../docs/framework/net-native/reflection-and-net-native.md)  
  
    - [<span data-ttu-id="f40ba-152">依赖反射的 API</span><span class="sxs-lookup"><span data-stu-id="f40ba-152">APIs That Rely on Reflection</span></span>](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)  
  
    - [<span data-ttu-id="f40ba-153">反射 API 引用</span><span class="sxs-lookup"><span data-stu-id="f40ba-153">Reflection API Reference</span></span>](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
    - [<span data-ttu-id="f40ba-154">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="f40ba-154">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
- [<span data-ttu-id="f40ba-155">Serialization and Metadata（序列化和元数据）</span><span class="sxs-lookup"><span data-stu-id="f40ba-155">Serialization and Metadata</span></span>](../../../docs/framework/net-native/serialization-and-metadata.md)  
  
- [<span data-ttu-id="f40ba-156">将 Windows 应用商店应用迁移到 .NET Native</span><span class="sxs-lookup"><span data-stu-id="f40ba-156">Migrating Your Windows Store App to .NET Native</span></span>](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)  
  
- [<span data-ttu-id="f40ba-157">.NET Native 一般疑难解答</span><span class="sxs-lookup"><span data-stu-id="f40ba-157">.NET Native General Troubleshooting</span></span>](../../../docs/framework/net-native/net-native-general-troubleshooting.md)
