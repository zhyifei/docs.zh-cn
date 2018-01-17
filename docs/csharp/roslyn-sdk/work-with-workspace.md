---
title: "使用 .NET Compiler Platform SDK 工作区模型"
description: "此概述介绍了用于查询和操作代码的工作区和项目的类型。"
author: billwagner
ms.author: wiwagn
ms.date: 10/15/2017
ms.topic: conceptual
ms.prod: .net
ms.devlang: devlang-csharp
ms.custom: mvc
ms.openlocfilehash: d0d4e9c012b025b9393ac34f0833795fca9841d5
ms.sourcegitcommit: d095094e942eedf09530ea5636fbaf9029853027
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2017
---
# <a name="work-with-a-workspace"></a><span data-ttu-id="4bbc8-103">使用工作区</span><span class="sxs-lookup"><span data-stu-id="4bbc8-103">Work with a workspace</span></span>

<span data-ttu-id="4bbc8-104">工作区层是对整个解决方案执行代码分析和重构的起点。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-104">The **Workspaces** layer is the starting point for doing code analysis and refactoring over entire solutions.</span></span> <span data-ttu-id="4bbc8-105">此层内的工作区 API 有助于将解决方案中项目的全部相关信息组织为单个对象模型，可让用户直接访问编译器层对象模型（如源文本、语法树、语义模型和编译），而无需分析文件、配置选项，或管理项目内依赖项。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-105">Within this layer, the Workspace API assists you in organizing all the information about the projects in a solution into a single object model, offering you direct access to compiler layer object models like source text, syntax trees, semantic models, and compilations without needing to parse files, configure options, or manage inter-project dependencies.</span></span> 

<span data-ttu-id="4bbc8-106">托管环境（如 IDE）提供对应于打开的解决方案的工作区。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-106">Host environments, like an IDE, provide a workspace for you corresponding to the open solution.</span></span> <span data-ttu-id="4bbc8-107">此外，只需加载解决方案文件，即可在 IDE 外部使用此模型。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-107">It is also possible to use this model outside of an IDE by simply loading a solution file.</span></span>

## <a name="workspace"></a><span data-ttu-id="4bbc8-108">工作区</span><span class="sxs-lookup"><span data-stu-id="4bbc8-108">Workspace</span></span>

<span data-ttu-id="4bbc8-109">工作区是作为项目集合的解决方案的活动表示形式，每个工作区都包含一个文档集合。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-109">A workspace is an active representation of your solution as a collection of projects, each with a collection of documents.</span></span> <span data-ttu-id="4bbc8-110">工作区通常与随用户键入或操作属性而不断更改的主机环境关联。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-110">A workspace is typically tied to a host environment that is constantly changing as a user types or manipulates properties.</span></span> 

<span data-ttu-id="4bbc8-111"><xref:Microsoft.CodeAnalysis.Workspace> 提供对当前解决方案模型的访问权限。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-111">The <xref:Microsoft.CodeAnalysis.Workspace> provides access to the current model of the solution.</span></span> <span data-ttu-id="4bbc8-112">主机环境中发生更改时，工作区会引发相应事件，并更新 <xref:Microsoft.CodeAnalysis.Workspace.CurrentSolution?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-112">When a change in the host environment occurs, the workspace fires corresponding events, and the <xref:Microsoft.CodeAnalysis.Workspace.CurrentSolution?displayProperty=nameWithType> property is updated.</span></span> <span data-ttu-id="4bbc8-113">例如，用户在一个源文档对应的文本编辑器中键入时，工作区使用一个事件来指示解决方案的整体模型已更改以及修改了哪个文档。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-113">For example, when the user types in a text editor corresponding to one of the source documents, the workspace uses an event to signal that the overall model of the solution has changed and which document was modified.</span></span> <span data-ttu-id="4bbc8-114">然后，可通过分析新模型的正确性、突出显示重要区域，或针对代码更改提供建议来响应这些更改。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-114">You can then react to those changes by analyzing the new model for correctness, highlighting areas of significance, or making a suggestion for a code change.</span></span> 

<span data-ttu-id="4bbc8-115">此外，还可创建与主机环境断开连接或用于没有主机环境的应用程序的独立工作区。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-115">You can also create stand-alone workspaces that are disconnected from the host environment or used in an application that has no host environment.</span></span>

## <a name="solutions-projects-documents"></a><span data-ttu-id="4bbc8-116">解决方案、项目、文档</span><span class="sxs-lookup"><span data-stu-id="4bbc8-116">Solutions, projects, documents</span></span>

<span data-ttu-id="4bbc8-117">尽管每次按下一个键时工作区都可能会更改，仍可以隔离方式使用解决方案模型。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-117">Although a workspace may change every time a key is pressed, you can work with the model of the solution in isolation.</span></span> 

<span data-ttu-id="4bbc8-118">一个解决方案即是项目和文档的一个不可变模型。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-118">A solution is an immutable model of the projects and documents.</span></span> <span data-ttu-id="4bbc8-119">这意味着可共享模型，而不会锁定或重复。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-119">This means that the model can be shared without locking or duplication.</span></span> <span data-ttu-id="4bbc8-120">从 <xref:Microsoft.CodeAnalysis.Workspace.CurrentSolution?displayProperty=nameWithType> 属性获取解决方案实例后，该实例永远不会更改。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-120">After you obtain a solution instance from the <xref:Microsoft.CodeAnalysis.Workspace.CurrentSolution?displayProperty=nameWithType> property, that instance will never change.</span></span> <span data-ttu-id="4bbc8-121">但是，与语法树和编译类似，可通过基于现有解决方案和特定更改构造新实例来修改解决方案。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-121">However, like with syntax trees and compilations, you can modify solutions by constructing new instances based on existing solutions and specific changes.</span></span> <span data-ttu-id="4bbc8-122">要获取工作区以反映所做的更改，必须将更改后的解决方案显式应用回工作区。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-122">To get the workspace to reflect your changes, you must explicitly apply the changed solution back to the workspace.</span></span>

<span data-ttu-id="4bbc8-123">项目是整体不可变解决方案模型的一部分。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-123">A project is a part of the overall immutable solution model.</span></span> <span data-ttu-id="4bbc8-124">它表示所有源代码文档、分析和编译选项，以及程序集和项目到项目引用。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-124">It represents all the source code documents, parse and compilation options, and both assembly and project-to-project references.</span></span> <span data-ttu-id="4bbc8-125">可从项目中访问相应的编译，而无需确定项目依赖项或分析任何源文件。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-125">From a project, you can access the corresponding compilation without needing to determine project dependencies or parse any source files.</span></span>

<span data-ttu-id="4bbc8-126">文档也是整体不可变解决方案模型的一部分。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-126">A document is also a part of the overall immutable solution model.</span></span> <span data-ttu-id="4bbc8-127">文档表示单个源文件，可从其中访问文件、语法树和语义模型的文本。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-127">A document represents a single source file from which you can access the text of the file, the syntax tree, and the semantic model.</span></span>

<span data-ttu-id="4bbc8-128">下图表示了如何将工作区关联到主机环境和工具，以及如何进行编辑。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-128">The following diagram is a representation of how the Workspace relates to the host environment, tools, and how edits are made.</span></span>

![包含项目和源文件的工作区中不同元素之间的关系](media/workspace-obj-relations.png)

## <a name="summary"></a><span data-ttu-id="4bbc8-130">摘要</span><span class="sxs-lookup"><span data-stu-id="4bbc8-130">Summary</span></span>

<span data-ttu-id="4bbc8-131">Roslyn 公开了一组编译器 API 和工作区 API，提供了有关源代码的丰富信息，并完全保真地记录了 C# 和 Visual Basic 语言。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-131">Roslyn exposes a set of compiler APIs and Workspaces APIs that provides rich information about your source code and that has full fidelity with the C# and Visual Basic languages.</span></span>  <span data-ttu-id="4bbc8-132">.NET Compiler Platform SDK 极大地降低了创建以代码为中心的工具和应用程序的门槛。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-132">The .NET Compiler Platform SDK dramatically lowers the barrier to entry for creating code-focused tools and applications.</span></span> <span data-ttu-id="4bbc8-133">在元编程、代码生成和转换、C# 和 VB 语言的交互式使用以及在域专属语言中嵌入 C# 和 VB 等领域，它带来了许多创新机遇。</span><span class="sxs-lookup"><span data-stu-id="4bbc8-133">It creates many opportunities for innovation in areas such as meta-programming, code generation and transformation, interactive use of the C# and VB languages, and embedding of C# and VB in domain specific languages.</span></span>  
