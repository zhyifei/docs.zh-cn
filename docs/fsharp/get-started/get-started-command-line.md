---
title: '使用命令行工具实现 F # 入门'
description: '了解如何在 F # 在任何操作系统 （Windows、 macOs 或 Linux） 上使用.NET Core CLI 构建简单的多项目解决方案。'
ms.date: 03/26/2018
ms.openlocfilehash: 8a82970f33c8bbe1b8cdd8fb6499b59b16d3cbf3
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44198512"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="39e91-103">要开始使用 F # 使用.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="39e91-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="39e91-104">本文介绍如何你可以开始使用 F # 在任何操作系统上 （Windows、 macOS 或 Linux） 使用.NET Core  CLI。</span><span class="sxs-lookup"><span data-stu-id="39e91-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="39e91-105">它将经历构建使用由一个控制台应用程序调用的类库的多项目解决方案。</span><span class="sxs-lookup"><span data-stu-id="39e91-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="39e91-106">系统必备</span><span class="sxs-lookup"><span data-stu-id="39e91-106">Prerequisites</span></span>

<span data-ttu-id="39e91-107">若要开始，你必须安装最新[.NET Core SDK](https://www.microsoft.com/net/download/)。</span><span class="sxs-lookup"><span data-stu-id="39e91-107">To begin, you must install the latest [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

<span data-ttu-id="39e91-108">本文假定，您知道如何使用命令行，并且包含首选的文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="39e91-108">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="39e91-109">如果还没有使用它， [Visual Studio Code](get-started-vscode.md)是作为文本编辑器中进行 F # 很好的选择。</span><span class="sxs-lookup"><span data-stu-id="39e91-109">If you don't already use it, [Visual Studio Code](get-started-vscode.md) is a great option as a text editor for F#.</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="39e91-110">构建简单的多项目解决方案</span><span class="sxs-lookup"><span data-stu-id="39e91-110">Build a simple multi-project solution</span></span>

<span data-ttu-id="39e91-111">打开命令提示符处/终端，并使用[dotnet 新](../../core/tools/dotnet-new.md)命令创建名为的新解决方案文件`FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="39e91-111">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```console
dotnet new sln -o FSNetCore
```

<span data-ttu-id="39e91-112">运行上述命令后会生成以下目录结构：</span><span class="sxs-lookup"><span data-stu-id="39e91-112">The following directory structure is produced after running the previous command:</span></span>

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="39e91-113">编写类库</span><span class="sxs-lookup"><span data-stu-id="39e91-113">Write a class library</span></span>

<span data-ttu-id="39e91-114">将目录更改为*FSNetCore*。</span><span class="sxs-lookup"><span data-stu-id="39e91-114">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="39e91-115">使用`dotnet new`命令，创建一个在类库项目**src**名为库的文件夹。</span><span class="sxs-lookup"><span data-stu-id="39e91-115">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```console
dotnet new classlib -lang F# -o src/Library
```

<span data-ttu-id="39e91-116">运行上述命令后会生成以下目录结构：</span><span class="sxs-lookup"><span data-stu-id="39e91-116">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="39e91-117">内容替换为`Library.fs`使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="39e91-117">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="39e91-118">将 Newtonsoft.Json NuGet 包添加到类库项目。</span><span class="sxs-lookup"><span data-stu-id="39e91-118">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="39e91-119">添加`Library`投影到`FSNetCore`解决方案： 使用[dotnet sln 添加](../../core/tools/dotnet-sln.md)命令：</span><span class="sxs-lookup"><span data-stu-id="39e91-119">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```console
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="39e91-120">运行`dotnet build`以生成项目。</span><span class="sxs-lookup"><span data-stu-id="39e91-120">Run `dotnet build` to build the project.</span></span> <span data-ttu-id="39e91-121">在生成时，将还原未解析的依赖项。</span><span class="sxs-lookup"><span data-stu-id="39e91-121">Unresolved dependencies will be restored when building.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="39e91-122">编写的控制台应用程序使用类库</span><span class="sxs-lookup"><span data-stu-id="39e91-122">Write a console application that consumes the class library</span></span>

<span data-ttu-id="39e91-123">使用`dotnet new`命令，创建一个控制台应用程序中的**src**名为应用程序的文件夹。</span><span class="sxs-lookup"><span data-stu-id="39e91-123">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```console
dotnet new console -lang F# -o src/App
```

<span data-ttu-id="39e91-124">运行上述命令后会生成以下目录结构：</span><span class="sxs-lookup"><span data-stu-id="39e91-124">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        ├── App
        │   ├── App.fsproj
        │   ├── Program.fs
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="39e91-125">内容替换为`Program.fs`文件使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="39e91-125">Replace the contents of the `Program.fs` file with the following code:</span></span>

```fsharp
open System
open Library

[<EntryPoint>]
let main argv =
    printfn "Nice command-line arguments! Here's what JSON.NET has to say about them:"

    argv
    |> Array.map getJsonNetJson
    |> Array.iter (printfn "%s")

    0 // return an integer exit code
```

<span data-ttu-id="39e91-126">添加对的引用`Library`使用的项目[dotnet 添加引用](../../core/tools/dotnet-add-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="39e91-126">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="39e91-127">添加`App`投影到`FSNetCore`解决方案： 使用`dotnet sln add`命令：</span><span class="sxs-lookup"><span data-stu-id="39e91-127">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```console
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="39e91-128">还原 NuGet 依赖项， `dotnet restore` ([请参阅备注](#dotnet-restore-note)) 并运行`dotnet build`以生成项目。</span><span class="sxs-lookup"><span data-stu-id="39e91-128">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="39e91-129">将目录更改为`src/App`控制台项目并运行项目传递`Hello World`作为自变量：</span><span class="sxs-lookup"><span data-stu-id="39e91-129">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```console
cd src/App
dotnet run Hello World
```

<span data-ttu-id="39e91-130">你应看到以下结果：</span><span class="sxs-lookup"><span data-stu-id="39e91-130">You should see the following results:</span></span>

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a><span data-ttu-id="39e91-131">后续步骤</span><span class="sxs-lookup"><span data-stu-id="39e91-131">Next steps</span></span>

<span data-ttu-id="39e91-132">接下来，请查看[F # 教程](../tour.md)若要了解有关不同的 F # 功能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="39e91-132">Next, check out the [Tour of F#](../tour.md) to learn more about different F# features.</span></span>
