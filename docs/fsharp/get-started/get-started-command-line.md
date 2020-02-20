---
title: 命令行工具F#入门
description: 了解如何F#使用 .NET Core CLI 在任何操作系统（Windows、MacOS 或 Linux）上构建简单的多项目解决方案。
ms.date: 03/26/2018
ms.openlocfilehash: 6f67314f49150e20b18734f21f24daa3ce856922
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504142"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="e2aa8-103">要开始使用 F # 使用.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="e2aa8-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="e2aa8-104">本文介绍如何你可以开始使用 F # 在任何操作系统上 （Windows、 macOS 或 Linux） 使用.NET Core  CLI。</span><span class="sxs-lookup"><span data-stu-id="e2aa8-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="e2aa8-105">其中介绍了如何使用控制台应用程序调用的类库构建多项目解决方案。</span><span class="sxs-lookup"><span data-stu-id="e2aa8-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e2aa8-106">必备条件</span><span class="sxs-lookup"><span data-stu-id="e2aa8-106">Prerequisites</span></span>

<span data-ttu-id="e2aa8-107">若要开始，必须安装最新[.NET Core SDK](https://dotnet.microsoft.com/download)。</span><span class="sxs-lookup"><span data-stu-id="e2aa8-107">To begin, you must install the latest [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

<span data-ttu-id="e2aa8-108">本文假设你知道如何使用命令行并具有首选文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="e2aa8-108">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="e2aa8-109">如果尚未使用该选项， [Visual Studio Code](get-started-vscode.md)是的一个很好的选项F#。</span><span class="sxs-lookup"><span data-stu-id="e2aa8-109">If you don't already use it, [Visual Studio Code](get-started-vscode.md) is a great option as a text editor for F#.</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="e2aa8-110">构建简单的多项目解决方案</span><span class="sxs-lookup"><span data-stu-id="e2aa8-110">Build a simple multi-project solution</span></span>

<span data-ttu-id="e2aa8-111">打开命令提示符/终端，并使用[dotnet new](../../core/tools/dotnet-new.md)命令创建名为 `FSNetCore`的新解决方案文件：</span><span class="sxs-lookup"><span data-stu-id="e2aa8-111">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```dotnetcli
dotnet new sln -o FSNetCore
```

<span data-ttu-id="e2aa8-112">运行上述命令后，将生成以下目录结构：</span><span class="sxs-lookup"><span data-stu-id="e2aa8-112">The following directory structure is produced after running the previous command:</span></span>

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="e2aa8-113">编写类库</span><span class="sxs-lookup"><span data-stu-id="e2aa8-113">Write a class library</span></span>

<span data-ttu-id="e2aa8-114">将目录更改为*FSNetCore*。</span><span class="sxs-lookup"><span data-stu-id="e2aa8-114">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="e2aa8-115">使用 `dotnet new` 命令，在名为 Library 的**src**文件夹中创建一个类库项目。</span><span class="sxs-lookup"><span data-stu-id="e2aa8-115">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```dotnetcli
dotnet new classlib -lang "F#" -o src/Library
```

<span data-ttu-id="e2aa8-116">运行上述命令后，将生成以下目录结构：</span><span class="sxs-lookup"><span data-stu-id="e2aa8-116">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="e2aa8-117">将 `Library.fs` 的内容替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="e2aa8-117">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="e2aa8-118">将 Newtonsoft.json NuGet 包添加到库项目。</span><span class="sxs-lookup"><span data-stu-id="e2aa8-118">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```dotnetcli
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="e2aa8-119">使用[dotnet .sln add](../../core/tools/dotnet-sln.md)命令将 `Library` 项目添加到 `FSNetCore` 解决方案：</span><span class="sxs-lookup"><span data-stu-id="e2aa8-119">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```dotnetcli
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="e2aa8-120">运行 `dotnet build` 以生成项目。</span><span class="sxs-lookup"><span data-stu-id="e2aa8-120">Run `dotnet build` to build the project.</span></span> <span data-ttu-id="e2aa8-121">生成时将还原未解析的依赖项。</span><span class="sxs-lookup"><span data-stu-id="e2aa8-121">Unresolved dependencies will be restored when building.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="e2aa8-122">编写使用类库的控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="e2aa8-122">Write a console application that consumes the class library</span></span>

<span data-ttu-id="e2aa8-123">使用 `dotnet new` 命令，在名为 "应用" 的**src**文件夹中创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="e2aa8-123">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```dotnetcli
dotnet new console -lang "F#" -o src/App
```

<span data-ttu-id="e2aa8-124">运行上述命令后，将生成以下目录结构：</span><span class="sxs-lookup"><span data-stu-id="e2aa8-124">The following directory structure is produced after running the previous command:</span></span>

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

<span data-ttu-id="e2aa8-125">将 `Program.fs` 文件的内容替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="e2aa8-125">Replace the contents of the `Program.fs` file with the following code:</span></span>

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

<span data-ttu-id="e2aa8-126">使用[dotnet 添加引用](../../core/tools/dotnet-add-reference.md)添加对 `Library` 项目的引用。</span><span class="sxs-lookup"><span data-stu-id="e2aa8-126">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```dotnetcli
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="e2aa8-127">使用 `dotnet sln add` 命令将 `App` 项目添加到 `FSNetCore` 解决方案：</span><span class="sxs-lookup"><span data-stu-id="e2aa8-127">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```dotnetcli
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="e2aa8-128">还原 NuGet 依赖项，`dotnet restore` 并运行 `dotnet build` 以生成项目。</span><span class="sxs-lookup"><span data-stu-id="e2aa8-128">Restore the NuGet dependencies, `dotnet restore` and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="e2aa8-129">将目录更改为 `src/App` 控制台项目，并运行将 `Hello World` 作为参数传递的项目：</span><span class="sxs-lookup"><span data-stu-id="e2aa8-129">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```dotnetcli
cd src/App
dotnet run Hello World
```

<span data-ttu-id="e2aa8-130">应该看到以下结果：</span><span class="sxs-lookup"><span data-stu-id="e2aa8-130">You should see the following results:</span></span>

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a><span data-ttu-id="e2aa8-131">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e2aa8-131">Next steps</span></span>

<span data-ttu-id="e2aa8-132">接下来，查看[的教程， F# ](../tour.md)了解有关不同F#功能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e2aa8-132">Next, check out the [Tour of F#](../tour.md) to learn more about different F# features.</span></span>
