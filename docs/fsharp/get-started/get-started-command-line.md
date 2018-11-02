---
title: '使用命令行工具实现 F # 入门'
description: '了解如何在 F # 在任何操作系统 （Windows、 macOs 或 Linux） 上使用.NET Core CLI 构建简单的多项目解决方案。'
ms.date: 03/26/2018
ms.openlocfilehash: 8a82970f33c8bbe1b8cdd8fb6499b59b16d3cbf3
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "45673904"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="6a2f6-103">要开始使用 F # 使用.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="6a2f6-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="6a2f6-104">本文介绍如何你可以开始使用 F # 在任何操作系统上 （Windows、 macOS 或 Linux） 使用.NET Core  CLI。</span><span class="sxs-lookup"><span data-stu-id="6a2f6-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="6a2f6-105">它将经历构建使用由一个控制台应用程序调用的类库的多项目解决方案。</span><span class="sxs-lookup"><span data-stu-id="6a2f6-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6a2f6-106">系统必备</span><span class="sxs-lookup"><span data-stu-id="6a2f6-106">Prerequisites</span></span>

<span data-ttu-id="6a2f6-107">若要开始，你必须安装最新[.NET Core SDK](https://www.microsoft.com/net/download/)。</span><span class="sxs-lookup"><span data-stu-id="6a2f6-107">To begin, you must install the latest [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

<span data-ttu-id="6a2f6-108">本文假定，您知道如何使用命令行，并且包含首选的文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="6a2f6-108">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="6a2f6-109">如果还没有使用它， [Visual Studio Code](get-started-vscode.md)是作为文本编辑器中进行 F # 很好的选择。</span><span class="sxs-lookup"><span data-stu-id="6a2f6-109">If you don't already use it, [Visual Studio Code](get-started-vscode.md) is a great option as a text editor for F#.</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="6a2f6-110">构建简单的多项目解决方案</span><span class="sxs-lookup"><span data-stu-id="6a2f6-110">Build a simple multi-project solution</span></span>

<span data-ttu-id="6a2f6-111">打开命令提示符处/终端，并使用[dotnet 新](../../core/tools/dotnet-new.md)命令创建名为的新解决方案文件`FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="6a2f6-111">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```console
dotnet new sln -o FSNetCore
```

<span data-ttu-id="6a2f6-112">运行上述命令后会生成以下目录结构：</span><span class="sxs-lookup"><span data-stu-id="6a2f6-112">The following directory structure is produced after running the previous command:</span></span>

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="6a2f6-113">编写类库</span><span class="sxs-lookup"><span data-stu-id="6a2f6-113">Write a class library</span></span>

<span data-ttu-id="6a2f6-114">将目录更改为*FSNetCore*。</span><span class="sxs-lookup"><span data-stu-id="6a2f6-114">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="6a2f6-115">使用`dotnet new`命令，创建一个在类库项目**src**名为库的文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a2f6-115">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```console
dotnet new classlib -lang F# -o src/Library
```

<span data-ttu-id="6a2f6-116">运行上述命令后会生成以下目录结构：</span><span class="sxs-lookup"><span data-stu-id="6a2f6-116">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="6a2f6-117">内容替换为`Library.fs`使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="6a2f6-117">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="6a2f6-118">将 Newtonsoft.Json NuGet 包添加到类库项目。</span><span class="sxs-lookup"><span data-stu-id="6a2f6-118">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="6a2f6-119">添加`Library`投影到`FSNetCore`解决方案： 使用[dotnet sln 添加](../../core/tools/dotnet-sln.md)命令：</span><span class="sxs-lookup"><span data-stu-id="6a2f6-119">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```console
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="6a2f6-120">运行`dotnet build`以生成项目。</span><span class="sxs-lookup"><span data-stu-id="6a2f6-120">Run `dotnet build` to build the project.</span></span> <span data-ttu-id="6a2f6-121">在生成时，将还原未解析的依赖项。</span><span class="sxs-lookup"><span data-stu-id="6a2f6-121">Unresolved dependencies will be restored when building.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="6a2f6-122">编写的控制台应用程序使用类库</span><span class="sxs-lookup"><span data-stu-id="6a2f6-122">Write a console application that consumes the class library</span></span>

<span data-ttu-id="6a2f6-123">使用`dotnet new`命令，创建一个控制台应用程序中的**src**名为应用程序的文件夹。</span><span class="sxs-lookup"><span data-stu-id="6a2f6-123">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```console
dotnet new console -lang F# -o src/App
```

<span data-ttu-id="6a2f6-124">运行上述命令后会生成以下目录结构：</span><span class="sxs-lookup"><span data-stu-id="6a2f6-124">The following directory structure is produced after running the previous command:</span></span>

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

<span data-ttu-id="6a2f6-125">内容替换为`Program.fs`文件使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="6a2f6-125">Replace the contents of the `Program.fs` file with the following code:</span></span>

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

<span data-ttu-id="6a2f6-126">添加对的引用`Library`使用的项目[dotnet 添加引用](../../core/tools/dotnet-add-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="6a2f6-126">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="6a2f6-127">添加`App`投影到`FSNetCore`解决方案： 使用`dotnet sln add`命令：</span><span class="sxs-lookup"><span data-stu-id="6a2f6-127">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```console
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="6a2f6-128">还原 NuGet 依赖项， `dotnet restore` ([请参阅备注](#dotnet-restore-note)) 并运行`dotnet build`以生成项目。</span><span class="sxs-lookup"><span data-stu-id="6a2f6-128">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="6a2f6-129">将目录更改为`src/App`控制台项目并运行项目传递`Hello World`作为自变量：</span><span class="sxs-lookup"><span data-stu-id="6a2f6-129">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```console
cd src/App
dotnet run Hello World
```

<span data-ttu-id="6a2f6-130">你应看到以下结果：</span><span class="sxs-lookup"><span data-stu-id="6a2f6-130">You should see the following results:</span></span>

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a><span data-ttu-id="6a2f6-131">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6a2f6-131">Next steps</span></span>

<span data-ttu-id="6a2f6-132">接下来，请查看[F # 教程](../tour.md)若要了解有关不同的 F # 功能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6a2f6-132">Next, check out the [Tour of F#](../tour.md) to learn more about different F# features.</span></span>
