---
title: "使用 .NET Native 编译引用"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- native compilation
- .NET and native code
- compilation with .NET Native
- .NET Native
- C# and native compilation
ms.assetid: 47cd5648-9469-4b1d-804c-43cc04384045
caps.latest.revision: "27"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a79744d99571fa1428da1fade8f63c4c80ae7b6c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="compiling-apps-with-net-native"></a><span data-ttu-id="83f48-102">使用 .NET Native 编译引用</span><span class="sxs-lookup"><span data-stu-id="83f48-102">Compiling Apps with .NET Native</span></span>
[!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="83f48-103">是包含在 Visual Studio 2015 和更高版本的预编译技术用于生成和部署 Windows 应用程序。</span><span class="sxs-lookup"><span data-stu-id="83f48-103"> is a precompilation technology for building and deploying Windows apps that is included with Visual Studio 2015 and later versions.</span></span> <span data-ttu-id="83f48-104">它自动将以托管代码（C# 或 Visual Basic）编写并面向 .NET Framework 和 Windows 10 的发布版本的应用编译为本机代码。</span><span class="sxs-lookup"><span data-stu-id="83f48-104">It automatically compiles the release version of apps that are written in managed code (C# or Visual Basic) and that target the .NET Framework and Windows 10 to native code.</span></span>  
  
 <span data-ttu-id="83f48-105">通常，定位于 .NET Framework 的应用会被编译到中间语言 (IL) 中。</span><span class="sxs-lookup"><span data-stu-id="83f48-105">Typically, apps that target the .NET Framework are compiled to intermediate language (IL).</span></span> <span data-ttu-id="83f48-106">在运行时间，及时生成 (JIT) 编译器将 IL 翻译为本机代码。</span><span class="sxs-lookup"><span data-stu-id="83f48-106">At run time, the just-in-time (JIT) compiler translates the IL to native code.</span></span> <span data-ttu-id="83f48-107">与此相反， [!INCLUDE[net_native](../../../includes/net-native-md.md)] 将 Windows 商店应用直接编译为本机代码。</span><span class="sxs-lookup"><span data-stu-id="83f48-107">In contrast, [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiles Windows apps directly to native code.</span></span> <span data-ttu-id="83f48-108">对于开发者，这意味着：</span><span class="sxs-lookup"><span data-stu-id="83f48-108">For developers, this means:</span></span>  
  
-   <span data-ttu-id="83f48-109">你的应用程序功能的本机代码的性能。</span><span class="sxs-lookup"><span data-stu-id="83f48-109">Your apps feature the performance of native code.</span></span> <span data-ttu-id="83f48-110">通常情况下，性能将优于第一次编译到 IL，然后由 JIT 编译器编译为本机代码的代码。</span><span class="sxs-lookup"><span data-stu-id="83f48-110">Usually, performance will be superior to code that is first compiled to IL and then compiled to native code by the JIT compiler.</span></span> 
  
-   <span data-ttu-id="83f48-111">你可以继续用 C# 或 Visual Basic 进行编程。</span><span class="sxs-lookup"><span data-stu-id="83f48-111">You can continue to program in C# or Visual Basic.</span></span>  
  
-   <span data-ttu-id="83f48-112">你可以继续使用 .NET Framework 提供的资源，包括类库、自动内存管理、垃圾回收和异常处理。</span><span class="sxs-lookup"><span data-stu-id="83f48-112">You can continue to take advantage of the resources provided by the .NET Framework, including its class library, automatic memory management and garbage collection, and exception handling.</span></span>  
  
 <span data-ttu-id="83f48-113">对于你的应用用户， [!INCLUDE[net_native](../../../includes/net-native-md.md)] 提供以下优势：</span><span class="sxs-lookup"><span data-stu-id="83f48-113">For users of your apps, [!INCLUDE[net_native](../../../includes/net-native-md.md)] offers these advantages:</span></span>  
  
-   <span data-ttu-id="83f48-114">对于大多数应用程序和方案的更快的执行时间。</span><span class="sxs-lookup"><span data-stu-id="83f48-114">Faster execution times for the majority of apps and scenarios.</span></span>
  
-   <span data-ttu-id="83f48-115">对于大多数应用程序和方案的更快的启动时间。</span><span class="sxs-lookup"><span data-stu-id="83f48-115">Faster startup times for the majority of apps and scenarios.</span></span> 
  
-   <span data-ttu-id="83f48-116">部署和更新的低成本。</span><span class="sxs-lookup"><span data-stu-id="83f48-116">Low deployment and update costs.</span></span>  
  
-   <span data-ttu-id="83f48-117">优化应用内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="83f48-117">Optimized app memory usage.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="83f48-118">对于大多数应用程序和方案，.NET 本机提供显著更快的启动时间和相比编译到 IL 或 NGEN 映像的应用时的优越性能。</span><span class="sxs-lookup"><span data-stu-id="83f48-118">For the vast majority of apps and scenarios, .NET Native offers significantly faster startup times and superior performance when compared to an app compiled to IL or to an NGEN image.</span></span> <span data-ttu-id="83f48-119">但是，你的结果可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="83f48-119">However, your results may vary.</span></span> <span data-ttu-id="83f48-120">若要确保你的应用程序具有受益的.NET Native 的性能增强功能，您应比较其性能，与你的应用程序的非.NET 本机版本。</span><span class="sxs-lookup"><span data-stu-id="83f48-120">To ensure that your app has benefited from the performance enhancements of .NET Native, you should compare its performance with that of the non-.NET Native version of your app.</span></span> <span data-ttu-id="83f48-121">有关详细信息，请参阅[性能会话概述](https:/docs.microsoft.com/visualstudio/profiling/performance-session-overview)。</span><span class="sxs-lookup"><span data-stu-id="83f48-121">For more information, see [Performance Session Overview](https:/docs.microsoft.com/visualstudio/profiling/performance-session-overview).</span></span>
 
<span data-ttu-id="83f48-122">但是 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 涉及的本机代码编译不止一个。</span><span class="sxs-lookup"><span data-stu-id="83f48-122">But [!INCLUDE[net_native](../../../includes/net-native-md.md)] involves more than a compilation to native code.</span></span> <span data-ttu-id="83f48-123">它会改变 .NET Framework 应用的创建和执行方式。</span><span class="sxs-lookup"><span data-stu-id="83f48-123">It transforms the way that .NET Framework apps are built and executed.</span></span> <span data-ttu-id="83f48-124">具体而言：</span><span class="sxs-lookup"><span data-stu-id="83f48-124">In particular:</span></span>  
  
-   <span data-ttu-id="83f48-125">在预编译期间，所需的 .NET Framework 部分会静态连接到你的应用。</span><span class="sxs-lookup"><span data-stu-id="83f48-125">During precompilation, required portions of the .NET Framework are statically linked into your app.</span></span> <span data-ttu-id="83f48-126">这允许应用同 .NET Framework 的应用本地库一起运行，并且允许编译器执行全局分析，从而提供性能优势。</span><span class="sxs-lookup"><span data-stu-id="83f48-126">This allows the app to run with app-local libraries of the .NET Framework, and the compiler to perform global analysis to deliver performance wins.</span></span> <span data-ttu-id="83f48-127">因此，应用甚至在 .NET Framework 更新后会启动得更快。</span><span class="sxs-lookup"><span data-stu-id="83f48-127">As a result, apps launch consistently faster even after .NET Framework updates.</span></span>  
  
-   <span data-ttu-id="83f48-128">[!INCLUDE[net_native](../../../includes/net-native-md.md)]运行时优化用于动态预编程，并且在大多数情况下提供优异的性能。</span><span class="sxs-lookup"><span data-stu-id="83f48-128">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] runtime is optimized for static precompilation and in the vast majority of cases offers superior performance.</span></span> <span data-ttu-id="83f48-129">同时，它保留了开发者认为非常高效的核心反射特性。</span><span class="sxs-lookup"><span data-stu-id="83f48-129">At the same time, it retains the core reflection features that developers find so productive.</span></span>  
  
-   [!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="83f48-130"> 使用了同 C++ 编译器（已为静态预编译方案进行过优化）相同的后端。</span><span class="sxs-lookup"><span data-stu-id="83f48-130"> uses the same back end as the C++ compiler, which is optimized for static precompilation scenarios.</span></span>  
  
 <span data-ttu-id="83f48-131">如该表所示，[!INCLUDE[net_native](../../../includes/net-native-md.md)] 能够将 C++ 的性能优势带给托管代码开发者，因为它使用同高级选项下的 C++ 相同或相似的工具。</span><span class="sxs-lookup"><span data-stu-id="83f48-131">[!INCLUDE[net_native](../../../includes/net-native-md.md)] is able to bring the performance benefits of C++ to managed code developers because it uses the same or similar tools as C++ under the hood, as shown in this table.</span></span>  
  
||[!INCLUDE[net_native](../../../includes/net-native-md.md)]|<span data-ttu-id="83f48-132">C++</span><span class="sxs-lookup"><span data-stu-id="83f48-132">C++</span></span>|  
|-|----------------------------------------------------------------|-----------|  
|<span data-ttu-id="83f48-133">库</span><span class="sxs-lookup"><span data-stu-id="83f48-133">Libraries</span></span>|<span data-ttu-id="83f48-134">.NET Framework + Windows 运行时</span><span class="sxs-lookup"><span data-stu-id="83f48-134">The .NET Framework + Windows Runtime</span></span>|<span data-ttu-id="83f48-135">Win32 + Windows 运行时</span><span class="sxs-lookup"><span data-stu-id="83f48-135">Win32 + Windows Runtime</span></span>|  
|<span data-ttu-id="83f48-136">编译器</span><span class="sxs-lookup"><span data-stu-id="83f48-136">Compiler</span></span>|<span data-ttu-id="83f48-137">UTC 优化编译器</span><span class="sxs-lookup"><span data-stu-id="83f48-137">UTC optimizing compiler</span></span>|<span data-ttu-id="83f48-138">UTC 优化编译器</span><span class="sxs-lookup"><span data-stu-id="83f48-138">UTC optimizing compiler</span></span>|  
|<span data-ttu-id="83f48-139">已部署</span><span class="sxs-lookup"><span data-stu-id="83f48-139">Deployed</span></span>|<span data-ttu-id="83f48-140">随时可以运行的二进制代码</span><span class="sxs-lookup"><span data-stu-id="83f48-140">Ready-to-run binaries</span></span>|<span data-ttu-id="83f48-141">随时可以运行的二进制代码 (ASM)</span><span class="sxs-lookup"><span data-stu-id="83f48-141">Ready-to-run binaries (ASM)</span></span>|  
|<span data-ttu-id="83f48-142">运行时</span><span class="sxs-lookup"><span data-stu-id="83f48-142">Runtime</span></span>|<span data-ttu-id="83f48-143">MRT.dll（最短 CLR 运行时）</span><span class="sxs-lookup"><span data-stu-id="83f48-143">MRT.dll (Minimal CLR Runtime)</span></span>|<span data-ttu-id="83f48-144">CRT.dll（C 运行时）</span><span class="sxs-lookup"><span data-stu-id="83f48-144">CRT.dll (C Runtime)</span></span>|  
  
 <span data-ttu-id="83f48-145">对于适用于 Windows 10 的 Windows 应用，可将应用程序包（.appx 文件）中的 .NET 本机代码编译二进制文件上载到 Windows 应用商店。</span><span class="sxs-lookup"><span data-stu-id="83f48-145">For Windows apps for Windows 10, you upload .NET Native Code Compilation binaries in app packages (.appx files) to the Windows Store.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="83f48-146">本节内容</span><span class="sxs-lookup"><span data-stu-id="83f48-146">In This Section</span></span>  
 <span data-ttu-id="83f48-147">要查看有关带有 .NET Native 代码编译的应用开发的信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="83f48-147">For more information about developing apps with .NET Native Code Compilation, see these topics:</span></span>  
  
-   [<span data-ttu-id="83f48-148">.NET Native 代码编译入门：开发者经验介绍</span><span class="sxs-lookup"><span data-stu-id="83f48-148">Getting Started with .NET Native Code Compilation: The Developer Experience Walkthrough</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
  
-   <span data-ttu-id="83f48-149">[.NET 本机和编译：](../../../docs/framework/net-native/net-native-and-compilation.md) .NET 本机如何将你的项目编译为本机代码。</span><span class="sxs-lookup"><span data-stu-id="83f48-149">[.NET Native and Compilation:](../../../docs/framework/net-native/net-native-and-compilation.md) How .NET Native compiles your project to native code.</span></span>  
  
-   [<span data-ttu-id="83f48-150">反射和 .NET Native</span><span class="sxs-lookup"><span data-stu-id="83f48-150">Reflection and .NET Native</span></span>](../../../docs/framework/net-native/reflection-and-net-native.md)  
  
    -   [<span data-ttu-id="83f48-151">依赖反射的 API</span><span class="sxs-lookup"><span data-stu-id="83f48-151">APIs That Rely on Reflection</span></span>](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)  
  
    -   [<span data-ttu-id="83f48-152">反射 API 引用</span><span class="sxs-lookup"><span data-stu-id="83f48-152">Reflection API Reference</span></span>](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
    -   [<span data-ttu-id="83f48-153">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="83f48-153">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
-   [<span data-ttu-id="83f48-154">Serialization and Metadata（序列化和元数据）</span><span class="sxs-lookup"><span data-stu-id="83f48-154">Serialization and Metadata</span></span>](../../../docs/framework/net-native/serialization-and-metadata.md)  
  
-   [<span data-ttu-id="83f48-155">将 Windows 应用商店应用迁移到 .NET Native</span><span class="sxs-lookup"><span data-stu-id="83f48-155">Migrating Your Windows Store App to .NET Native</span></span>](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)  
  
-   [<span data-ttu-id="83f48-156">.NET Native 一般疑难解答</span><span class="sxs-lookup"><span data-stu-id="83f48-156">.NET Native General Troubleshooting</span></span>](../../../docs/framework/net-native/net-native-general-troubleshooting.md)  
  
## <a name="see-also"></a><span data-ttu-id="83f48-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83f48-157">See Also</span></span>  
 [<span data-ttu-id="83f48-158">.NET Native 常见问题</span><span class="sxs-lookup"><span data-stu-id="83f48-158">.NET Native FAQ</span></span>](http://msdn.microsoft.com/vstudio/dn642499.aspx)
