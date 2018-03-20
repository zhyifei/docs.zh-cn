---
title: ".NET Compiler Platform SDK 概念和对象模型"
description: "此概述提供了高效使用 .NET 编译器 SDK 所需的背景。 介绍了 API 层、涉及的主要类型以及总体对象模型。"
author: billwagner
ms.author: wiwagn
ms.date: 10/10/2017
ms.topic: conceptual
ms.prod: .net
ms.devlang: devlang-csharp
ms.custom: mvc
ms.openlocfilehash: d230d334eba4e438635a4c70e8c1b5fc5075b065
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
# <a name="understand-the-net-compiler-platform-sdk-model"></a><span data-ttu-id="db22d-104">了解 .NET Compiler Platform SDK 模型</span><span class="sxs-lookup"><span data-stu-id="db22d-104">Understand the .NET Compiler Platform SDK model</span></span>

<span data-ttu-id="db22d-105">编译器按照结构化规则处理代码，这些规则通常不同于用户读取和理解代码的方式。</span><span class="sxs-lookup"><span data-stu-id="db22d-105">Compilers process the code you write following structured rules that often differ from the way humans read and understand code.</span></span> <span data-ttu-id="db22d-106">基本了解编译器使用的模型对于了解生成基于 Roslyn 的工具时使用的 API 至关重要。</span><span class="sxs-lookup"><span data-stu-id="db22d-106">A basic understanding of the model used by compilers is essential to understanding the APIs you use when building Roslyn-based tools.</span></span> 

## <a name="compiler-pipeline-functional-areas"></a><span data-ttu-id="db22d-107">编译器管道功能区域</span><span class="sxs-lookup"><span data-stu-id="db22d-107">Compiler pipeline functional areas</span></span>

<span data-ttu-id="db22d-108">.NET Compiler Platform SDK 通过提供镜像传统编译器管道的 API 层，作为使用者向用户公开 C# 和 Visual Basic 编译器的代码分析。</span><span class="sxs-lookup"><span data-stu-id="db22d-108">The .NET Compiler Platform SDK exposes the C# and Visual Basic compilers' code analysis to you as a consumer by providing an API layer that mirrors a traditional compiler pipeline.</span></span>

![编译器管道将源代码处理为对象代码的步骤](media/compiler-pipeline.png)

<span data-ttu-id="db22d-110">此管道的每个阶段都是一个单独的组件。</span><span class="sxs-lookup"><span data-stu-id="db22d-110">Each phase of this pipeline is a separate component.</span></span> <span data-ttu-id="db22d-111">首先，分析阶段标记化源文本，并将其分析为遵循语言语法的语法。</span><span class="sxs-lookup"><span data-stu-id="db22d-111">First, the parse phase tokenizes and parses source text into syntax that follows the language grammar.</span></span> <span data-ttu-id="db22d-112">随后，声明阶段分析源和导入的元数据，形成命名符号。</span><span class="sxs-lookup"><span data-stu-id="db22d-112">Second, the declaration phase analyzes source and imported metadata to form named symbols.</span></span> <span data-ttu-id="db22d-113">然后，绑定阶段将代码中的标识符与符号匹配。</span><span class="sxs-lookup"><span data-stu-id="db22d-113">Next, the bind phase matches identifiers in the code to symbols.</span></span> <span data-ttu-id="db22d-114">最后，发出阶段发出所有信息均由编译器生成的程序集。</span><span class="sxs-lookup"><span data-stu-id="db22d-114">Finally, the emit phase emits an assembly with all the information built up by the compiler.</span></span>

![编译器管道 API 提供对编译器管道中包含的每个步骤的访问权限](media/compiler-pipeline-api.png)

<span data-ttu-id="db22d-116">.NET Compiler Platform SDK 对应于每个阶段提供一个对象模型，该模型允许访问该阶段的信息。</span><span class="sxs-lookup"><span data-stu-id="db22d-116">Corresponding to each of those phases, the .NET Compiler Platform SDK exposes an object model that allows access to the information at that phase.</span></span> <span data-ttu-id="db22d-117">分析阶段公开一个语法树，声明阶段公开一个分层符号表，绑定阶段公开编译器语义分析的结果，发出阶段公开生成 IL 字节代码的 API。</span><span class="sxs-lookup"><span data-stu-id="db22d-117">The parsing phase exposes a syntax tree, the declaration phase exposes a hierarchical symbol table, the binding phase exposes the result of the compiler’s semantic analysis, and the emit phase is an API that produces IL byte codes.</span></span>

![编译器管道每个步骤的编译器 API 提供的语言服务](media/compiler-pipeline-lang-svc.png)

<span data-ttu-id="db22d-119">每个编译器将这些组件合并在一起，组成一个端到端整体。</span><span class="sxs-lookup"><span data-stu-id="db22d-119">Each compiler combines these components together as a single end-to-end whole.</span></span>

<span data-ttu-id="db22d-120">这些 API 与 Visual Studio 使用的 API 相同。</span><span class="sxs-lookup"><span data-stu-id="db22d-120">These APIs are the same ones used by Visual Studio.</span></span> <span data-ttu-id="db22d-121">例如，代码大纲和格式设置功能使用语法树，对象浏览器和导航功能使用符号表，重构和转到定义使用语义模型，编辑并继续使用所有这些信息，包括发出 API。</span><span class="sxs-lookup"><span data-stu-id="db22d-121">For instance, the code outlining and formatting features use the syntax trees, the Object Browser and navigation features use the symbol table, refactorings and Go to Definition use the semantic model, and Edit and Continue uses all of these, including the Emit API.</span></span> 

## <a name="api-layers"></a><span data-ttu-id="db22d-122">API 层</span><span class="sxs-lookup"><span data-stu-id="db22d-122">API layers</span></span>

<span data-ttu-id="db22d-123">.NET 编译器 SDK 包含两个主要 API 层：编译器 API 和工作区 API。</span><span class="sxs-lookup"><span data-stu-id="db22d-123">The .NET compiler SDK consists of two main layers of APIs: compiler APIs and workspaces APIs.</span></span>

![由编译器管道 API 表示的 API 层](media/api-layers.png)

### <a name="compiler-apis"></a><span data-ttu-id="db22d-125">编译器 API</span><span class="sxs-lookup"><span data-stu-id="db22d-125">Compiler APIs</span></span>

<span data-ttu-id="db22d-126">编译器层包含的对象模型（语法模型和语义模型）对应于在编译器管道的每个阶段公开的信息。</span><span class="sxs-lookup"><span data-stu-id="db22d-126">The compiler layer contains the object models that correspond to information exposed at each phase of the compiler pipeline, both syntactic and semantic.</span></span> <span data-ttu-id="db22d-127">编译器层还包含编译器的单次调用的不可变快照，包括程序集引用、编译器选项和源代码文件。</span><span class="sxs-lookup"><span data-stu-id="db22d-127">The compiler layer also contains an immutable snapshot of a single invocation of a compiler, including assembly references, compiler options, and source code files.</span></span> <span data-ttu-id="db22d-128">C# 语言和 Visual Basic 语言由两个不同的 API 表示。</span><span class="sxs-lookup"><span data-stu-id="db22d-128">There are two distinct APIs that represent the C# language and the Visual Basic language.</span></span> <span data-ttu-id="db22d-129">这两个 API 的形状类似，但针对每种语言的高保真进行了定制。</span><span class="sxs-lookup"><span data-stu-id="db22d-129">These two APIs are similar in shape but tailored for high-fidelity to each individual language.</span></span> <span data-ttu-id="db22d-130">此层不包含 Visual Studio 组件的依赖项。</span><span class="sxs-lookup"><span data-stu-id="db22d-130">This layer has no dependencies on Visual Studio components.</span></span>

### <a name="diagnostic-apis"></a><span data-ttu-id="db22d-131">诊断 API</span><span class="sxs-lookup"><span data-stu-id="db22d-131">Diagnostic APIs</span></span>

<span data-ttu-id="db22d-132">在编译器分析过程中，编译器会生成一组诊断，包括语法、语义、明确赋值以及各种警告和信息性诊断。</span><span class="sxs-lookup"><span data-stu-id="db22d-132">As part of its analysis the compiler may produce a set of diagnostics covering everything from syntax, semantic, and definite assignment errors to various warnings and informational diagnostics.</span></span> <span data-ttu-id="db22d-133">编译器 API 层通过一个可扩展 API 公开诊断，该可扩展 API 允许将用户定义的分析器插入编译过程。</span><span class="sxs-lookup"><span data-stu-id="db22d-133">The Compiler API layer exposes diagnostics through an extensible API that allows user-defined analyzers to be plugged into the compilation process.</span></span> <span data-ttu-id="db22d-134">它支持随编译器定义的诊断一起，生成用户定义的诊断，例如由 StyleCop 或 FxCop 等工具生成的诊断。</span><span class="sxs-lookup"><span data-stu-id="db22d-134">It allows user-defined diagnostics, such as those produced by tools like StyleCop or FxCop, to be produced alongside compiler-defined diagnostics.</span></span> <span data-ttu-id="db22d-135">以这种方式生成诊断有以下优势：与 MSBuild 和 Visual Studio 等工具（具体取决于对根据策略停止生成等体验进行的诊断）自然地集成、在编辑器中显示实时波形曲线，以及建议代码修复。</span><span class="sxs-lookup"><span data-stu-id="db22d-135">Producing diagnostics in this way has the benefit of integrating naturally with tools such as MSBuild and Visual Studio which depend on diagnostics for experiences such as halting a build based on policy and showing live squiggles in the editor and suggesting code fixes.</span></span>

### <a name="scripting-apis"></a><span data-ttu-id="db22d-136">脚本 API</span><span class="sxs-lookup"><span data-stu-id="db22d-136">Scripting APIs</span></span>

<span data-ttu-id="db22d-137">托管 API 和脚本 API 是编译器层的一部分。</span><span class="sxs-lookup"><span data-stu-id="db22d-137">Hosting and scripting APIs are part of the compiler layer.</span></span> <span data-ttu-id="db22d-138">可使用它们来执行代码片段和累积运行时执行上下文。</span><span class="sxs-lookup"><span data-stu-id="db22d-138">You can use them for executing code snippets and accumulating a runtime execution context.</span></span>
<span data-ttu-id="db22d-139">C# 交互式 REPL （读取–求值–打印循环）可使用这些 API。</span><span class="sxs-lookup"><span data-stu-id="db22d-139">The C# interactive REPL (Read-Evaluate-Print Loop) uses these APIs.</span></span> <span data-ttu-id="db22d-140">借助 REPL，可将 C# 用作脚本语言，在编写代码的同时，以交互方式执行代码。</span><span class="sxs-lookup"><span data-stu-id="db22d-140">The REPL enables you to use C# as a scripting language, executing the code interactively as you write it.</span></span>

### <a name="workspaces-apis"></a><span data-ttu-id="db22d-141">工作区 API</span><span class="sxs-lookup"><span data-stu-id="db22d-141">Workspaces APIs</span></span>

<span data-ttu-id="db22d-142">工作区层包含工作区 API，是对整个解决方案执行代码分析和重构的起点。</span><span class="sxs-lookup"><span data-stu-id="db22d-142">The Workspaces layer contains the Workspace API, which is the starting point for doing code analysis and refactoring over entire solutions.</span></span> <span data-ttu-id="db22d-143">它有助于将解决方案中项目的全部相关信息组织为单个对象模型，可让用户直接访问编译器层对象模型，而无需分析文件、配置选项，或管理项目到项目依赖项。</span><span class="sxs-lookup"><span data-stu-id="db22d-143">It assists you in organizing all the information about the projects in a solution into single object model, offering you direct access to the compiler layer object models without needing to parse files, configure options, or manage project-to-project dependencies.</span></span>

<span data-ttu-id="db22d-144">此外，工作区层还包含一组 API，用于实现在 Visual Studio IDE 等主机环境中使用的代码分析和重构工具。</span><span class="sxs-lookup"><span data-stu-id="db22d-144">In addition, the Workspaces layer surfaces a set of APIs used when implementing code analysis and refactoring tools that function within a host environment like the Visual Studio IDE.</span></span> <span data-ttu-id="db22d-145">相关示例包括查找所有引用、格式设置和代码生成 API。</span><span class="sxs-lookup"><span data-stu-id="db22d-145">Examples include the Find All References, Formatting, and Code Generation APIs.</span></span>

<span data-ttu-id="db22d-146">此层不包含 Visual Studio 组件的依赖项。</span><span class="sxs-lookup"><span data-stu-id="db22d-146">This layer has no dependencies on Visual Studio components.</span></span>
