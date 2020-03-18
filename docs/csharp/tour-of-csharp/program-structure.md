---
title: C# 程序结构 - C# 语言介绍
description: 了解 C# 程序的基本构建基块
ms.date: 02/25/2020
ms.assetid: 984f0314-507f-47a0-af56-9011243f5e65
ms.openlocfilehash: c09c11a4dd957b29b2adb7aaa8d68a50f30620b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156826"
---
# <a name="program-structure"></a><span data-ttu-id="c1d8d-103">程序结构</span><span class="sxs-lookup"><span data-stu-id="c1d8d-103">Program Structure</span></span>

<span data-ttu-id="c1d8d-104">C# 中的关键组织结构概念包括***程序***、***命名空间***、***类型***、***成员***和***程序集***。</span><span class="sxs-lookup"><span data-stu-id="c1d8d-104">The key organizational concepts in C# are ***programs***, ***namespaces***, ***types***, ***members***, and ***assemblies***.</span></span> <span data-ttu-id="c1d8d-105">C# 程序由一个或多个源文件组成。</span><span class="sxs-lookup"><span data-stu-id="c1d8d-105">C# programs consist of one or more source files.</span></span> <span data-ttu-id="c1d8d-106">程序声明类型，而类型则包含成员，并被整理到命名空间中。</span><span class="sxs-lookup"><span data-stu-id="c1d8d-106">Programs declare types, which contain members and can be organized into namespaces.</span></span> <span data-ttu-id="c1d8d-107">类型示例包括类和接口。</span><span class="sxs-lookup"><span data-stu-id="c1d8d-107">Classes and interfaces are examples of types.</span></span> <span data-ttu-id="c1d8d-108">成员示例包括字段、方法、属性和事件。</span><span class="sxs-lookup"><span data-stu-id="c1d8d-108">Fields, methods, properties, and events are examples of members.</span></span> <span data-ttu-id="c1d8d-109">编译完的 C# 程序实际上会打包到程序集中。</span><span class="sxs-lookup"><span data-stu-id="c1d8d-109">When C# programs are compiled, they're physically packaged into assemblies.</span></span> <span data-ttu-id="c1d8d-110">程序集的文件扩展名通常为 `.exe` 或 `.dll`，具体取决于实现的是***应用程序***还是***库***。</span><span class="sxs-lookup"><span data-stu-id="c1d8d-110">Assemblies typically have the file extension `.exe` or `.dll`, depending on whether they implement ***applications*** or ***libraries***, respectively.</span></span>

<span data-ttu-id="c1d8d-111">可以使用 `dotnet new` 命令创建名为 acme 的库项目  ：</span><span class="sxs-lookup"><span data-stu-id="c1d8d-111">You can create a library project named *acme* using the `dotnet new` command:</span></span>

```console
dotnet new classlib -o acme
```

<span data-ttu-id="c1d8d-112">在该项目中，在名为 `Acme.Collections` 的命名空间中声明名为 `Stack` 的类：</span><span class="sxs-lookup"><span data-stu-id="c1d8d-112">In that project, declare a class named `Stack` in a namespace called `Acme.Collections`:</span></span>

[!code-csharp[Stack](../../../samples/snippets/csharp/tour/program-structure/program.cs#L1-L34)]

<span data-ttu-id="c1d8d-113">此类的完全限定的名称为 `Acme.Collections.Stack`。</span><span class="sxs-lookup"><span data-stu-id="c1d8d-113">The fully qualified name of this class is `Acme.Collections.Stack`.</span></span> <span data-ttu-id="c1d8d-114">此类包含多个成员：一个 `top` 字段、两个方法（`Push` 和 `Pop`）和一个 `Entry` 嵌套类。</span><span class="sxs-lookup"><span data-stu-id="c1d8d-114">The class contains several members: a field named `top`, two methods named `Push` and `Pop`, and a nested class named `Entry`.</span></span> <span data-ttu-id="c1d8d-115">`Entry` 类还包含三个成员：一个 `next` 字段、一个 `data` 字段和一个构造函数。</span><span class="sxs-lookup"><span data-stu-id="c1d8d-115">The `Entry` class further contains three members: a field named `next`, a field named `data`, and a constructor.</span></span> <span data-ttu-id="c1d8d-116">命令：</span><span class="sxs-lookup"><span data-stu-id="c1d8d-116">The command:</span></span>

```console
dotnet build
```

<span data-ttu-id="c1d8d-117">将示例编译成库（不含 `Main` 入口点的代码），并生成 `acme.dll` 程序集。</span><span class="sxs-lookup"><span data-stu-id="c1d8d-117">compiles the example as a library (code without a `Main` entry point) and produces an assembly named `acme.dll`.</span></span>

<span data-ttu-id="c1d8d-118">程序集包含中间语言 (IL) 指令形式的可执行代码和元数据形式的符号信息。</span><span class="sxs-lookup"><span data-stu-id="c1d8d-118">Assemblies contain executable code in the form of Intermediate Language (IL) instructions, and symbolic information in the form of metadata.</span></span> <span data-ttu-id="c1d8d-119">执行前，.NET 公共语言运行时的实时 (JIT) 编译器会将程序集中的 IL 代码转换为特定于处理器的代码。</span><span class="sxs-lookup"><span data-stu-id="c1d8d-119">Before it's executed, the Just-In-Time (JIT) compiler of .NET Common Language Runtime converts the IL code in an assembly to processor-specific code.</span></span>

<span data-ttu-id="c1d8d-120">由于程序集是包含代码和元数据的自描述功能单元，因此无需在 C# 中使用 `#include` 指令和头文件。</span><span class="sxs-lookup"><span data-stu-id="c1d8d-120">Because an assembly is a self-describing unit of functionality containing both code and metadata, there's no need for `#include` directives and header files in C#.</span></span> <span data-ttu-id="c1d8d-121">只需在编译程序时引用特定的程序集，即可在 C# 程序中使用此程序集中包含的公共类型和成员。</span><span class="sxs-lookup"><span data-stu-id="c1d8d-121">The public types and members contained in a particular assembly are made available in a C# program simply by referencing that assembly when compiling the program.</span></span> <span data-ttu-id="c1d8d-122">例如，此程序使用 `acme.dll` 程序集中的 `Acme.Collections.Stack` 类：</span><span class="sxs-lookup"><span data-stu-id="c1d8d-122">For example, this program uses the `Acme.Collections.Stack` class from the `acme.dll` assembly:</span></span>

[!code-csharp[UsingStack](../../../samples/snippets/csharp/tour/program-structure/Program.cs#L38-L52)]

<span data-ttu-id="c1d8d-123">上述程序的项目的 .csproj 文件必须包含 C# 编译器的引用节点，以解析对 `acme.dll` 程序集中类的引用  ：</span><span class="sxs-lookup"><span data-stu-id="c1d8d-123">The *csproj* file for the preceding program's project must include a reference node for the C# compiler to resolve references to the classes in the `acme.dll` assembly:</span></span>

```xml
  <ItemGroup>
    <ProjectReference Include="..\acme\acme.csproj" />
  </ItemGroup>
```

<span data-ttu-id="c1d8d-124">完成此操作后，`dotnet build` 会创建名为 `example.exe` 的可执行程序集，它将在运行时输出以下内容：</span><span class="sxs-lookup"><span data-stu-id="c1d8d-124">After that addition, `dotnet build` creates an executable assembly named `example.exe`, which, when run, produces the output:</span></span>

```console
100
10
1
```

<span data-ttu-id="c1d8d-125">使用 C#，可以将程序的源文本存储在多个源文件中。</span><span class="sxs-lookup"><span data-stu-id="c1d8d-125">C# permits the source text of a program to be stored in several source files.</span></span> <span data-ttu-id="c1d8d-126">编译多文件 C# 程序时，可以将所有源文件一起处理，并且源文件可以随意相互引用。从概念上讲，就像是所有源文件在处理前被集中到一个大文件中一样。</span><span class="sxs-lookup"><span data-stu-id="c1d8d-126">When a multi-file C# program is compiled, all of the source files are processed together, and the source files can freely reference each other—conceptually, it is as if all the source files were concatenated into one large file before being processed.</span></span> <span data-ttu-id="c1d8d-127">在 C# 中永远都不需要使用前向声明，因为声明顺序无关紧要（极少数例外情况除外）。</span><span class="sxs-lookup"><span data-stu-id="c1d8d-127">Forward declarations are never needed in C# because, with few exceptions, declaration order is insignificant.</span></span> <span data-ttu-id="c1d8d-128">C# 并不限制源文件只能声明一种公共类型，也不要求源文件的文件名必须与其中声明的类型相匹配。</span><span class="sxs-lookup"><span data-stu-id="c1d8d-128">C# does not limit a source file to declaring only one public type nor does it require the name of the source file to match a type declared in the source file.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c1d8d-129">[上一页](index.md)
>[下一页](types-and-variables.md)</span><span class="sxs-lookup"><span data-stu-id="c1d8d-129">[Previous](index.md)
[Next](types-and-variables.md)</span></span>
