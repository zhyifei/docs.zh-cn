---
title: "C# 程序结构 - C# 语言介绍"
description: "了解 C# 程序的基本构建基块"
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 984f0314-507f-47a0-af56-9011243f5e65
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8d8f443f8458cd392c75e9787e612ca1cc3518c7
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="program-structure"></a><span data-ttu-id="e43e7-104">程序结构</span><span class="sxs-lookup"><span data-stu-id="e43e7-104">Program Structure</span></span>

<span data-ttu-id="e43e7-105">C# 中的关键组织结构概念包括***程序***、***命名空间***、***类型***、***成员***和***程序集***。</span><span class="sxs-lookup"><span data-stu-id="e43e7-105">The key organizational concepts in C# are ***programs***, ***namespaces***, ***types***, ***members***, and ***assemblies***.</span></span> <span data-ttu-id="e43e7-106">C# 程序由一个或多个源文件组成。</span><span class="sxs-lookup"><span data-stu-id="e43e7-106">C# programs consist of one or more source files.</span></span> <span data-ttu-id="e43e7-107">程序声明类型，而类型则包含成员，并被整理到命名空间中。</span><span class="sxs-lookup"><span data-stu-id="e43e7-107">Programs declare types, which contain members and can be organized into namespaces.</span></span> <span data-ttu-id="e43e7-108">类型示例包括类和接口。</span><span class="sxs-lookup"><span data-stu-id="e43e7-108">Classes and interfaces are examples of types.</span></span> <span data-ttu-id="e43e7-109">成员示例包括字段、方法、属性和事件。</span><span class="sxs-lookup"><span data-stu-id="e43e7-109">Fields, methods, properties, and events are examples of members.</span></span> <span data-ttu-id="e43e7-110">编译完的 C# 程序实际上会打包到程序集中。</span><span class="sxs-lookup"><span data-stu-id="e43e7-110">When C# programs are compiled, they are physically packaged into assemblies.</span></span> <span data-ttu-id="e43e7-111">程序集的文件扩展名通常为 `.exe` 或 `.dll`，具体取决于实现的是***应用程序***还是***库***。</span><span class="sxs-lookup"><span data-stu-id="e43e7-111">Assemblies typically have the file extension `.exe` or `.dll`, depending on whether they implement ***applications*** or ***libraries***, respectively.</span></span>

<span data-ttu-id="e43e7-112">以下示例在 `Acme.Collections` 命名空间中声明 `Stack` 类：</span><span class="sxs-lookup"><span data-stu-id="e43e7-112">The example declares a class named `Stack` in a namespace called `Acme.Collections`:</span></span>

<span data-ttu-id="e43e7-113">[!code-csharp[Stack](../../../samples/snippets/csharp/tour/program-structure/program.cs#L1-L34)]</span><span class="sxs-lookup"><span data-stu-id="e43e7-113">[!code-csharp[Stack](../../../samples/snippets/csharp/tour/program-structure/program.cs#L1-L34)]</span></span>

<span data-ttu-id="e43e7-114">此类的完全限定的名称为 `Acme.Collections.Stack`。</span><span class="sxs-lookup"><span data-stu-id="e43e7-114">The fully qualified name of this class is `Acme.Collections.Stack`.</span></span> <span data-ttu-id="e43e7-115">此类包含多个成员：一个 `top` 字段、两个方法（`Push` 和 `Pop`）和一个 `Entry` 嵌套类。</span><span class="sxs-lookup"><span data-stu-id="e43e7-115">The class contains several members: a field named `top`, two methods named `Push` and `Pop`, and a nested class named `Entry`.</span></span> <span data-ttu-id="e43e7-116">`Entry` 类还包含三个成员：一个 `next` 字段、一个 `data` 字段和一个构造函数。</span><span class="sxs-lookup"><span data-stu-id="e43e7-116">The `Entry` class further contains three members: a field named `next`, a field named `data`, and a constructor.</span></span> <span data-ttu-id="e43e7-117">假定示例的源代码存储在 `acme.cs` 文件中，以下命令行</span><span class="sxs-lookup"><span data-stu-id="e43e7-117">Assuming that the source code of the example is stored in the file `acme.cs`, the command line</span></span>

```
csc /t:library acme.cs
```

<span data-ttu-id="e43e7-118">将示例编译成库（不含 `Main` 入口点的代码），并生成 `acme.dll` 程序集。</span><span class="sxs-lookup"><span data-stu-id="e43e7-118">compiles the example as a library (code without a `Main` entry point) and produces an assembly named `acme.dll`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e43e7-119">上述示例使用 `csc` 作为命令行 C# 编译器。</span><span class="sxs-lookup"><span data-stu-id="e43e7-119">The examples above use `csc` as the command line C# compiler.</span></span> <span data-ttu-id="e43e7-120">此编译器是 Windows 可执行文件。</span><span class="sxs-lookup"><span data-stu-id="e43e7-120">This compiler is a windows executable.</span></span> <span data-ttu-id="e43e7-121">若要在其他平台上使用 C#，应使用 .NET Core 工具。</span><span class="sxs-lookup"><span data-stu-id="e43e7-121">To use C# across other platforms, you should use the tools for .NET Core.</span></span> <span data-ttu-id="e43e7-122">.NET Core 生态系统使用 `dotnet` CLI 来管理命令行生成。</span><span class="sxs-lookup"><span data-stu-id="e43e7-122">The .NET Core ecosystem uses the `dotnet` CLI to manage command line builds.</span></span> <span data-ttu-id="e43e7-123">这包括管理依赖项和调用 C# 编译器。</span><span class="sxs-lookup"><span data-stu-id="e43e7-123">This includes managing dependencies, and invoking the C# compiler.</span></span> <span data-ttu-id="e43e7-124">有关在 .NET Core 支持的平台上使用这些工具的完整说明，请参阅[这篇教程](../../core/tutorials/using-with-xplat-cli.md)。</span><span class="sxs-lookup"><span data-stu-id="e43e7-124">See [this tutorial](../../core/tutorials/using-with-xplat-cli.md) for a full description of those tools on the platforms supported by .NET Core.</span></span>

<span data-ttu-id="e43e7-125">程序集包含中间语言 (IL) 指令形式的可执行代码和元数据形式的符号信息。</span><span class="sxs-lookup"><span data-stu-id="e43e7-125">Assemblies contain executable code in the form of Intermediate Language (IL) instructions, and symbolic information in the form of metadata.</span></span> <span data-ttu-id="e43e7-126">执行前，程序集中的 IL 代码会被 .NET 公共语言运行时的实时 (JIT) 编译器自动转换成处理器专属代码。</span><span class="sxs-lookup"><span data-stu-id="e43e7-126">Before it is executed, the IL code in an assembly is automatically converted to processor-specific code by the Just-In-Time (JIT) compiler of .NET Common Language Runtime.</span></span>

<span data-ttu-id="e43e7-127">由于程序集是包含代码和元数据的自描述功能单元，因此无需在 C# 中使用 `#include` 指令和头文件。</span><span class="sxs-lookup"><span data-stu-id="e43e7-127">Because an assembly is a self-describing unit of functionality containing both code and metadata, there is no need for `#include` directives and header files in C#.</span></span> <span data-ttu-id="e43e7-128">只需在编译程序时引用特定的程序集，即可在 C# 程序中使用此程序集中包含的公共类型和成员。</span><span class="sxs-lookup"><span data-stu-id="e43e7-128">The public types and members contained in a particular assembly are made available in a C# program simply by referencing that assembly when compiling the program.</span></span> <span data-ttu-id="e43e7-129">例如，此程序使用 `acme.dll` 程序集中的 `Acme.Collections.Stack` 类：</span><span class="sxs-lookup"><span data-stu-id="e43e7-129">For example, this program uses the `Acme.Collections.Stack` class from the `acme.dll` assembly:</span></span>

<span data-ttu-id="e43e7-130">[!code-csharp[UsingStack](../../../samples/snippets/csharp/tour/program-structure/Program.cs#L38-L52)]</span><span class="sxs-lookup"><span data-stu-id="e43e7-130">[!code-csharp[UsingStack](../../../samples/snippets/csharp/tour/program-structure/Program.cs#L38-L52)]</span></span>

<span data-ttu-id="e43e7-131">如果程序存储在文件 `example.cs` 中，那么在 `example.cs` 编译完后，可以使用编译器的 /r 选项引用 acme.dll 程序集：</span><span class="sxs-lookup"><span data-stu-id="e43e7-131">If the program is stored in the file `example.cs`, when `example.cs` is compiled, the acme.dll assembly can be referenced using the compiler’s /r option:</span></span>

```
csc /r:acme.dll example.cs
```

<span data-ttu-id="e43e7-132">这会创建 `example.exe` 可执行程序集，它将在运行时输出以下内容：</span><span class="sxs-lookup"><span data-stu-id="e43e7-132">This creates an executable assembly named `example.exe`, which, when run, produces the output:</span></span>

```
100
10
1
```

<span data-ttu-id="e43e7-133">使用 C#，可以将程序的源文本存储在多个源文件中。</span><span class="sxs-lookup"><span data-stu-id="e43e7-133">C# permits the source text of a program to be stored in several source files.</span></span> <span data-ttu-id="e43e7-134">编译多文件 C# 程序时，可以将所有源文件一起处理，并且源文件可以随意相互引用。从概念上讲，就像是所有源文件在处理前被集中到一个大文件中一样。</span><span class="sxs-lookup"><span data-stu-id="e43e7-134">When a multi-file C# program is compiled, all of the source files are processed together, and the source files can freely reference each other—conceptually, it is as if all the source files were concatenated into one large file before being processed.</span></span> <span data-ttu-id="e43e7-135">在 C# 中，永远都不需要使用前向声明，因为声明顺序无关紧要（除了极少数的例外情况）。</span><span class="sxs-lookup"><span data-stu-id="e43e7-135">Forward declarations are never needed in C# because, with very few exceptions, declaration order is insignificant.</span></span> <span data-ttu-id="e43e7-136">C# 并不限制源文件只能声明一种公共类型，也不要求源文件的文件名必须与其中声明的类型相匹配。</span><span class="sxs-lookup"><span data-stu-id="e43e7-136">C# does not limit a source file to declaring only one public type nor does it require the name of the source file to match a type declared in the source file.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="e43e7-137">[上一页](index.md)
[下一页](types-and-variables.md)</span><span class="sxs-lookup"><span data-stu-id="e43e7-137">[Previous](index.md)
[Next](types-and-variables.md)</span></span>

