---
title: "使用 .NET Native 编译引用"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- native compilation
- .NET and native code
- compilation with .NET Native
- .NET Native
- C# and native compilation
ms.assetid: 47cd5648-9469-4b1d-804c-43cc04384045
caps.latest.revision: 27
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 76645ae43ce6754ffdf505729ec1198785a71561
ms.contentlocale: zh-cn
ms.lasthandoff: 09/07/2017

---
# <a name="compiling-apps-with-net-native"></a><span data-ttu-id="f90c4-102">使用 .NET Native 编译引用</span><span class="sxs-lookup"><span data-stu-id="f90c4-102">Compiling Apps with .NET Native</span></span>
[!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="f90c4-103"> 是一项预编译技术，用于构建和部署 [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)]附带的 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="f90c4-103"> is a precompilation technology for building and deploying Windows apps that is included with [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)].</span></span> <span data-ttu-id="f90c4-104">它自动将以托管代码（C# 或 Visual Basic）编写并面向 .NET Framework 和 Windows 10 的发布版本的应用编译为本机代码。</span><span class="sxs-lookup"><span data-stu-id="f90c4-104">It automatically compiles the release version of apps that are written in managed code (C# or Visual Basic) and that target the .NET Framework and Windows 10 to native code.</span></span>  
  
 <span data-ttu-id="f90c4-105">通常，定位于 .NET Framework 的应用会被编译到中间语言 (IL) 中。</span><span class="sxs-lookup"><span data-stu-id="f90c4-105">Typically, apps that target the .NET Framework are compiled to intermediate language (IL).</span></span> <span data-ttu-id="f90c4-106">在运行时间，及时生成 (JIT) 编译器将 IL 翻译为本机代码。</span><span class="sxs-lookup"><span data-stu-id="f90c4-106">At run time, the just-in-time (JIT) compiler translates the IL to native code.</span></span> <span data-ttu-id="f90c4-107">与此相反， [!INCLUDE[net_native](../../../includes/net-native-md.md)] 将 Windows 商店应用直接编译为本机代码。</span><span class="sxs-lookup"><span data-stu-id="f90c4-107">In contrast, [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiles Windows apps directly to native code.</span></span> <span data-ttu-id="f90c4-108">对于开发者，这意味着：</span><span class="sxs-lookup"><span data-stu-id="f90c4-108">For developers, this means:</span></span>  
  
-   <span data-ttu-id="f90c4-109">你的应用将提供本机代码的优越性能。</span><span class="sxs-lookup"><span data-stu-id="f90c4-109">Your apps will provide the superior performance of native code.</span></span>  
  
-   <span data-ttu-id="f90c4-110">你可以继续用 C# 或 Visual Basic 进行编程。</span><span class="sxs-lookup"><span data-stu-id="f90c4-110">You can continue to program in C# or Visual Basic.</span></span>  
  
-   <span data-ttu-id="f90c4-111">你可以继续使用 .NET Framework 提供的资源，包括类库、自动内存管理、垃圾回收和异常处理。</span><span class="sxs-lookup"><span data-stu-id="f90c4-111">You can continue to take advantage of the resources provided by the .NET Framework, including its class library, automatic memory management and garbage collection, and exception handling.</span></span>  
  
 <span data-ttu-id="f90c4-112">对于你的应用用户， [!INCLUDE[net_native](../../../includes/net-native-md.md)] 提供以下优势：</span><span class="sxs-lookup"><span data-stu-id="f90c4-112">For users of your apps, [!INCLUDE[net_native](../../../includes/net-native-md.md)] offers these advantages:</span></span>  
  
-   <span data-ttu-id="f90c4-113">快速的执行时间</span><span class="sxs-lookup"><span data-stu-id="f90c4-113">Fast execution times</span></span>  
  
-   <span data-ttu-id="f90c4-114">持续快速的启动时间</span><span class="sxs-lookup"><span data-stu-id="f90c4-114">Consistently speedy startup times</span></span>  
  
-   <span data-ttu-id="f90c4-115">较低的部署和更新成本</span><span class="sxs-lookup"><span data-stu-id="f90c4-115">Low deployment and update costs</span></span>  
  
-   <span data-ttu-id="f90c4-116">优化过的应用内存使用</span><span class="sxs-lookup"><span data-stu-id="f90c4-116">Optimized app memory usage</span></span>  
  
 <span data-ttu-id="f90c4-117">但是 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 涉及的本机代码编译不止一个。</span><span class="sxs-lookup"><span data-stu-id="f90c4-117">But [!INCLUDE[net_native](../../../includes/net-native-md.md)] involves more than a compilation to native code.</span></span> <span data-ttu-id="f90c4-118">它会改变 .NET Framework 应用的创建和执行方式。</span><span class="sxs-lookup"><span data-stu-id="f90c4-118">It transforms the way that .NET Framework apps are built and executed.</span></span> <span data-ttu-id="f90c4-119">具体而言：</span><span class="sxs-lookup"><span data-stu-id="f90c4-119">In particular:</span></span>  
  
-   <span data-ttu-id="f90c4-120">在预编译期间，所需的 .NET Framework 部分会静态连接到你的应用。</span><span class="sxs-lookup"><span data-stu-id="f90c4-120">During precompilation, required portions of the .NET Framework are statically linked into your app.</span></span> <span data-ttu-id="f90c4-121">这允许应用同 .NET Framework 的应用本地库一起运行，并且允许编译器执行全局分析，从而提供性能优势。</span><span class="sxs-lookup"><span data-stu-id="f90c4-121">This allows the app to run with app-local libraries of the .NET Framework, and the compiler to perform global analysis to deliver performance wins.</span></span> <span data-ttu-id="f90c4-122">因此，应用甚至在 .NET Framework 更新后会启动得更快。</span><span class="sxs-lookup"><span data-stu-id="f90c4-122">As a result, apps launch consistently faster even after .NET Framework updates.</span></span>  
  
-   <span data-ttu-id="f90c4-123">[!INCLUDE[net_native](../../../includes/net-native-md.md)] 运行时得到了优化用于动态预编程，因此能够提供优越性能。</span><span class="sxs-lookup"><span data-stu-id="f90c4-123">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] runtime is optimized for static precompilation and thus is able to offer superior performance.</span></span> <span data-ttu-id="f90c4-124">同时，它保留了开发者认为非常高效的核心反射特性。</span><span class="sxs-lookup"><span data-stu-id="f90c4-124">At the same time, it retains the core reflection features that developers find so productive.</span></span>  
  
-   [!INCLUDE[net_native](../../../includes/net-native-md.md)]<span data-ttu-id="f90c4-125"> 使用了同 C++ 编译器（已为静态预编译方案进行过优化）相同的后端。</span><span class="sxs-lookup"><span data-stu-id="f90c4-125"> uses the same back end as the C++ compiler, which is optimized for static precompilation scenarios.</span></span>  
  
 <span data-ttu-id="f90c4-126">如该表所示，[!INCLUDE[net_native](../../../includes/net-native-md.md)] 能够将 C++ 的性能优势带给托管代码开发者，因为它使用同高级选项下的 C++ 相同或相似的工具。</span><span class="sxs-lookup"><span data-stu-id="f90c4-126">[!INCLUDE[net_native](../../../includes/net-native-md.md)] is able to bring the performance benefits of C++ to managed code developers because it uses the same or similar tools as C++ under the hood, as shown in this table.</span></span>  
  
||[!INCLUDE[net_native](../../../includes/net-native-md.md)]|<span data-ttu-id="f90c4-127">C++</span><span class="sxs-lookup"><span data-stu-id="f90c4-127">C++</span></span>|  
|-|----------------------------------------------------------------|-----------|  
|<span data-ttu-id="f90c4-128">库</span><span class="sxs-lookup"><span data-stu-id="f90c4-128">Libraries</span></span>|<span data-ttu-id="f90c4-129">.NET Framework + Windows 运行时</span><span class="sxs-lookup"><span data-stu-id="f90c4-129">The .NET Framework + Windows Runtime</span></span>|<span data-ttu-id="f90c4-130">Win32 + Windows 运行时</span><span class="sxs-lookup"><span data-stu-id="f90c4-130">Win32 + Windows Runtime</span></span>|  
|<span data-ttu-id="f90c4-131">编译器</span><span class="sxs-lookup"><span data-stu-id="f90c4-131">Compiler</span></span>|<span data-ttu-id="f90c4-132">UTC 优化编译器</span><span class="sxs-lookup"><span data-stu-id="f90c4-132">UTC optimizing compiler</span></span>|<span data-ttu-id="f90c4-133">UTC 优化编译器</span><span class="sxs-lookup"><span data-stu-id="f90c4-133">UTC optimizing compiler</span></span>|  
|<span data-ttu-id="f90c4-134">已部署</span><span class="sxs-lookup"><span data-stu-id="f90c4-134">Deployed</span></span>|<span data-ttu-id="f90c4-135">随时可以运行的二进制代码</span><span class="sxs-lookup"><span data-stu-id="f90c4-135">Ready-to-run binaries</span></span>|<span data-ttu-id="f90c4-136">随时可以运行的二进制代码 (ASM)</span><span class="sxs-lookup"><span data-stu-id="f90c4-136">Ready-to-run binaries (ASM)</span></span>|  
|<span data-ttu-id="f90c4-137">运行时</span><span class="sxs-lookup"><span data-stu-id="f90c4-137">Runtime</span></span>|<span data-ttu-id="f90c4-138">MRT.dll（最短 CLR 运行时）</span><span class="sxs-lookup"><span data-stu-id="f90c4-138">MRT.dll (Minimal CLR Runtime)</span></span>|<span data-ttu-id="f90c4-139">CRT.dll（C 运行时）</span><span class="sxs-lookup"><span data-stu-id="f90c4-139">CRT.dll (C Runtime)</span></span>|  
  
 <span data-ttu-id="f90c4-140">对于适用于 Windows 10 的 Windows 应用，可将应用程序包（.appx 文件）中的 .NET 本机代码编译二进制文件上载到 Windows 应用商店。</span><span class="sxs-lookup"><span data-stu-id="f90c4-140">For Windows apps for Windows 10, you upload .NET Native Code Compilation binaries in app packages (.appx files) to the Windows Store.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f90c4-141">本节内容</span><span class="sxs-lookup"><span data-stu-id="f90c4-141">In This Section</span></span>  
 <span data-ttu-id="f90c4-142">要查看有关带有 .NET Native 代码编译的应用开发的信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="f90c4-142">For more information about developing apps with .NET Native Code Compilation, see these topics:</span></span>  
  
-   [<span data-ttu-id="f90c4-143">.NET Native 代码编译入门：开发者经验介绍</span><span class="sxs-lookup"><span data-stu-id="f90c4-143">Getting Started with .NET Native Code Compilation: The Developer Experience Walkthrough</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
  
-   <span data-ttu-id="f90c4-144">[.NET 本机和编译：](../../../docs/framework/net-native/net-native-and-compilation.md) .NET 本机如何将你的项目编译为本机代码。</span><span class="sxs-lookup"><span data-stu-id="f90c4-144">[.NET Native and Compilation:](../../../docs/framework/net-native/net-native-and-compilation.md) How .NET Native compiles your project to native code.</span></span>  
  
-   [<span data-ttu-id="f90c4-145">反射和 .NET Native</span><span class="sxs-lookup"><span data-stu-id="f90c4-145">Reflection and .NET Native</span></span>](../../../docs/framework/net-native/reflection-and-net-native.md)  
  
    -   [<span data-ttu-id="f90c4-146">依赖反射的 API</span><span class="sxs-lookup"><span data-stu-id="f90c4-146">APIs That Rely on Reflection</span></span>](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)  
  
    -   [<span data-ttu-id="f90c4-147">反射 API 引用</span><span class="sxs-lookup"><span data-stu-id="f90c4-147">Reflection API Reference</span></span>](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
    -   [<span data-ttu-id="f90c4-148">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="f90c4-148">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
-   [<span data-ttu-id="f90c4-149">Serialization and Metadata（序列化和元数据）</span><span class="sxs-lookup"><span data-stu-id="f90c4-149">Serialization and Metadata</span></span>](../../../docs/framework/net-native/serialization-and-metadata.md)  
  
-   [<span data-ttu-id="f90c4-150">将 Windows 应用商店应用迁移到 .NET Native</span><span class="sxs-lookup"><span data-stu-id="f90c4-150">Migrating Your Windows Store App to .NET Native</span></span>](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)  
  
-   [<span data-ttu-id="f90c4-151">.NET Native 一般疑难解答</span><span class="sxs-lookup"><span data-stu-id="f90c4-151">.NET Native General Troubleshooting</span></span>](../../../docs/framework/net-native/net-native-general-troubleshooting.md)  
  
## <a name="see-also"></a><span data-ttu-id="f90c4-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f90c4-152">See Also</span></span>  
 [<span data-ttu-id="f90c4-153">.NET Native 常见问题</span><span class="sxs-lookup"><span data-stu-id="f90c4-153">.NET Native FAQ</span></span>](http://msdn.microsoft.com/vstudio/dn642499.aspx)

