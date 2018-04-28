---
title: 使用 project.json 减少包依赖项
description: 创建基于 project.json 的库时减少包依赖项。
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 647d850c1629cddc1584a2044174838930b2fb1d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="reducing-package-dependencies-with-projectjson"></a><span data-ttu-id="e7459-103">使用 project.json 减少包依赖项</span><span class="sxs-lookup"><span data-stu-id="e7459-103">Reducing Package Dependencies with project.json</span></span>

<span data-ttu-id="e7459-104">本文介绍创作 `project.json` 库时减少包依赖项需要了解的内容。</span><span class="sxs-lookup"><span data-stu-id="e7459-104">This article covers what you need to know about reducing your package dependencies when authoring `project.json` libraries.</span></span> <span data-ttu-id="e7459-105">本文结束后，用户将了解如何撰写库，使其仅使用所需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="e7459-105">By the end of this article, you will learn how to compose your library such that it only uses the dependencies it needs.</span></span> 

## <a name="why-its-important"></a><span data-ttu-id="e7459-106">为什么这十分重要</span><span class="sxs-lookup"><span data-stu-id="e7459-106">Why it's Important</span></span>

<span data-ttu-id="e7459-107">.NET Core 是由 NuGet 包组成的产品。</span><span class="sxs-lookup"><span data-stu-id="e7459-107">.NET Core is a product made up of NuGet packages.</span></span>  <span data-ttu-id="e7459-108">基本包为 [.NETStandard.Library 元包](https://www.nuget.org/packages/NETStandard.Library)，它是由其他包组成的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="e7459-108">An essential package is the [.NETStandard.Library metapackage](https://www.nuget.org/packages/NETStandard.Library), which is a NuGet package composed of other packages.</span></span>  <span data-ttu-id="e7459-109">它提供保证可在多个 .NET 实现（例如，.NET Framework、.NET Core 和 Xamarin/Mono）上正常工作的包集。</span><span class="sxs-lookup"><span data-stu-id="e7459-109">It provides you with the set of packages that are guaranteed to work on multiple .NET implementations, such as .NET Framework, .NET Core and Xamarin/Mono.</span></span>

<span data-ttu-id="e7459-110">但是，很有可能库将不会使用它所包含的每个包。</span><span class="sxs-lookup"><span data-stu-id="e7459-110">However, there's a good chance that your library won't use every single package it contains.</span></span>  <span data-ttu-id="e7459-111">当创作库并通过 NuGet 进行分发时，最佳做法是将依赖项“修剪”为仅实际使用的包。</span><span class="sxs-lookup"><span data-stu-id="e7459-111">When authoring a library and distributing it over NuGet, it's a best practice to "trim" your dependencies down to only the packages you actually use.</span></span>  <span data-ttu-id="e7459-112">这会使 NuGet 包的总体内存占用变小。</span><span class="sxs-lookup"><span data-stu-id="e7459-112">This results in a smaller overall footprint for NuGet packages.</span></span>

## <a name="how-to-do-it"></a><span data-ttu-id="e7459-113">如何执行此操作</span><span class="sxs-lookup"><span data-stu-id="e7459-113">How to do it</span></span>

<span data-ttu-id="e7459-114">当前，没有任何可修剪包引用的正式 `dotnet` 命令。</span><span class="sxs-lookup"><span data-stu-id="e7459-114">Currently, there is no official `dotnet` command which trims package references.</span></span>  <span data-ttu-id="e7459-115">相反，需要手动进行此操作。</span><span class="sxs-lookup"><span data-stu-id="e7459-115">Instead, you'll have to do it manually.</span></span>  <span data-ttu-id="e7459-116">一般过程如下所示：</span><span class="sxs-lookup"><span data-stu-id="e7459-116">The general process looks like the following:</span></span>

1. <span data-ttu-id="e7459-117">在 `project.json` 的 `dependencies` 部分中引用 `NETStandard.Library` 版本 `1.6.0`。</span><span class="sxs-lookup"><span data-stu-id="e7459-117">Reference `NETStandard.Library` version `1.6.0` in a `dependencies` section of your `project.json`.</span></span>
2. <span data-ttu-id="e7459-118">使用 `dotnet restore`（[请参阅注释](#dotnet-restore-note)）从命令行中还原包。</span><span class="sxs-lookup"><span data-stu-id="e7459-118">Restore packages with `dotnet restore` ([see note](#dotnet-restore-note)) from the command line.</span></span>
3. <span data-ttu-id="e7459-119">检查 `project.lock.json` 文件并找到 `NETSTandard.Library` 部分。</span><span class="sxs-lookup"><span data-stu-id="e7459-119">Inspect the `project.lock.json` file and find the `NETSTandard.Library` section.</span></span>  <span data-ttu-id="e7459-120">它在文件的开头附近。</span><span class="sxs-lookup"><span data-stu-id="e7459-120">It's near the beginning of the file.</span></span>
4. <span data-ttu-id="e7459-121">复制 `dependencies` 下所有列出的包。</span><span class="sxs-lookup"><span data-stu-id="e7459-121">Copy all of the listed packages under `dependencies`.</span></span>
5. <span data-ttu-id="e7459-122">删除 `.NETStandard.Library` 引用并将其替换为复制的包。</span><span class="sxs-lookup"><span data-stu-id="e7459-122">Remove the `.NETStandard.Library` reference and replace it with the copied packages.</span></span>
6. <span data-ttu-id="e7459-123">删除不需要的包引用。</span><span class="sxs-lookup"><span data-stu-id="e7459-123">Remove references to packages you don't need.</span></span>


<span data-ttu-id="e7459-124">可以通过下面其中一种方式查找不需要的包：</span><span class="sxs-lookup"><span data-stu-id="e7459-124">You can find out which packages you don't need by one of the following ways:</span></span>

1. <span data-ttu-id="e7459-125">试用和错误。</span><span class="sxs-lookup"><span data-stu-id="e7459-125">Trial and error.</span></span>  <span data-ttu-id="e7459-126">这包括删除包、还原以及查看库是否仍在编译，并重复此过程。</span><span class="sxs-lookup"><span data-stu-id="e7459-126">This involves removing a package, restoring, seeing if your library still compiles, and repeating this process.</span></span>
2. <span data-ttu-id="e7459-127">使用如 [ILSpy](http://ilspy.net) 或 [.NET Reflector](http://www.red-gate.com/products/dotnet-development/reflector) 等工具快速浏览引用，以查看代码实际使用的内容。</span><span class="sxs-lookup"><span data-stu-id="e7459-127">Using a tool such as [ILSpy](http://ilspy.net) or [.NET Reflector](http://www.red-gate.com/products/dotnet-development/reflector) to peek at references to see what your code is actually using.</span></span>  <span data-ttu-id="e7459-128">然后，可以删除与正在使用的类型不相对应的包。</span><span class="sxs-lookup"><span data-stu-id="e7459-128">You can then remove packages which don't correspond to types you're using.</span></span>

## <a name="example"></a><span data-ttu-id="e7459-129">示例</span><span class="sxs-lookup"><span data-stu-id="e7459-129">Example</span></span> 

<span data-ttu-id="e7459-130">假设编写了一个为泛型集合类型提供其他功能的库。</span><span class="sxs-lookup"><span data-stu-id="e7459-130">Imagine that you wrote a library which provided additional functionality to generic collection types.</span></span>  <span data-ttu-id="e7459-131">此类库需要依赖于如 `System.Collections` 的包，但可能根本不会依赖于如 `System.Net.Http` 的包。</span><span class="sxs-lookup"><span data-stu-id="e7459-131">Such a library would need to depend on packages such as `System.Collections`, but may not at all depend on packages such as `System.Net.Http`.</span></span>  <span data-ttu-id="e7459-132">因此，将包依赖项修剪为只剩该库所需的依赖项是个好办法！</span><span class="sxs-lookup"><span data-stu-id="e7459-132">As such, it would be good to trim package dependencies down to only what this library required!</span></span>

<span data-ttu-id="e7459-133">若要修剪此库，请从 `project.json` 文件开始，然后将引用添加到 `NETStandard.Library` 版本 `1.6.0`。</span><span class="sxs-lookup"><span data-stu-id="e7459-133">To trim this library, you start with the `project.json` file and add a reference to `NETStandard.Library` version `1.6.0`.</span></span>

```json
{
    "version":"1.0.0",
    "dependencies":{
        "NETStandard.Library":"1.6.0"
    },
    "frameworks": {
        "netstandard1.0": {}
     }
}
```

<span data-ttu-id="e7459-134">接着，使用 `dotnet restore`（[请参阅注释](#dotnet-restore-note)）还原包，检查 `project.lock.json` 文件，并查找为 `NETSTandard.Library` 还原的所有包。</span><span class="sxs-lookup"><span data-stu-id="e7459-134">Next, you restore packages with `dotnet restore` ([see note](#dotnet-restore-note)), inspect the `project.lock.json` file, and find all the packages restored for `NETSTandard.Library`.</span></span>

<span data-ttu-id="e7459-135">以下是以 `netstandard1.0` 为目标时，`project.lock.json` 文件中相关部分的内容：</span><span class="sxs-lookup"><span data-stu-id="e7459-135">Here's what the relevant section in the `project.lock.json` file looks like when targeting `netstandard1.0`:</span></span>

```json
"NETStandard.Library/1.6.0":{
    "type": "package",
    "dependencies": {
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Diagnostics.Debug": "4.0.11",
        "System.Diagnostics.Tools": "4.0.1",
        "System.Globalization": "4.0.11",
        "System.IO": "4.1.0",
        "System.Linq": "4.1.0",
        "System.Net.Primitives": "4.0.11",
        "System.ObjectModel": "4.0.12",
        "System.Reflection": "4.1.0",
        "System.Reflection.Extensions": "4.0.1",
        "System.Reflection.Primitives": "4.0.1",
        "System.Resources.ResourceManager": "4.0.1",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Text.Encoding": "4.0.11",
        "System.Text.Encoding.Extensions": "4.0.11",
        "System.Text.RegularExpressions": "4.1.0",
        "System.Threading": "4.0.11",
        "System.Threading.Tasks": "4.0.11",
        "System.Xml.ReaderWriter": "4.0.11",
        "System.Xml.XDocument": "4.0.11"
    }
}
```

<span data-ttu-id="e7459-136">然后，将包引用复制到库的 `project.json` 文件的 `dependencies` 部分，替换 `NETStandard.Library` 引用：</span><span class="sxs-lookup"><span data-stu-id="e7459-136">Next, copy over the package references into the `dependencies` section of the library's `project.json` file, replacing the `NETStandard.Library` reference:</span></span>

```json
{
    "version":"1.0.0",
    "dependencies":{
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Diagnostics.Debug": "4.0.11",
        "System.Diagnostics.Tools": "4.0.1",
        "System.Globalization": "4.0.11",
        "System.IO": "4.1.0",
        "System.Linq": "4.1.0",
        "System.Net.Primitives": "4.0.11",
        "System.ObjectModel": "4.0.12",
        "System.Reflection": "4.1.0",
        "System.Reflection.Extensions": "4.0.1",
        "System.Reflection.Primitives": "4.0.1",
        "System.Resources.ResourceManager": "4.0.1",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Text.Encoding": "4.0.11",
        "System.Text.Encoding.Extensions": "4.0.11",
        "System.Text.RegularExpressions": "4.1.0",
        "System.Threading": "4.0.11",
        "System.Threading.Tasks": "4.0.11",
        "System.Xml.ReaderWriter": "4.0.11",
        "System.Xml.XDocument": "4.0.11"
    },
    "frameworks":{
        "netstandard1.0": {}
    }
}
```

<span data-ttu-id="e7459-137">这里有相当多的包，其中的许多包对于扩展集合类型来说不是必需的。</span><span class="sxs-lookup"><span data-stu-id="e7459-137">That's quite a lot of packages, many of which which certainly aren't necessary for extending collection types.</span></span>  <span data-ttu-id="e7459-138">可以手动删除包，或者可以使用如 [ILSpy](http://ilspy.net) 或 [.NET Reflector](http://www.red-gate.com/products/dotnet-development/reflector) 等工具来确定代码实际使用的包。</span><span class="sxs-lookup"><span data-stu-id="e7459-138">You can either remove packages manually or use a tool such as [ILSpy](http://ilspy.net) or [.NET Reflector](http://www.red-gate.com/products/dotnet-development/reflector) to identify which packages your code actually uses.</span></span>

<span data-ttu-id="e7459-139">修剪后的包可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="e7459-139">Here's what a trimmed package could look like:</span></span>

```json
{
    "dependencies":{
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Linq": "4.1.0",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Runtime.Handles": "4.0.1",
        "System.Runtime.InteropServices": "4.1.0",
        "System.Runtime.InteropServices.RuntimeInformation": "4.0.0",
        "System.Threading.Tasks": "4.0.11"
    },
    "frameworks":{
        "netstandard1.0": {}
     }
}
```

<span data-ttu-id="e7459-140">现在，它比依赖于 `NETStandard.Library` 元包时内存占用更小。</span><span class="sxs-lookup"><span data-stu-id="e7459-140">Now, it has a smaller footprint than if it had depended on the `NETStandard.Library` metapackage.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]