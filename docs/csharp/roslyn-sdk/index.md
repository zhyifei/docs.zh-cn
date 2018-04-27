---
title: .NET Compiler Platform SDK (Roslyn API)
description: 了解如何使用 .NET Compiler Platform SDK（亦称为“Roslyn API”）来理解 .NET 代码、发现并修复错误。
keywords: roslyn, 分析器, 代码修补程序
author: billwagner
ms.author: wiwagn
ms.date: 10/10/2017
ms.topic: conceptual
ms.prod: .net
ms.devlang: devlang-csharp
ms.custom: mvc
ms.openlocfilehash: aad6b06748b02e2ea3003ca339d8a5a0b15583f8
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="the-net-compiler-platform-sdk"></a><span data-ttu-id="26d8e-104">.NET Compiler Platform SDK</span><span class="sxs-lookup"><span data-stu-id="26d8e-104">The .NET Compiler Platform SDK</span></span>

<span data-ttu-id="26d8e-105">编译器在验证代码语法和语义时生成应用代码的详细模型。</span><span class="sxs-lookup"><span data-stu-id="26d8e-105">Compilers build a detailed model of application code as they validate the syntax and semantics of that code.</span></span> <span data-ttu-id="26d8e-106">此模型可用于根据源代码生成可执行输出。</span><span class="sxs-lookup"><span data-stu-id="26d8e-106">They use this model to build the executable output from the source code.</span></span> <span data-ttu-id="26d8e-107">.NET Compiler Platform SDK 提供对此模型的访问权限。</span><span class="sxs-lookup"><span data-stu-id="26d8e-107">The .NET Compiler Platform SDK provides access to this model.</span></span> <span data-ttu-id="26d8e-108">我们越来越依赖 IntelliSense、重构、智能重命名、“查找所有引用”和“转到定义”等集成开发环境 (IDE) 功能来提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="26d8e-108">Increasingly, we rely on integrated development environment (IDE) features such as IntelliSense, refactoring, intelligent rename, "Find all references," and "Go to definition" to increase our productivity.</span></span> <span data-ttu-id="26d8e-109">我们依靠代码分析工具来提升代码质量，并依靠代码生成器来帮助构造应用。</span><span class="sxs-lookup"><span data-stu-id="26d8e-109">We rely on code analysis tools to improve our code quality, and code generators to aid in application construction.</span></span> <span data-ttu-id="26d8e-110">随着这些工具越来越智能化，它们需要越来越多地访问仅由编译器在处理应用代码时创建的模型。</span><span class="sxs-lookup"><span data-stu-id="26d8e-110">As these tools get smarter, they need access to more and more of the model that only compilers create as they process application code.</span></span> <span data-ttu-id="26d8e-111">这就是 Roslyn API 的核心任务所在：打开“黑匣”，让工具和最终用户能够共享编译器生成的大量代码相关信息。</span><span class="sxs-lookup"><span data-stu-id="26d8e-111">This is the core mission of the Roslyn APIs: opening up the black boxes and allowing tools and end users to share in the wealth of information compilers have about our code.</span></span>
<span data-ttu-id="26d8e-112">编译器通过 Roslyn 成为平台，即可以在工具和应用中执行代码相关任务的 API，而不是输入源代码并输出对象代码的不透明转换器。</span><span class="sxs-lookup"><span data-stu-id="26d8e-112">Instead of being opaque source-code-in and object-code-out translators, through Roslyn, compilers become platforms: APIs that you can use for code-related tasks in your tools and applications.</span></span>

## <a name="net-compiler-platform-sdk-concepts"></a><span data-ttu-id="26d8e-113">.NET Compiler Platform SDK 概念</span><span class="sxs-lookup"><span data-stu-id="26d8e-113">.NET Compiler Platform SDK concepts</span></span>

<span data-ttu-id="26d8e-114">.NET Compiler Platform SDK 极大地降低了创建以代码为中心的工具和应用的门槛。</span><span class="sxs-lookup"><span data-stu-id="26d8e-114">The .NET Compiler Platform SDK dramatically lowers the barrier to entry for creating code focused tools and applications.</span></span> <span data-ttu-id="26d8e-115">在元编程、代码生成和转换、C# 和 VB 语言的交互式使用以及在域专属语言中嵌入 C# 和 VB 等领域，它带来了许多创新机遇。</span><span class="sxs-lookup"><span data-stu-id="26d8e-115">It creates many opportunities for innovation in areas such as meta-programming, code generation and transformation, interactive use of the C# and VB languages, and embedding of C# and VB in domain specific languages.</span></span>

<span data-ttu-id="26d8e-116">使用 .NET Compiler Platform SDK，可以生成分析器和代码修补程序，从而发现和更正编码错误。</span><span class="sxs-lookup"><span data-stu-id="26d8e-116">The .NET Compiler Platform SDK enables you to build ***analyzers*** and ***code fixes*** that find and correct coding mistakes.</span></span> <span data-ttu-id="26d8e-117">分析器不仅理解代码的语法和结构，还能检测应更正的做法。</span><span class="sxs-lookup"><span data-stu-id="26d8e-117">***Analyzers*** understand the syntax and structure of code and detect practices that should be corrected.</span></span> <span data-ttu-id="26d8e-118">代码修补程序建议一处或多处修复，以修复分析器发现的编码错误。</span><span class="sxs-lookup"><span data-stu-id="26d8e-118">***Code fixes*** provide one or more suggested fixes for addressing coding mistakes found by analyzers.</span></span> <span data-ttu-id="26d8e-119">通常情况下，分析器和关联的代码修补程序一起打包在一个项目中。</span><span class="sxs-lookup"><span data-stu-id="26d8e-119">Typically, an analyzer and the associated code fixes are packaged together in a single project.</span></span> 

<span data-ttu-id="26d8e-120">分析器和代码修补程序通过静态分析来理解代码。</span><span class="sxs-lookup"><span data-stu-id="26d8e-120">Analyzers and code fixes use static analysis to understand code.</span></span> <span data-ttu-id="26d8e-121">它们既不运行代码，也未带来其他测试方面的好处。</span><span class="sxs-lookup"><span data-stu-id="26d8e-121">They do not run the code or provide other testing benefits.</span></span> <span data-ttu-id="26d8e-122">不过，它们可以指出哪些做法常常导致 bug 出现、代码不可维护或需要验证标准指南。</span><span class="sxs-lookup"><span data-stu-id="26d8e-122">They can, however, point out practices that often lead to bugs, unmaintanable code, or standard guideline validation.</span></span>

<span data-ttu-id="26d8e-123">.NET Compiler Platform SDK 提供了一组 API，可便于检查和理解 C# 或 Visual Basic 基准代码。</span><span class="sxs-lookup"><span data-stu-id="26d8e-123">The .NET Compiler Platform SDK provides a single set of APIs that enable you to examine and understand a C# or Visual Basic codebase.</span></span> <span data-ttu-id="26d8e-124">由于可以使用这一基准代码，因此能够利用 .NET Compiler Platform SDK 提供的语法和语义分析 API，更轻松地编写分析器和代码修补程序。</span><span class="sxs-lookup"><span data-stu-id="26d8e-124">Because you can use this single codebase, you can write analyzers and code fixes more easily by leveraging the syntactic and semantic analysis APIs provided by the .NET Compiler Platform SDK.</span></span> <span data-ttu-id="26d8e-125">从复制编译器完成的分析这项大型任务中解放出来后，便可以专注于执行更有针对性的任务，即发现和修复项目或库的常见编码错误。</span><span class="sxs-lookup"><span data-stu-id="26d8e-125">Freed from the large task of replicating the anaysis done by the compiler, you can concentrate on the more focused task of finding and fixing common coding errors for your project or library.</span></span>

<span data-ttu-id="26d8e-126">这带来的一个小小的好处是，分析器和代码修补程序较小，在 Visual Studio 中加载时占用的内存比为了理解项目中的代码而编写自己的基准代码占用的内存少得多。</span><span class="sxs-lookup"><span data-stu-id="26d8e-126">A smaller benefit is that your analyzers and code fixes are smaller and use much less memory when loaded in Visual Studio than they would if you wrote your own codebase to understand the code in a project.</span></span> <span data-ttu-id="26d8e-127">利用编译器和 Visual Studio 使用的相同类，可以创建自己的静态分析工具。</span><span class="sxs-lookup"><span data-stu-id="26d8e-127">By leveraging the same classes used by the compiler and Visual Studio, you can create your own static analysis tools.</span></span> <span data-ttu-id="26d8e-128">也就是说，团队可以使用分析器和代码修补程序，而不会对 IDE 的性能造成显著影响。</span><span class="sxs-lookup"><span data-stu-id="26d8e-128">This means your team can use analyzers and code fixes without a noticeable impact on the IDE's performance.</span></span>

<span data-ttu-id="26d8e-129">在下列三个主要方案中，需要编写分析器和代码修补程序：</span><span class="sxs-lookup"><span data-stu-id="26d8e-129">There are three main scenarios for writing analyzers and code fixes:</span></span>

1. [<span data-ttu-id="26d8e-130">*强制执行团队编码标准*</span><span class="sxs-lookup"><span data-stu-id="26d8e-130">*Enforce team coding standards*</span></span>](#enforce-team-coding-standards)
1. [<span data-ttu-id="26d8e-131">*提供库包方面的指导*</span><span class="sxs-lookup"><span data-stu-id="26d8e-131">*Provide guidance with library packages*</span></span>](#provide-guidance-with-library-packages)
1. [<span data-ttu-id="26d8e-132">*提供常规编码指南*</span><span class="sxs-lookup"><span data-stu-id="26d8e-132">*Provide general coding guidance*</span></span>](#provide-general-coding-guidance)

## <a name="enforce-team-coding-standards"></a><span data-ttu-id="26d8e-133">强制执行团队编码标准</span><span class="sxs-lookup"><span data-stu-id="26d8e-133">Enforce team coding standards</span></span>

<span data-ttu-id="26d8e-134">许多团队都有编码标准，通过由其他团队成员评审代码的形式强制执行。</span><span class="sxs-lookup"><span data-stu-id="26d8e-134">Many teams have coding standards that are enforced through code reviews with other team members.</span></span> <span data-ttu-id="26d8e-135">分析器和代码修补程序可以让这个过程更加高效。</span><span class="sxs-lookup"><span data-stu-id="26d8e-135">Analyzers and code fixes can make this process much more efficient.</span></span> <span data-ttu-id="26d8e-136">当开发人员与团队中的其他成员共享工作内容时，其他成员会执行代码评审。</span><span class="sxs-lookup"><span data-stu-id="26d8e-136">Code reviews happen when a developer shares their work with others on the team.</span></span> <span data-ttu-id="26d8e-137">在有任何注释前，开发人员一直都在完成新功能。</span><span class="sxs-lookup"><span data-stu-id="26d8e-137">The developer will have invested all the time needed to complete a new feature before getting any comments.</span></span> <span data-ttu-id="26d8e-138">开发人员不符合团队做法的习惯就会得到强化，时间可能长达几周之久。</span><span class="sxs-lookup"><span data-stu-id="26d8e-138">Weeks may go by while the developer reinforces habits that don't match the team's practices.</span></span>

<span data-ttu-id="26d8e-139">分析器在开发人员编写代码的同时运行。</span><span class="sxs-lookup"><span data-stu-id="26d8e-139">Analyzers run as a developer writes code.</span></span> <span data-ttu-id="26d8e-140">这样，开发人员就可以获得即时反馈，从而立即遵循相关指南。</span><span class="sxs-lookup"><span data-stu-id="26d8e-140">The developer gets immediate feedback that encourages following the guidance immediately.</span></span> <span data-ttu-id="26d8e-141">只要开始原型设计，开发人员就养成了编写符合标准的代码的习惯。</span><span class="sxs-lookup"><span data-stu-id="26d8e-141">The developer builds habits to write compliant code as soon as they begin prototyping.</span></span> <span data-ttu-id="26d8e-142">当功能可供人员评审时，所有标准指南就已强制执行。</span><span class="sxs-lookup"><span data-stu-id="26d8e-142">When the feature is ready for humans to review, all the standard guidance has been enforced.</span></span>

<span data-ttu-id="26d8e-143">团队可以生成分析器和代码修补程序，以发现违反团队编码做法的最常见做法。</span><span class="sxs-lookup"><span data-stu-id="26d8e-143">Teams can build analyzers and code fixes that look for the most common practices that violate team coding practices.</span></span> <span data-ttu-id="26d8e-144">这些分析器和代码修补程序可以安装到每个开发人员的计算机上，以强制执行标准。</span><span class="sxs-lookup"><span data-stu-id="26d8e-144">These can be installed on each developer's machine to enforce the standards.</span></span>

## <a name="provide-guidance-with-library-packages"></a><span data-ttu-id="26d8e-145">提供库包方面的指导</span><span class="sxs-lookup"><span data-stu-id="26d8e-145">Provide guidance with library packages</span></span>

<span data-ttu-id="26d8e-146">NuGet 上有大量适用于 .NET 开发人员的库。</span><span class="sxs-lookup"><span data-stu-id="26d8e-146">There are a wealth of libraries available for .NET developers on NuGet.</span></span>
<span data-ttu-id="26d8e-147">一些来自 Microsoft，一些来自第三方公司，另一些来自社区成员和志愿者。</span><span class="sxs-lookup"><span data-stu-id="26d8e-147">Some of these come from Microsoft, some from third-party companies, and others from community members and volunteers.</span></span> <span data-ttu-id="26d8e-148">如果开发人员可以成功使用这些库后，它们的采用率和评价就会有所提升。</span><span class="sxs-lookup"><span data-stu-id="26d8e-148">These libraries get more adoption and higher reviews when developers can succeed with those libraries.</span></span>

<span data-ttu-id="26d8e-149">除了提供文档之外，还可以提供分析程序和代码修补程序，用于发现和更正库的常见错误用法。</span><span class="sxs-lookup"><span data-stu-id="26d8e-149">In addition to providing documentation, you can provide analyzers and code fixes that find and correct common mis-uses of your library.</span></span> <span data-ttu-id="26d8e-150">这些即时更正有助于开发人员更快地成功使用库。</span><span class="sxs-lookup"><span data-stu-id="26d8e-150">These immediate corrections will help developers succeed more quickly.</span></span> 

<span data-ttu-id="26d8e-151">可以将分析器和代码修补程序与 NuGet 上的库一起打包。</span><span class="sxs-lookup"><span data-stu-id="26d8e-151">You can package analyzers and code fixes with your library on NuGet.</span></span> <span data-ttu-id="26d8e-152">在这种情况下，每个安装了 NuGet 包的开发人员都还将安装分析器包。</span><span class="sxs-lookup"><span data-stu-id="26d8e-152">In that scenario, every developer who installs your NuGet package will also install the analyzer package.</span></span> <span data-ttu-id="26d8e-153">所有使用库的开发人员都会立即从团队获得指导，即有关错误和建议更正做法的即时反馈。</span><span class="sxs-lookup"><span data-stu-id="26d8e-153">All developers using your library will immediately get guidance from your team in the form of immediate feedback on mistakes and suggested corrections.</span></span>

## <a name="provide-general-guidance"></a><span data-ttu-id="26d8e-154">提供常规指南</span><span class="sxs-lookup"><span data-stu-id="26d8e-154">Provide general guidance</span></span>

<span data-ttu-id="26d8e-155">.NET 开发人员社区已发现效果理想的体验模式和最好避免使用的模式。</span><span class="sxs-lookup"><span data-stu-id="26d8e-155">The .NET developer community has discovered through experience patterns that work well and patterns that are best avoided.</span></span> <span data-ttu-id="26d8e-156">一些社区成员已创建分析器来强制执行这些推荐模式。</span><span class="sxs-lookup"><span data-stu-id="26d8e-156">Several community members have created analyzers that enforce those recommended patterns.</span></span> <span data-ttu-id="26d8e-157">随着掌握的信息越来越多，新见解是无止境的。</span><span class="sxs-lookup"><span data-stu-id="26d8e-157">As we learn more, there is always room for new ideas.</span></span>

<span data-ttu-id="26d8e-158">这些分析器可以上传到 [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs) 中，并由开发人员使用 Visual Studio 进行下载。</span><span class="sxs-lookup"><span data-stu-id="26d8e-158">These analyzers can be uploaded to the [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs) and downloaded by developers using Visual Studio.</span></span> <span data-ttu-id="26d8e-159">语言和平台的新手可以快速了解公认做法，并尽早在 .NET 之旅中高效工作。</span><span class="sxs-lookup"><span data-stu-id="26d8e-159">Newcomers to the language and the platform learn accepted practices quickly and become productive earlier in their .NET journey.</span></span> <span data-ttu-id="26d8e-160">随着使用越来越广泛，这些做法就会被社区采用。</span><span class="sxs-lookup"><span data-stu-id="26d8e-160">As these become more widely used, the community adopts these practices.</span></span>

## <a name="next-steps"></a><span data-ttu-id="26d8e-161">后续步骤</span><span class="sxs-lookup"><span data-stu-id="26d8e-161">Next steps</span></span>

<span data-ttu-id="26d8e-162">.NET Compiler Platform SDK 包括用于代码生成、分析和重构的最新语言对象模型。</span><span class="sxs-lookup"><span data-stu-id="26d8e-162">The .NET Compiler Platform SDK includes the latest language object models for code generation, analysis, and refactoring.</span></span> <span data-ttu-id="26d8e-163">此部分从概念上概述了 .NET Compiler Platform SDK。</span><span class="sxs-lookup"><span data-stu-id="26d8e-163">This section provides a conceptual overview of the .NET Compiler Platform SDK.</span></span> <span data-ttu-id="26d8e-164">有关更多详细信息，可以参阅快速入门、示例和教程部分。</span><span class="sxs-lookup"><span data-stu-id="26d8e-164">Further details can be found in the quickstarts, samples and tutorials sections.</span></span>

<span data-ttu-id="26d8e-165">若要详细了解 .NET Compiler Platform SDK 概念，可以参阅下列四个主题：</span><span class="sxs-lookup"><span data-stu-id="26d8e-165">You can learn more about the concepts in the .NET Compiler Platform SDK in these four topics:</span></span>

 - [<span data-ttu-id="26d8e-166">使用语法可视化工具浏览代码</span><span class="sxs-lookup"><span data-stu-id="26d8e-166">Explore code with the syntax visualizer</span></span>](syntax-visualizer.md)
 - [<span data-ttu-id="26d8e-167">了解编译器 API 模型</span><span class="sxs-lookup"><span data-stu-id="26d8e-167">Understand the compiler API model</span></span>](compiler-api-model.md)
 - [<span data-ttu-id="26d8e-168">处理语法</span><span class="sxs-lookup"><span data-stu-id="26d8e-168">Work with syntax</span></span>](work-with-syntax.md)
 - [<span data-ttu-id="26d8e-169">处理语义</span><span class="sxs-lookup"><span data-stu-id="26d8e-169">Work with semantics</span></span>](work-with-semantics.md)
 - [<span data-ttu-id="26d8e-170">处理工作区</span><span class="sxs-lookup"><span data-stu-id="26d8e-170">Work with a workspace</span></span>](work-with-workspace.md)
 
<span data-ttu-id="26d8e-171">若要开始，需要安装 .NET 编译器平台 SDK：</span><span class="sxs-lookup"><span data-stu-id="26d8e-171">To get started, you'll need to install the **.NET Compiler Platform SDK**:</span></span>

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

<!--

Turn this on as more of the conceptual content is in place:
- Try the [Quickstarts](quickstart/index.md) to create your first tutorial.
- Experiment with one of the [Tutorials](tutorials/index.md).
- Explore the [Samples](samples/index.md) to see some simple analyzers.
- Read the [Concepts](concepts/index.md) to understand the ideas behind analyzers and code fixes.

-->
